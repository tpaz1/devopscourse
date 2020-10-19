# **`multistage Dockerfile` tutorial**
in this tutorial we are gonna work on our `multistage Dockerfile` skills.  
We will create a dockerfile that runs a pipeline — covering build, lint,code analysis, test, and finally deployment.
This will allow us to create a Container pipeline instead of building custom Jobs for every
project in [`JENKINS`](https://www.jenkins.io/doc/book/) or [`CircleCI`](https://circleci.com/product/) for that matter.
This will also allow us to seamlessly create container pipeline and reuse it with any CI/CD framework.

### Pre requirements 
- `Docker` [installed](https://docs.docker.com/get-docker/)

Our `Dockerfile` stages will be:
* Builder stage - getting our application files and installing requirements with python package manager [`pip`](https://www.w3schools.com/python/python_pip.asp)
* [`Pylint`](https://www.pylint.org/) stage - using it for error detection as a code analysis tool.
* Unit test stage - testing our code as a unit for a quick debugging before the integration test. [Unit Test vs Integration Test](https://www.guru99.com/unit-test-vs-integration-test.html) 
* Final stage - with that done a new image of our application will be created.

What we've accomplished:

- Our final image will have only the required files that it needs to run with and no Source code will be stored in it.

- It passed Lint tests and Unit tests in one shoot without a single push to central repo.

- Meaning that the developer don't need to wait for a CI/CD to run the tests or wait for his turn / job completion in the CI/CD.

- and of course the size - Multistage build vs single stage build


