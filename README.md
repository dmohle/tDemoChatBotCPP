# tDemoChatBotCPP
tDemoChatBotCPP

demo for CPP class on Noc 6, 2023

## Creating a Simple Flask Web Application
### Overview
This guide will help you create a basic web application using Python and the Flask web framework. The application will display a background image and allow users to enter and display text.

### Prerequisites
Python installed on your computer.
Flask framework installed (pip install Flask).
Step-by-Step Guide
##1. Project Setup
Create a new directory for your project.

Inside the project directory, create the following files:

app.py: Python script for your web application.
templates folder: Create a folder named "templates" to store your HTML templates.
static folder: Create a folder named "static" to store static files like images.
## 2. HTML Template
Create an HTML file named index.html inside the "templates" folder. You can customize this file as desired. Here's an example:

html
Copy code
<!DOCTYPE html>
<html>
<head>
    <title>Welcome to your personal AI Chatbot!</title>
    <style>
        body {
            background-image: url('/static/twoRobotsReading.png');
            background-size: cover;
            background-repeat: no-repeat;
            background-attachment: fixed;
        }
    </style>
</head>
<body>
    <h2>Enter your prompt here:</h2>
    <form method="POST">
        <textarea name="question" rows="2" cols="100">{{ textQuestion }}</textarea><br>
        <input type="submit" value="Click to get your response!">
    </form>
    <textarea name="answer" rows="4" cols="100">{{ textAnswer }}</textarea><br>
</body>
</html>
## 3. Python Code
In your app.py file, write the Python code for your web application. Here's an example using Flask:

python
Copy code
from flask import Flask, request, render_template

app = Flask(__name__)

@app.route("/", methods=["GET", "POST"])
def start_here():
    if request.method == "POST":
        text_question = request.form.get("question")
        text_answer = text_question
        return render_template("index.html", textQuestion=text_question, textAnswer=text_answer)
    return render_template("index.html", textQuestion="", textAnswer="")

if __name__ == "__main__":
    app.run(debug=True)
## 4. Static Files
Place the background image file (e.g., twoRobotsReading.png) in the "static" folder.

Update the CSS in your HTML template to reference the image correctly:

css
Copy code
background-image: url('/static/twoRobotsReading.png');
## 5. Run Your Application
Open a terminal, navigate to your project directory, and run your Flask application:

Copy code
python app.py
Access your website in a web browser at http://127.0.0.1:5000/ or http://localhost:5000/.

You should see the web page with the background image and the ability to enter and display text.

This guide outlines the steps to create a basic Flask web application. Students can use this as a starting point for web development projects and further enhance the application with more features and functionality.
