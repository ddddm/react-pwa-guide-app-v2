# react-pwa-guide-kit

> This is a guide kit is designed to show how to make a Progressive Web App(PWA) and PWA features in React.js development environments. Customized and opinionated tools and build process are optimized to achive high-performed web application which is audited by strict auditor, [Lighthouse](https://github.com/GoogleChrome/lighthouse). Moreover, this guide kit is also backed by Firebase for hosting, realtime database, and also push notification.

# Demo

[Demo](https://react-pwa-hello-world.firebaseapp.com/#/) is working on firebase hosting. Please take a look.

# Features

- **Material Design and AppShell**: Responsive, fit any form factor, desktop but the first is mobile. AppShell architecture implemented wearing material design got bressed by [material-ui.com](https://material-ui.com)
- **ES6 via Babel**: You can use ES6 feature with same babel-preset to [create-react-app](https://github.com/facebookincubator/create-react-app) and dynamic module importing
- **Webpack 2**
  - **Remarkable configurations**: Webpack configuration file has been written in configurable, optimzied and easy settings
  - **Developing Progressive Web App**: You can check them of optimized bundling for PWA including code-splitting, multiple chunk and [preload](https://www.npmjs.com/package/preload-webpack-plugin). As developing, reloading changes instantly by webpack-dev-server, also it is working well with [service worker](https://github.com/ragingwind/sw-precache-webpack-dev-plugin)
- **HTTPS**: Deploying to Firebase Hosting to run perfectly on HTTPS with PWA features
- **Web Push**: Web Push demo also is branded at this app by Firebase Push Messaging
- **Service Worker**: Generating service worker scripts is completly intergrated in build process with Webpack 2 and plugins
- **Web Manifest**: Have a look how to installable webapp work by Web Manifest
- **Realtime Database**: We featured firebase to show PWA how to work with fetched data and cached data via service worker
- **Server Side Rendering**: Deprecated in favour of using code splitting and react-router 4 ~~Presenting intial page in short time is an important issue. This guide kit includes
simple server side code for demonstration. Buidling PWA for Server Side Rendering version landed You can take a look what is different between both of versions~~
- **React Lite Support**: To achieve minimal vundle size at initializing time of the app, we support for building with react-lite. Simple, you can get another version of app running on `react-lite` if you could add the additional argument on build command when you build `-- --env.lite`

# Getting Started

## Setup

To use filrebase cli tool, you must setup firelbase cli and then logged into firebase by `firebase login`. To do this please refer to [firebase cli guide](https://firebase.google.com/docs/cli/). And then you need to create a new project on firebase and get the intialize codes from firebase, which are API_KEY, MESSAGING_SENDER_ID, DATABASE_URL, to save at .env. If you're not familiar with a brand new filrebase? you can have a look for [official guide](https://firebase.google.com/docs/web/setup)

```sh
# install dependencies
yarn install

# firebase init, input with following answers
# select hosting only
# select your project or create one
# input build for public directory
# answer no for configuration as a single-page app
firebase init

# update values in .env with the intialize codes from firebase
# and then rename .env.example in compliance with loading env as build
mv .env.example .env
```

## Build

We support three versions of build, production, development(debug) and ssr. All of build files will be in `./build`

```sh
# build in production
yarn build

# build in debug
yarn build:debug
```

## Run PWA on Server

```sh
# starting app by webpack-dev-server, no-ssr
yarn start
```

## Deployment

You need to check that configuration again. You must have a project on firebase, this project have the suitable settings for firebase generated by fireblase cli and .env file must be exist with the initialize code from firebase

```sh
# deploy to firebase
yarn deploy
```

## Testing Firebase Cloud Messaging for Push

This guide-kit use Push Messaging built on top of Firebase Cloud Messaging. `Notificaiotn` page will show you peer token to send push message to current opened tab. To do this, [`fcm-cli`](https://github.com/ragingwind/fcm-cli) is a really simple and powerful tool for testing FCM on terminal. [This video will cover how to deal with fcm-cli and FCM](https://goo.gl/Jx4poC) (*Korean*)

# Lighthouse Audit Result

Audit result is [here](https://goo.gl/2ur4rl), you can review the result with Lighthouse [viewer](https://googlechrome.github.io/lighthouse/viewer/)

![](https://cloud.githubusercontent.com/assets/124117/23695353/0fa9face-0422-11e7-89a1-da7d33e17855.png)

# License

MIT @ CodeBusiking
