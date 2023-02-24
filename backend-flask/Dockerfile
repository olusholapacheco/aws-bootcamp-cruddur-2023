FROM python:3.10-slim-buster

# Insider Container
# Make a new folder inside the Container
WORKDIR /backend-flask

# Outside Container ----> Inside Container
# This contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

# Inside the container 
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container ----> Inside Container
# . means everything in the current directory
# first period . - /backend-flask (outside container)
# second period . - /backend-flask (inside container)
COPY . .

# Set environment variable (Env Vars)
# Inside Container and will remain set when the container is running

ENV FLASK_ENV=development

EXPOSE ${PORT}
# CMD (COMMAND)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]

