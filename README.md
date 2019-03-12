# firebase-mock-api-server
A simple mock API server using [Express.js](https://expressjs.com/) that is hosted on [Firebase](https://firebase.google.com/).

## Why custom mock server
You have full control of what API to define and what data to respond with with minimal coding.

## Show me examples
The APIs are defined via Express and served though Firebase cloud functions. All the API can be found at [functions/index.js](https://github.com/amardeshbd/firebase-mock-api-server/blob/master/functions/index.js) 
and pre-loaded mock responses example can be found at [mock-responses/user.json](https://github.com/amardeshbd/firebase-mock-api-server/blob/master/functions/mock-responses/user.json)

#### Simple GET
https://mock-apis-server.firebaseapp.com/say/hello
#### Capture data from URL
https://mock-apis-server.firebaseapp.com/users/myid
#### POST data to register new account
Success
```
curl -X POST \
  https://mock-apis-server.firebaseapp.com/register \
  -H 'Content-Type: application/json' \
  -d '{"userId": "myusername", "email":"my@email.com", "name": "New User"}'
```

Fail
```
curl -X POST \
  https://mock-apis-server.firebaseapp.com/register \
  -H 'Content-Type: application/json' \
  -d '{"userId": "taken", "email":"existing@email.com", "name": "Existing User"}'
```

> NOTE: You will have to use terminal to execute these curl commands.