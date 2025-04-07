Here’s your **Flask Web Framework Learning Guide (8 hours)** with **complete examples** for each topic:

---

## 🌐 1. Introduction to Flask Framework

### 📦 Install Flask

```bash
pip install flask
```

### 🚀 Hello Flask

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hello, Flask!"

if __name__ == '__main__':
    app.run(debug=True)
```

> Visit: [http://127.0.0.1:5000](http://127.0.0.1:5000)

---

## 🔁 2. Flask Routing and Views

### 📍 Dynamic Routing

```python
@app.route('/hello/<name>')
def hello(name):
    return f"Hello, {name}!"
```

---

### 🧱 Rendering HTML Templates

**Directory Structure:**
```
/project
  └── app.py
  └── templates/
        └── index.html
```

**index.html**
```html
<!DOCTYPE html>
<html>
<head><title>Home</title></head>
<body>
  <h1>Welcome {{ name }}</h1>
</body>
</html>
```

**app.py**
```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html', name="Flask Learner")
```

---

## 📝 3. Flask Forms

### 📄 Install Flask-WTF

```bash
pip install flask-wtf
```

**form.py**
```python
from flask_wtf import FlaskForm
from wtforms import StringField, SubmitField
from wtforms.validators import DataRequired

class NameForm(FlaskForm):
    name = StringField('Your Name', validators=[DataRequired()])
    submit = SubmitField('Submit')
```

**app.py**
```python
from flask import Flask, render_template, request
from form import NameForm

app = Flask(__name__)
app.config['SECRET_KEY'] = 'secret!'

@app.route('/', methods=['GET', 'POST'])
def form():
    form = NameForm()
    name = None
    if form.validate_on_submit():
        name = form.name.data
    return render_template('form.html', form=form, name=name)
```

**templates/form.html**
```html
<form method="POST">
    {{ form.hidden_tag() }}
    {{ form.name.label }} {{ form.name() }}
    {{ form.submit() }}
</form>

{% if name %}
  <h2>Hello, {{ name }}!</h2>
{% endif %}
```

---

## 🗄️ 4. Database Integration (SQLite with SQLAlchemy)

### 📦 Install Flask SQLAlchemy

```bash
pip install flask-sqlalchemy
```

**app.py**
```python
from flask_sqlalchemy import SQLAlchemy

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///users.db'
db = SQLAlchemy(app)

class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(50), nullable=False)

@app.route('/add/<name>')
def add(name):
    user = User(name=name)
    db.session.add(user)
    db.session.commit()
    return f"User {name} added!"

with app.app_context():
    db.create_all()
```

---

## 🔐 5. User Authentication

### 📦 Install Flask-Login

```bash
pip install flask-login
```

**Setup Login System (basic)**

```python
from flask_login import LoginManager, UserMixin, login_user, login_required, logout_user

login_manager = LoginManager()
login_manager.init_app(app)

class User(UserMixin, db.Model):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(50), unique=True)
    password = db.Column(db.String(50))

@login_manager.user_loader
def load_user(user_id):
    return User.query.get(int(user_id))

@app.route('/login/<username>')
def login(username):
    user = User.query.filter_by(username=username).first()
    if user:
        login_user(user)
        return f"{username} logged in!"
    return "User not found."

@app.route('/protected')
@login_required
def protected():
    return "Logged-in only content."

@app.route('/logout')
@login_required
def logout():
    logout_user()
    return "Logged out"
```

---

## 🌐 6. Portfolio Website (from design to deployment)

### 📁 Folder Structure

```
/portfolio
  ├── app.py
  ├── templates/
  │   └── index.html
  ├── static/
  │   └── style.css
```

### **index.html**

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Portfolio</title>
  <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
  <h1>Hello, I'm Jane Doe</h1>
  <p>Web Developer | Python Enthusiast</p>
</body>
</html>
```

### **app.py**

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def portfolio():
    return render_template('index.html')
```

> To deploy: use [PythonAnywhere](https://www.pythonanywhere.com/) or [Render](https://render.com/)

---

## 🤖 7. ML Web App Deployment (Flask + ML Model)

### Example: House Price Predictor (with Pickle)

#### Step 1: Save your ML model
```python
import pickle
model = ... # trained sklearn model
with open('model.pkl', 'wb') as f:
    pickle.dump(model, f)
```

#### Step 2: Flask Web App

```python
import pickle
from flask import Flask, request, render_template

model = pickle.load(open('model.pkl', 'rb'))

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('predict.html')

@app.route('/predict', methods=['POST'])
def predict():
    features = [float(x) for x in request.form.values()]
    prediction = model.predict([features])
    return render_template('predict.html', result=prediction[0])
```

#### predict.html

```html
<form method="POST" action="/predict">
    <input type="text" name="feature1" placeholder="Feature 1">
    <input type="text" name="feature2" placeholder="Feature 2">
    <button type="submit">Predict</button>
</form>

{% if result %}
  <h2>Predicted Value: {{ result }}</h2>
{% endif %}
```

---

Let me know if you'd like:

✅ Starter template for a full Flask app  
✅ Hosting/deployment guide  
✅ Mini-project ideas for practice

Would you like to work on one of these now?