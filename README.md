# Item Catalog
==============================================

Hosted via Heroku here - (https://fsnd-item-catalog-app.herokuapp.com/catalog/)

## Description

> This repository contains a Web application that queries a database and then dynamically generates complete web pages and API endpoints.
> Set up to use a virtual machine - Vagrant (VM) to run our database server.

> In this project we develop a RESTful web application using the Python framework Flask along with implementing third-party OAuth authentication. Learn when to properly use the various HTTP methods available to you and how these methods relate to CRUD (create, read, update and delete) operations.

> This project was initially hosted on an Ubuntu instance via Amazon Lightsail, it is now hosted via Heroku, the instructions and github repo for the deployed version can be found [here](https://github.com/Christianq010/fsnd_Item-Catalog-heroku).

### About Our Projects

#### *Item Catalog*
* We use an Object-Relational Mapping (ORM) layer - SQLAlchemy to interact with our database.
* `GET` and `POST` requests that translate to CRUD operations.
* Using the Flask framework for development of our application.

We need to be able to successfully run the virtual machine in order to view our projects.

The VM is a Linux server system that runs on top of your own computer.
* We can share files easily between our computer and the VM.
* We'll be running a web service inside the VM which we'll be able to access from our regular browser locally.

We're using tools called Vagrant and VirtualBox to install and manage the VM. You'll need to install these to run the applications.

## Prerequisites -
* We'll be using a Unix-style terminal on your computer. On Windows, we recommend using the Git Bash terminal that comes with the Git software (www.git-scm.com).
* For Windows users, you may use putty (http://www.chiark.greenend.org.uk/~sgtatham/putty/) for SSH implementation.

## Instructions
* VirtualBox is the software that actually runs the virtual machine. Install VirtualBox - (https://www.virtualbox.org/wiki/Downloads).
* Vagrant is the software that configures the VM and lets you share files between your host computer and the VM's filesystem. Install Vagrant - (https://www.vagrantup.com/downloads.html).
 * To find out if vagrant has successfully installed type `vagrant --version` into git bash or cmd

## Configure the VM
* Use Github to fork and clone or download the the repository - https://github.com/udacity/fullstack-nanodegree-vm.
* Once you download the files and end up with a new local directory containing the VM files.
 * Change to this directory in your terminal with cd.
 * Inside, you will find another directory called vagrant. Change directory to the vagrant directory.

### Start the Virtual Machine
* Inside the vagrant subdirectory, run the command `vagrant up`
 * This will cause Vagrant to download the Linux operating system and install it. This may take quite a while (many minutes) depending on how fast your Internet connection is.
* Once you get your shell prompt back. Run `vagrant ssh` to log in to your newly installed Linux VM
 * If you have trouble with an SSH client you may use the authentication information provided and use Putty to explore the VM via SSH

### Running the Database
* The PostgreSQL database server will automatically be started inside the VM.
 * Run `psql` inside the VM command-line tool to access it and run SQL statements: eg. `select * from table_name;`
* Populate the database with some dummy data by running `python data.py` inside the VM.

### Logging out and in
* Run `vagrant reload` if you edit the Vagrant file or make other changes to code that would affect the virtual machine.
* If you type `exit` (or `Ctrl-D`) at the shell prompt inside the VM, you will be logged out, and put back into your host computer's shell. To log back in, make sure you're in the same directory and type `vagrant ssh` again.
* To exit Vagrant after the test simply type `logout`
* To momentarily stop Vagrant running in the background when done type `vagrant halt`
* `vagrant destroy` to destroy your virtual machine. The source code and the content of the data directory will remain unchanged.
* If you reboot your computer, you will need to run `vagrant up` to restart the VM.

### Create Google Client ID & Secret
* Create and then Go to your app's page in the Google APIs Console — https://console.developers.google.com/apis
* From Credentials from the menu on the left.
* Create an OAuth 2.0 Client ID.
* Choose Web application.
* You can then set the authorized JavaScript origins to `http://localhost:5000`.

### Create Facebook Client and Secret
* Create and then Go to your app's page in the Facebook Developers Console — https://developers.facebook.com/apps/
* Go to Settings from the menu on the left and select Add Product.
* Create Facebook Log in, configure Client OAuth Settings and Valid OAuth redirect URIs (http://localhost:5000) etc and save changes.
* Add your relevant APP ID to the Facebook Log in Script in `login.html`.
* Set the APP ID and APP Secret in the `fb_client_secrets.json` file.

### API Endpoints
* Show all Catalog names in JSON - `/catalog/JSON`.
* Show Items in Specific Catalog Page in JSON - `/catalog/<int:category_id>/items/JSON`
* Show individual Items in the URL in JSON - `/catalog/<int:category_id>/items/<int:menu_id>/JSON`


### Resources
* Udacity FSND Webcast on setting up Vagrant - https://www.youtube.com/watch?v=djnqoEO2rLc
* Refactor Code to Python PEP 8 style guide
  * http://pep8online.com/checkresult
  * https://stackoverflow.com/questions/10739843/how-should-i-format-a-long-url-in-a-python-comment-and-still-be-pep8-compliant
  * https://stackoverflow.com/questions/1874592/how-to-write-very-long-string-that-conforms-with-pep8-and-prevent-e501
  * https://stackoverflow.com/questions/40003378/pep8-error-in-import-line-e501-line-too-long
