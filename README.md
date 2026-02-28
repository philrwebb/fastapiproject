# Deploying a real fastapi project to render.com

I had recently gone through a youtube tutorial from TechWithTim around building an API using fastapi. It included use of a separate image repository (imagekit.io) and JWT authentication/authorisation.

A fun project with some real-world use cases and lessons.

Then I got to thinking - how could you deploy a python based api to the web. Once again - youtube video came to the rescue and after some mucking around (see below) got the whole thing working. The deploy was as easy as creating YAML with all the necessary declarative stuff and hitting a button. Render looks at your git repository and based on the YAML deploys the api and backend db in postgres.

This repository has all that is necessary. If you want to run it on local server for dev then clone this project:

```sh
git clone https://github.com/philrwebb/fastapiproject.git
```

Then change into the project folder and:

```sh
uv run main.py
```

This above assumes you have uv (a rust based package manager for python available) - you can install via

```sh
pip install uv
```

Once you go to uv I guarantee you will never go back to pip.

Following download to development you can run the app with:

```
uv run main.py
```

Because it is written with the FastAPI library it support a docs url that allows you to try things out. This will be at:

http://localhost:8000/docs

First run against this will set up and run the database creation (sqlite in dev) and create the users and posts tables.
