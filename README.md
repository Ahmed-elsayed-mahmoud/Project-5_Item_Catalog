# Item Catalog App

## Project Overview 

This is a python module that creates a website and JSON API for a list of items grouped into a category and integrates third-party user registration and authentication.
 Users can edit or delete items they've creating. Adding items, deleteing items and editing items requiring logging in with Google+.


## Setting up your computer

These dependencies must be installed before you can run the app. The easiest way to do so is by using [pip](https://pypi.python.org/pypi/pip). Simply run the following commands:

    pip install Flask
	pip install SQLAlchemy
	pip install Flask-GoogleLogin

As the app uses Google for authentication as the next step you have to obtain a client id and client secret from Google:

1. go to https://console.developers.google.com/project and login with Google.
2. Create a new project
3. Name the project
4. Select "API Manager-> Credentials-> Create credentials -> "OAth client ID" 
5. Select Web Application
6. On the consent screen, type in a product name and save.
7. In **Authorized javascript origins** field add:
    http://0.0.0.0:8080
    http://localhost:8080
8. In **Authorized redirect URIs** field add:
	http://localhost:8080/oauth2callback/
9. Open the **project.py** file and replace the **<Client ID\>** and **<Client Secret\>** placeholders with your client id and your client secret.


## How To Run 

For the first time you have to create the categories. To do so run

	`python database_setup.py`
	
To start the app simply run
	
	`python project.py`

	
Now you can open in a webpage by going to either:
    http://0.0.0.0:8080
    http://localhost:8080 
	

## Files of the project

* main.py -- python script with flask main application
* itemcatalog.db -- sqlite database for item catalog
* database_setup.py -- pathon script for sqlalchemy database schema with sample data
* static/styles/style.css -- css style for all views
* templates/index.html -- template for catalog and category overview
* templates/create_item.html -- template for item add view
* templates/delete_item.html -- template for item delete view
* templates/edit_item.html -- template for item edit view
* templates/show_item.html -- template for item view
* templates/login.html -- template for login with Google+ view
* templates/list_items.html -- template for all items created view
* templates/latest_items.html -- template for latest items created view

## Frameworks/technologies used

This app uses 

- [Flask](http://flask.pocoo.org)
- [SQLAlchemy](http://www.sqlalchemy.org)
- [Flask-GoogleLogin](https://pythonhosted.org/Flask-GoogleLogin/)


## Remarks 
- The app uses [Jasny Bootstrap's](http://jasny.github.io/bootstrap/javascript/#fileinput) file input widget for the picture upload.
- The pictures are stored in the database.
- The app uses nonces to prevent cross-site request forgeries (CSFR) when creating, updating and deleting items.
- The app offers two API endpoints:
	- **JSON:** /catalog.json
	- **XML:** /catalog.xml
- The app uses a (slightly modified) **dashboard.css** stylesheet from Bootstrap's [Dashboard sample page](http://getbootstrap.com/examples/dashboard/).
- The app is not optimized for small devices (smartphones etc.).


## License

The project is licensed under the [Apache License](LICENSE).