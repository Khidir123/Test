# My Healthcare App (HealthPortalPro)

## Table of Contents
- [Introduction](#introduction)
- [Pre-requisites](#pre-requisites)
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)

## Introduction
Brief overview of the healthcare app and its purpose.

## Pre-requisites
1. Docker
2. Docker Compose
3. Make
4. Self Signed SSL Certificate

## Installation
1. For Ubuntu
2. For Windows

### Installing Make on Ubuntu
#### 1. Update apt Database
```bash
$ sudo apt update
```
#### 2. Install Make
```bash
$ sudo apt -y install make
```
#### 3. Verify Installation
```bash
$ make --version
```

### Installing Make on Windows
##### 1. Run Powershell as an administrator
Windows Search > Windows Powershell > Right Click > Run as Administrator

##### 2. Check output of `Get-ExecutionPolicy`
If `Get-ExecutionPolicy` returns `Restricted`, run the following command.
```
$ Set-ExecutionPolicy AllSigned
```
If it is already unrestricted, then you can skip this step.

##### 3. Install `chocolatey`
```
$ Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

##### 4. Install `Make`
```
$ choco install make
```

##### 5. Test Make installation
```
$ make -version
```

##### 6. Reset Execution Policy
```
$ Set-ExecutionPolicy Restricted
```

## Creating a Self Signed SSL Certificate

#### 1. Follow the instructions below
Click [here](https://devopscube.com/create-self-signed-certificates-openssl/).
#### 2. Add the rootCA.crt to your trusted root certificates E.g. For Chrome

##### Go to your browser settings -> Privacy and security -> Security -> Manage Device Certificates
##### Go to Authorities and import the rootCA.crt file from your certificate folder

### Deployment Guide
#### 1. Clone the repository
```bash
$ gh repo clone HelloTech69/HealthCareApp
```

#### 2. Navigate to the project directory
```bash
$ cd HealthCareApp
```

#### 3. In the config folder, create a certs folder if it does not exist
#### 4. Copy the domain name or your IP .crt and .key files to the certs folder

#### 5. Build the Docker image
```bash
$ make build
```

#### 6. Run the Docker container
```bash
$ make up
```

#### 7. Just for Myself
In the server folder, modify the node env do production, modify sessionMiddleware, modify the config
In the client folder, modify the server/deployment url
In google console and github Oauth, modify the redirect url

## Usage
Guidance on how to use the app effectively.

## Features

1. **Nutrition Information**
    - Access to a vast food database with detailed nutritional information through the Edamam API.
    - Search for specific foods and retrieve comprehensive nutrition details.
    - Create personalized meal plans and track daily nutritional intake.

2. **Recipe Analysis**
    - Utilize the Edamam API to analyze recipes based on their ingredients.
    - Calculate calorie content, macronutrient breakdown, and other nutritional insights for recipes.
    - Make informed dietary choices by understanding the nutritional value of your favorite dishes.

3. **Smart Exercise Assistant**
    - Use Tenserflow library to track the right posture for exercise
    - Also provides counter for user to keep track of exercise currently being done
    - Ensures users are doing the exercise correctly

4. **Feature 4**
    - Description of feature 4
    - Description of feature 4
    - Description of feature 4

## API Documentation
#### For viewing the API documentation, run the application and visit the following URL:
```bash
http://localhost:3500/api-docs
```

## Contributing
Guidelines for contributing to the project.

## License
Information about the project's license and usage rights.
