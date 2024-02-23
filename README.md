# Project Setup Guide

To run this project, you need to have the following prerequisites installed:

- Poetry
- Ngrok

## Installation Steps

1. Clone this repository using Git:
```
# github cli
gh repo clone ab-dauletkhan/python-whatsapp-assistant

# git clone

git clone https://github.com/ab-dauletkhan/python-whatsapp-assistant.git
# or

git clone git@github.com:ab-dauletkhan/python-whatsapp-assistant.git
```

2. Navigate to the root directory of the project and install dependencies using Poetry:
```
poetry install
```

3. Setup Ngrok:

- Register at Ngrok, verify your account, and optionally enable two-factor authentication.
- Follow the setup steps described on [Ngrok Dashboard](https://dashboard.ngrok.com/get-started/setup) for your operating system.

Example for macOS using Homebrew:
```
brew install ngrok/ngrok/ngrok
ngrok authtoken <your-auth-token> # from Ngrok dashboard

```
> Don't rush to deploy now; we'll run it together with Flask later.

4. Copy the example environment file and fill in the required fields:
```
cp example.env .env

```

## Running the Server

1. Activate the virtual environment using Poetry:
```
poetry shell
```
> Note: This will just activate the virtual environment.

2. Inside the Poetry shell, run the following command to start the server:
```
python run.py
```

3. Deploy your application online using Ngrok:

- At Ngrok, navigate to "Deploy your app online" and choose "Static Domain" (required for Meta).
- Open another Poetry shell and run:
  ```
  ngrok http 8000 --domain=<your_domain>.ngrok-free.app
  ```

Ensure that you're using port 8000 since the Flask app will be running on this port locally.

That's it! Your project should now be up and running.