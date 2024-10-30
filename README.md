#Creating a docker image
Hosted a flask application through docker . 

Radhe Radhe
Description
This repository contains the complete setup and configuration process for deploying a Flask application using Docker on an Ubuntu operating system. The following steps outline the changes made to the package management systems, the source code integration, and the entry point configuration.

Environment Setup
OS
Operating System: Ubuntu
Changes in APT Packages
To ensure all necessary dependencies are installed, the following command was executed:



RUN apt-get update && apt-get -y install python
This updates the package lists and installs Python.

Changes in PIP Packages
To install the required Python packages for the Flask application, the following command was executed:


RUN pip install flask flask-mysql
This installs the Flask web framework and the Flask-MySQL extension for database connectivity.

Source Code Integration
The source code for the Flask application was copied into the Docker image with the following command:


COPY /opt/source-code
This command ensures that the application code is included in the Docker image during the build process.

Update Entry Point
To set the entry point for the application, the following command was specified in the Dockerfile:

dockerfile
Copy code
ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask run
This command configures the Docker container to start the Flask application using the specified entry point, which includes the application file location.

Conclusion
This setup process provides a streamlined method for deploying a Flask application in a Docker container on an Ubuntu system. The configurations ensure that all necessary dependencies are installed and that the application can be run seamlessly within the container environment.
