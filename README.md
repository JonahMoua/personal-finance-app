# My personal finance

Create your monthly budget.

## Live Demo

[Live Demo](https://fir-app-3e66a.firebaseapp.com)

![Screenshot 1](client/src/screenshots/screenshot1.png)

![Screenshot 2](client/src/screenshots/screenshot2.png)

![Screenshot 3](client/src/screenshots/screenshot3.png)

## Getting Started

Create a firebase account:
[Firebase](https://firebase.google.com/)

- Create a new project and new app

- Create a Cloud firestore database with the following rules:

```
rules_version = '2';
service cloud.firestore {
    match /databases/{database}/documents {
        match /users/{uid}/budgets/{budgetId} {
            allow read, write: if request.auth.uid == uid
        }
        match /users/{uid}/configuration/{docId} {
            allow read, write: if request.auth.uid == uid
        }
    }
}
```

### Prerequisites

- Node 12.14.+
  - [Node](https://nodejs.org/en/)
- Vue cli 4.2.+

  - [Vue cli](https://cli.vuejs.org/guide/installation.html)

- Create .firebaserc file inside client folder

```
{
  "projects": {
    "default": "your_firebase_app"
  }
}
```

- In the client folder create a .env file for firebase project information

  - For this project you need to fill the vairables VUE_APP_FIREBASE_API_KEY, VUE_APP_FIREBASE_AUTH_DOMAIN, VUE_APP_FIREBASE_PROJECT_ID and VUE_APP_FIREBASE_APP_ID.

```
VUE_APP_FIREBASE_API_KEY=YOUR_FIREBASE_API_KEY
VUE_APP_FIREBASE_AUTH_DOMAIN=YOUR_FIREBASE_AUTH_DOMAIN
VUE_APP_FIREBASE_DATABASE_URL=
VUE_APP_FIREBASE_PROJECT_ID=YOUR_FIREBASE_PROJECT_ID
VUE_APP_FIREBASE_STORAGE_BUCKET=
VUE_APP_FIREBASE_MESSAGING_SENDER_ID=
VUE_APP_FIREBASE_APP_ID=YOUR_FIREBASE_APP_ID
```

### Installing

# In the client folder

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

## Deployment

```
cd client
npm run build
firebase deploy
```

## Built With

- [Vue.js](https://vuejs.org/) - The javascript framework
- [Firebase](https://firebase.google.com/) - Authentication and real time database
- [Vuetify](https://vuetifyjs.com) - Vue UI Library with beautifully handcrafted Material Components
- [Vue-Chartjs](https://vue-chartjs.org/) - Easy and beautiful charts with Chart.js and Vue.js


## Acknowledgments

- A special thanks to my wife for supporting me
