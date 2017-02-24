anno-lambda-preview
===================

* [What is this?](#what-is-this)
* [Assumptions](#assumptions)
* [What's in here?](#whats-in-here)
* [Bootstrap the project](#bootstrap-the-project)
* [Run the project](#run-the-project)

What is this?
-------------

AWS lambda function that generates the anno-docs preview, its main purpose if to offer a more autonomous way of previewing annotations on the editorial side.

This is a work in progress repo.

Assumptions
-----------

The following things are assumed to be true in this documentation.

* You are running OSX.
* You are using Python 2.7. (Probably the version that came OSX.)
* You have [virtualenv](https://pypi.python.org/pypi/virtualenv) and [virtualenvwrapper](https://pypi.python.org/pypi/virtualenvwrapper) installed and working.
* You have NPR's AWS credentials stored as environment variables locally.

For more details on the technology stack used with the app-template, see our [development environment blog post](http://blog.apps.npr.org/2013/06/06/how-to-setup-a-developers-environment.html).

What's in here?
---------------

The project contains the following folders and important files:

* ``code`` -- Where are lambda function code lives
* ``test``-- local tests to check that our code runs locally
* ``fabfile.py`` -- [Fabric](http://docs.fabfile.org/en/latest/) commands for automating setup and deployment
* ``requirements.txt`` -- Python requirements.

Bootstrap the project
---------------------

To bootstrap the project:

```
cd anno-lambda-preview
mkvirtualenv anno-lambda-preview
pip install -r requirements.txt
```

Run the project
---------------

Review the code for your lambda function, include all the required libraries in `code/requirements.txt`

Create a function in your AWS lambda environment.

Then run:

```
fab deploy:code,function=FUNCTION_NAME
```

Where `FUNCTION_NAME` is the name of the created lambda function
