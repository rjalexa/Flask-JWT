Certainly, here's the cleaned-up version of your Markdown content. It includes proper formatting, corrections to the image URLs, and minor text improvements for clarity.

---

# Flask API JWT Access Control: An Example with Pydantic, Flasgger, and MongoDB

![Flask](https://github.com/rjalexa/Flask-JWT/blob/main/assets/4a5481b3-4800-4369-aedc-c3a340e18e0c.png)
![JWT](https://github.com/rjalexa/Flask-JWT/blob/main/assets/c1cb54b2-deff-405a-b180-be394d8d80b3.png)
![Flasgger](https://github.com/rjalexa/Flask-JWT/blob/main/assets/0090a04e-8b0a-4ca5-b537-72c94bda3267.png)
![Gunicorn](https://github.com/rjalexa/Flask-JWT/blob/main/assets/30e18d2d-98a8-4750-a2b3-2f25354e68aa.png)
![MongoDB](https://github.com/rjalexa/Flask-JWT/blob/main/assets/bfd75154-4f33-4834-8b78-668bd2fdecad.png)
![Pydantic](https://github.com/rjalexa/Flask-JWT/blob/main/assets/3e36eb50-a5a2-43ab-b087-a7b08cb9b326.png)
![OpenAPI](https://github.com/rjalexa/Flask-JWT/blob/main/assets/0c91d8f9-2c57-4187-8bcb-d8584ce20388.png)
![Docker](https://github.com/rjalexa/Flask-JWT/blob/main/assets/0942570b-ce29-4ca9-b93d-80108ae5f532.png)
![Docker-Compose](https://github.com/rjalexa/Flask-JWT/blob/main/assets/1aaca4bf-6ea6-4c2a-b3ff-e83fd4a9b08a.png)

**Source:** [GitHub Repository](https://github.com/Gimyk/Rest_API_Flask)

This project has evolved to demonstrate several functionalities:

- `tokenreq` decorator function for route security.
- Signup route for registering a username, email, and password in MongoDB.
- Login route for obtaining access and refresh JWT tokens.
- Refresh route for renewing the access token when it expires.
- Unprotected and protected routes to demonstrate JWT-based security measures.

## Security Techniques

Several security techniques have been added. The application uses an unprotected MongoDB backend running on `localhost:27017`.

## Configuration Files

- **.env**: Set environment variables. Use `.env.example` as a template.
- **pyproject.toml**: Lists prerequisites. Run `poetry install` to install dependencies.

## Gunicorn Support

Install Gunicorn within the poetry shell environment. To verify the installation, run `which gunicorn`.

### VSCode Debugging

You'll need a `launch.json` file as shown below to run the app in debugging mode.

```json
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

Note: Using the simple RUN command in VSCode will launch Werkzeug on port 5000, not Gunicorn.

## Running the Code

For shell execution, use the provided `runme.sh` script. In this case, Gunicorn is launched as a Python module, not as an installed binary.

---

Let me know if this revision meets your requirements.
