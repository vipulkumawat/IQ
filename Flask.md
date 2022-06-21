**Flask Doc**

```

Flask is a web application framework written in Python.
Flask is based on Werkzeug WSGI toolkit and Jinja2 template engine. Both are Pocco projects.

What is Web Framework?
Web Application Framework or simply Web Framework represents a collection of libraries and modules that enables a web application developer to write applications without having to bother about low-level details such as protocols, thread management etc.

WSGI
Web Server Gateway Interface (WSGI) has been adopted as a standard for Python web application development. WSGI is a specification for a universal interface between the web server and the web applications.

Werkzeug
It is a WSGI toolkit, which implements requests, response objects, and other utility functions. This enables building a web framework on top of it. The Flask framework uses Werkzeug as one of its bases.

Jinja2
Jinja2 is a popular templating engine for Python. A web templating system combines a template with a certain data source to render dynamic web pages.

Flask is often referred to as a micro framework. It aims to keep the core of an application simple yet extensible. Flask does not have built-in abstraction layer for database handling, nor does it have form a validation support. Instead, Flask supports the extensions to add such functionality to the application. 



Install virtualenv for development environment
virtualenv is a virtual Python environment builder. It helps a user to create multiple Python environments side-by-side. Thereby, it can avoid compatibility issues between the different versions of the libraries.

The following command installs virtualenv

pip install virtualenv
This command needs administrator privileges. Add sudo before pip on Linux/Mac OS. If you are on Windows, log in as Administrator. On Ubuntu virtualenv may be installed using its package manager.

Sudo apt-get install virtualenv
Once installed, new virtual environment is created in a folder.

mkdir newproj
cd newproj
virtualenv venv



To activate corresponding environment, on Linux/OS X, use the following −

venv/bin/activate
On Windows, following can be used

venv\scripts\activate
We are now ready to install Flask in this environment.

pip install Flask


In order to test Flask installation, type the following code in the editor as Hello.py

from flask import Flask
app= Flask(__name__)

@app.route('/')
def hello_world():
	return 'Hello World'

if __name__=='__main__':
	app.run()


Importing flask module in the project is mandatory. An object of Flask class is our WSGI application.

Flask constructor takes the name of current module (__name__) as argument.

The route() function of the Flask class is a decorator, which tells the application which URL should call the associated function.

app.route(rule, options)
The rule parameter represents URL binding with the function.

The options is a list of parameters to be forwarded to the underlying Rule object.

In the above example, ‘/’ URL is bound with hello_world() function. Hence, when the home page of web server is opened in browser, the output of this function will be rendered.

Finally the run() method of Flask class runs the application on the local development server.

app.run(host, port, debug, options)


All parameters are optional
host

Hostname to listen on. Defaults to 127.0.0.1 (localhost). Set to ‘0.0.0.0’ to have server available externally

2	
port

Defaults to 5000

3	
debug

Defaults to false. If set to true, provides a debug information

4	
options

To be forwarded to underlying Werkzeug server.

The above given Python script is executed from Python shell.

Python Hello.py

Debug mode
A Flask application is started by calling the run() method. However, while the application is under development, it should be restarted manually for each change in the code. To avoid this inconvenience, enable debug support. The server will then reload itself if the code changes. It will also provide a useful debugger to track the errors if any, in the application.

The Debug mode is enabled by setting the debug property of the application object to True before running or passing the debug parameter to the run() method.

app.debug = True
app.run()
app.run(debug = True)


Flask – Routing:
Modern web frameworks use the routing technique to help a user remember application URLs. It is useful to access the desired page directly without having to navigate from the home page.

The route() decorator in Flask is used to bind URL to a function. For example −

@app.route(‘/hello’)
def hello_world():
   return ‘hello world’
Here, URL ‘/hello’ rule is bound to the hello_world() function. As a result, if a user visits http://localhost:5000/hello URL, the output of the hello_world() function will be rendered in the browser.

The add_url_rule() function of an application object is also available to bind a URL with a function as in the above example, route() is used.

A decorator’s purpose is also served by the following representation −

def hello_world():
   return ‘hello world’
app.add_url_rule(‘/’, ‘hello’, hello_world)



Variable Rules:
It is possible to build a URL dynamically, by adding variable parts to the rule parameter. This variable part is marked as <variable-name>. It is passed as a keyword argument to the function with which the rule is associated.

In the following example, the rule parameter of route() decorator contains <name> variable part attached to URL ‘/hello’. Hence, if the http://localhost:5000/hello/TutorialsPoint is entered as a URL in the browser, ‘TutorialPoint’ will be supplied to hello() function as argument.

from flask import Flask
app = Flask(__name__)

@app.route('/hello/<name>')
def hello_name(name):
   return 'Hello %s!' % name

if __name__ == '__main__':
   app.run(debug = True)

In addition to the default string variable part, rules can be constructed using the following converters −

Sr.No.	Converters & Description
1	
int

accepts integer

2	
float

For floating point value

3	
path

accepts slashes used as directory separator character

from flask import Flask
app = Flask(__name__)

@app.route('/blog/<int:postID>')
def show_blog(postID):
   return 'Blog Number %d' % postID

@app.route('/rev/<float:revNo>')
def revision(revNo):
   return 'Revision Number %f' % revNo

if __name__ == '__main__':
   app.run()


The URL rules of Flask are based on Werkzeug’s routing module. This ensures that the URLs formed are unique and based on precedents laid down by Apache.


from flask import Flask
app = Flask(__name__)

@app.route('/flask')
def hello_flask():
   return 'Hello Flask'

@app.route('/python/')
def hello_python():
   return 'Hello Python'

if __name__ == '__main__':
   app.run()



Both the rules appear similar but in the second rule, trailing slash (/) is used. As a result, it becomes a canonical URL. Hence, using /python or /python/ returns the same output. However, in case of the first rule, /flask/ URL results in 404 Not Found page.




```