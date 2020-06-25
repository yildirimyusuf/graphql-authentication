# GraphQL Authentication with JWT

* Graphql
* Apollo
* Babel
* Jest

### Prerequisites

* Node v10.4.1 or above
* Mongo database
* Google+ API Setup

### Installing

Install dependencies

```
cd graphql-authentication
npm install
```

Setup the config in /src/setup/config/config.example.json:
* Rename the file to 'config.json'
* Add your variables

```
/src/setup/config/config.json
```

Run in the development environment

```
npm run dev
```

To test if the authentication is working open any of the following routes:
* Google - /auth/google

They should redirect you to the callback with the user data and token; A cookie is now set with the token

## Running the tests

If the above is done correctly running the tests should be as simple as:

```
npm run test
```

Make sure to the test variables in the config file /src/setup/config/config.json are setup correctly

### Running coding style tests

To clean up the code with eslint run

```
npm run eslint
```

## Deployment

The config.json file only defines variables for the 'development' and 'test' environments.

You need to change the callback routes to redirect to your client in /setup/routes/auth.js

```
// Replace this
// res.send(resSchema(req.user, res.statusCode))

// With
res.redirect(process.env.CLIENT_ORIGIN)
```

Build project
```
npm run build
```

Start server
```
npm start
```
