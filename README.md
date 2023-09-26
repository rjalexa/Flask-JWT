# Flask API JWT access control with pydantic, flasgger and MongoDB backend, all dockerized and orchestrated by docker compose example
![flask](https://github.com/rjalexa/Flask-JWT/assets/15216911/4a5481b3-4800-4369-aedc-c3a340e18e0c)
![jwt](https://github.com/rjalexa/Flask-JWT/assets/15216911/c1cb54b2-deff-405a-b180-be394d8d80b3)
![flasgger](https://github.com/rjalexa/Flask-JWT/assets/15216911/0090a04e-8b0a-4ca5-b537-72c94bda3267)
![gunicorn](https://github.com/rjalexa/Flask-JWT/assets/15216911/30e18d2d-98a8-4750-a2b3-2f25354e68aa)
![mongodb](https://github.com/rjalexa/Flask-JWT/assets/15216911/bfd75154-4f33-4834-8b78-668bd2fdecad)
![pydantic](https://github.com/rjalexa/Flask-JWT/assets/15216911/3e36eb50-a5a2-43ab-b087-a7b08cb9b326)
![openapi](https://github.com/rjalexa/Flask-JWT/assets/15216911/0c91d8f9-2c57-4187-8bcb-d8584ce20388)
![docker](https://github.com/rjalexa/Flask-JWT/assets/15216911/0942570b-ce29-4ca9-b93d-80108ae5f532)
![docker-compose](https://github.com/rjalexa/Flask-JWT/assets/15216911/1aaca4bf-6ea6-4c2a-b3ff-e83fd4a9b08a)

    started from this: https://github.com/Gimyk/Rest_API_Flask
    then slowly fixed/evolved to show:
    * tokenreq decorator function to secure routes
    * signup route: to get a username, email and password and store it in MongoDB
    * login route: to use the username and password values to get an access and a refresh JWT tokens
    * refresh route: when the short lived access JWT expires, use the refresh token to get a new one
    * unprotected route: to show a non protected route
    * protected route: to show a protected route. you can access it after login, then after the access token expires, you can use the refresh route to get a new one
    Added several security related techniques.
                     
    As a demo it depends on an unprotected localhost:27017 mongodb backend

    The .env file sets needed environment variables. Please use the .env.example as a template, copy it to a .env file and edit the entries to change token
    expiry times and secrets and remove the comments

    The pyproject.toml file lists prerequisites to be installed by poetry. run poetry install 
    to install all prerequisite libraries
    
    To work under gunicorn: install gunicorn with pip3 but within the poetry shell enviroment.
    To check issue a 'which gunicorn' and you should see it's in the .venv .
    To run it under the VSCode debugger you also need a launch.json such as:
    ```
    {
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Python: Flask",
            "type": "python",
            "request": "launch",
            "program": "/Users/bob/code/Rest_API_Flask/.venv/bin/gunicorn",
            "gevent": true,
            "args": ["app.run:app", "--bind=127.0.0.1:8000", "--reload", "-w", "4"]
        }
    ]
}
```
Please note that using the simple RUN command will not launch gunicorn but werkzeug on port 5000
