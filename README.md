# Docker Exercises

This repository contains exercises that I used for learning Docker. It includes various examples and projects that demonstrate how to use Docker to containerize applications.

## Dockerizing a Python Program

To Dockerize a Python program, follow these steps:

1. Create a new directory for your project and navigate to it in your terminal.
2. Create a new file called `Dockerfile` in your project directory with the following contents:

    ```
    # Use an official Python runtime as a parent image
    FROM python:alpine

    # Set the working directory to /app
    WORKDIR /app

    # Copy the current directory contents into the container at /app
    COPY . /app

    # Install any needed packages specified in requirements.txt
    RUN pip install --trusted-host pypi.python.org -r requirements.txt

    # Run app.py when the container launches
    CMD ["python", "app.py"]
    ```

3. Create a new file called `requirements.txt` in your project directory with any dependencies your Python program requires.
4. Build your Docker image by running the following command in your terminal:

    ```
    docker build -t my-python-app .
    ```

   This command builds a Docker image called `my-python-app` using the `Dockerfile` in your current directory. The `.` specifies that the build context is the current directory.
5. Run your Docker container by running the following command in your terminal:

    ```
    docker run my-python-app
    ```

   This will start a new container and run your Python program.
