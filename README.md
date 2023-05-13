# Video Sharing

A video sharing platform that uses React, Vite, Nest.js, and TypeScript that allows users to easily share their favorite YouTube URLs.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Live Build

- [Video Sharing App Website](https://video-sharing-fe.vercel.app/) 👈

## Source Code

- [video-sharing-fe](https://github.com/nguyennhuttoan/video-sharing-fe) (Front-end) 👈

- [video-sharing-be](https://github.com/nguyennhuttoan/video-sharing-be) (Back-end) 👈

## Introduction

This video sharing app written in TypeScript is designed to make sharing YouTube videos quick and easy. Simply copy and paste the URL of the video you want to share, and the app will publish a preview of the video. This app uses Nest.js and React + TypeScript using Vite build tool.

## Prerequisites

- [Node.js](https://nodejs.org/en/download/) 18.16.0 (LTS) which includes [Node Package Manager](https://www.npmjs.com/get-npm)

- [MongoDB](https://www.mongodb.com/download-center/community) (6.0.5)

- [Git](https://git-scm.com/)

- [Docker Desktop](https://www.docker.com/products/docker-desktop)

## Installation & Configuration

To start using Video Sharing, clone the repository:

- Front-end

```bash
git  clone  https://github.com/nguyennhuttoan/video-sharing-fe
```

- Back-end

```bash
git  clone  https://github.com/nguyennhuttoan/video-sharing-be
```

- Install the required packages via NPM:

```bash
npm  install
```

## Database Setup

Download and install - [MongoDB](https://www.mongodb.com/download-center/community) (6.0.5). 1. Once the download is complete, double-click the downloaded file to begin the installation process.

Follow the prompts to install MongoDB, selecting the default options for most settings. 1. Finally, you can start the MongoDB server by running the following command in a terminal or command prompt:

```bash
mongod
```

This will start the MongoDB server and it should now be running on your local machine.

## Running the Application for Development

- Front-end

```bash
npm  run  dev
```

- Back-end

```bash
npm  run  start:dev
```

## Testing

### Unit tests

Simply run the following command:

```bash
npm  run  test
```

![enter image description here](https://i.imgur.com/OYhLhCu.png)

## Configuration

### Backend

- DB_URI: `mongo database uri`

- JWT_SECRET: `generating a token for authentication`

- JWT_EXPIRES: `expires time of jwt token`

- PORT: `server port for developing or testing`

### Frontend

- VITE_API_URL: `API URL of backend service`

## Docker Deployment

First, you must install [Docker Desktop](https://www.docker.com/products/docker-desktop) on your device, and check if it installed with command:

```bash
docker  --version
```

Next, look at `docker-compose.yml` file on your root directory. After that, open `terminal` on your project and run:

```bash
docker-compose  build
```

Containers are shown after composing:
![enter image description here](https://i.imgur.com/BfR1dgF.png)

## Heroku Deployment

### Prerequisites

- [video-sharing-be](https://github.com/nguyennhuttoan/video-sharing-be)

- [Heroku account](https://signup.heroku.com/)

- [Heroku CLI](https://cli.heroku.com/)

### Overview

`Heroku Node.js` support will only be applied when the application has a `package.json` file in the root directory

### Build the app and run it locally

```bash
npm  run  start
```

Start your app locally using the `heroku local` command, which is installed as part of the `Heroku CLI`

```bash
heroku  local  web
```

Your app should now be running on `http://localhost:<your-port>`.

## Deploy the application to Heroku

### Backend

After you commit your changes to git, you can deploy your app to `Heroku`

```bash
git  add  .



git  commit  -m  "Something"



heroku  login



Enter  your  Heroku  credentials.



...



heroku  create



git  push  heroku  master



...



----->  Node.js  app  detected



...



----->  Launching...  done



http://<your-app-name>.herokuapp.com  deployed  to  Heroku
```

To open the app in your browser, type:

```bash
heroku  open
```

## Vercel Frontend Deployment

### Prerequisites

- [video-sharing-fe](https://github.com/nguyennhuttoan/video-sharing-fe)

- [Vercel CLI](https://cli.heroku.com/)

Run the following command:

```bash
vercel  .
```

The app will be deployed by Vercel CLI (below image):

![enter image description here](https://i.imgur.com/C9dvfQj.png)

## Notable Packages

- [Nest.js](https://docs.nestjs.com/)

- [Vite.js](https://www.npmjs.com/package/vite)

- [Ant Design](https://www.npmjs.com/package/antd)

- [Mongoose](https://www.npmjs.com/package/mongoose)

- [Axios](https://www.npmjs.com/package/axios)

- [ReactPlayer](https://www.npmjs.com/package/react-player)

- [JWT](https://www.npmjs.com/package/jwt)

- more and more can be found at [front-end](https://github.com/nguyennhuttoan/video-sharing-fe/blob/main/package.json) and [backend](https://github.com/nguyennhuttoan/video-sharing-be/blob/master/package.json) package.json files.

## API Document

## Features

### Authentication and Authorization

The Auth APIs enables you to manage all aspects of user identity. If offers endpoints so users can log in, sign up.

#### Register & Login account

Description: The Register and Login API lets user create an account if the email they entered is not registered yet in the database or performing authenticate if the account is registered.

- **URL**: /v1/auth/login

- **Method**: POST

- **URL Params**: None

- **Request Body**:

```json
{
  "email": "example@email.com",

  "password": "password"
}
```

- **Success Response**:

- Code: 201 or 200

- Content:

```json
{
  "token": "your token here"
}
```

- **Error Response**:

- Condition: There was a problem with the request. Check the request parameters and JSON format.

- Code: 401

- Content:

```json
{
  "statusCode": 401,

  "message": "Invalid email or password",

  "error": "Unauthorized"
}
```

#### Video Management

#### Get all videos

Description: Get videos in system and return a list of videos.

- **URL**: /v1/video

- **Method**: GET

- **URL Params**: None

- **Success Response**:

- Code: 200

- Content:

```json
[
  {
    "title": "Test2",

    "description": "Test2",

    "url": "https://www.youtube.com/watch?v=testing1234"
  },

  {
    "title": "Test1",

    "description": "Test1",

    "url": "https://www.youtube.com/watch?v=testing123"
  }
]
```

#### Create a video

- **URL**: /v1/video

- **Method**: POST

- **Request Headers**:

```

{ "Authorization" : "Bearer token" }

```

- **Success Response**:

- Code: 200

- Content:

```json
{
  "title": "Test3",

  "description": "test3",

  "url": "https://www.youtube.com/watch?v=Test3",

  "user": "645f4102ee701bd6de3b6a74",

  "_id": "645f44e6ee701bd6de3b6a7c",

  "createdAt": "2023-05-13T08:05:58.197Z",

  "updatedAt": "2023-05-13T08:05:58.197Z",

  "__v": 0
}
```

- **Error Response**:

- Code: 401

- Content:

```json
{
  "statusCode": 401,

  "message": "Invalid email or password",

  "error": "Unauthorized"
}
```

## Usage

### Homepage

This is our homepage. In this page we can view a list of YouTube videos that have been uploaded by users. There also have 2 textboxes that prompt user to enter their email and password. Feel free to enter your email and hit Login/Register button.
![enter image description here](https://i.imgur.com/QIoY307.png)

### Logged in

After logging in, we will see our email address shows on the header and 2 buttons (Post and Logout). If you want to post a new video, simply click Post button. If you finally finish posting, simply click the Logout button if you want to sign out.
![enter image description here](https://i.imgur.com/Q8i4LuW.png)

### Post video

In this page, a form that prompt you to enter your video information.
![enter image description here](https://i.imgur.com/MsAmldU.png)

After entering all of the necessary information, hit Post button.
![enter image description here](https://i.imgur.com/AavKmai.png)
After clicking the Post button, your browser will be redirected back to homepage and the new video that you just posted will be shown.

![enter image description here](https://i.imgur.com/53EPTEd.png)

## Troubleshooting

### Unable to connect mongoDB using nestjs/mongoose locally

- Try to change the MONGO_URI from `mongodb://localhost:27017` to `mongodb://127.0.0.1:27017`
