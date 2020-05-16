# Python Flask app example
Use this example to demostrate CI/CD techniques on Minikube. The application is a simple python flask example with a test.

The configuration includes Dockerfile defining the app image.

## Prerequisites

* Access to DockerHub
* Functional Kubernetes environment (minikube)
* Container runtime (docker, podman)

## Manual steps

### Run locally

In local development developers can start the app running as a service with: `python run.py`. 

The app listens on 5000/TCP. It can be tested with `curl http://localhost:5000/` 

To run tests: `nosetests . --with-xunit` . It produces nosetests.xml test report compatible with JUnit.

### Build and run image

To build a container image using docker run in a current directory: `docker build -t flask-demo .`

With podman: `podman build -t flask-demo .`

Note: docker and podman provide similar syntax.

To start a container from an image: `docker run -it --rm -p 5000:5000 flask-demo`

Test: `curl http://localhost:5000`