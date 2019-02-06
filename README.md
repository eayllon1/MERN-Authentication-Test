# MERN Authentication Test


## 1 | Description

Modular authentication application made to isolate bugs with authentication,
and have one working authentication system to compare other apps implementing this protocol.

Authentication system uses MongoDB, Node.js, Express.js, React, and React-Native (MERN).


## 2 | Roadmap

### 2.1 Minimal Viable Product (MVP)

**Status:** _Complete_

Backend
- [x] Add MongoDB
  - [x] Create User Schema
  - [x] Ability to save User objects to the database
  - [x] Hash user passwords before saving credentials to the database
- [x] Add JsonWebTokens (JWT)
  - [x] Create and deliver token to the Client based on credentials
  - [x] Read token, compare to credentials on database
- [x] Create protected API routes  
  - [x] Create middleware the checks JWT

Frontend
- [x] Create a form that saves values to state
- [x] Send user credentials to server with POST method
- [x] Save JWT from Server
  - [x] JWT saved to Local Storage on React and React-native
  - [x] Local storage accessed, sent to server to verify authorization
  - [x] Working access to protected routes on Client and Server
- [x] Create a protected route
  - [x] Create a route that holds protected content
  - [x] Create middleware that redirects when server returns unauthorized

Currently, the app can create a new user with an email and password, redirect that user to the login page, then login to redirect to the restricted section. Passwords are salted and hashed before being saved to the database. The server will return an error on the given situations, which will be shown to the user on the client:
* Mismatching passwords
* Creating an account that has already been created
* Attempting to submit with an empty password field
* Attempting to submit with an empty email field
* Incorrect password for a given email on login

### 2.2 Next level missing features

**Status**: In Progress

- [ ] Logout system
  - [ ] Frontend logout button inside restricted sections
  - [ ] Logout button triggering logout procedure
- [ ] Passport.js integration
- [ ] Add 0Auth for social logins
  - [ ] Change User Schema for local and social logins
- [ ] Create user roles
  - [ ] Create restricted sections based on user role (No account, Free account, Premium account)
  - [ ] Add roles to user schema
  - [ ] Create system to test roles
- [ ] Verify accounts with Email verification

## 3 | Getting Started

### 3.1 Installing

Install dependencies in both `./frontend` and `./backend`

```
npm install || yarn
```

Authentication requires MongoDB to be installed on your system. MongoDB can be installed with [HomeBrew on Mac](https://treehouse.github.io/installation-guides/mac/mongo-mac.html)

In `./backend` create a new file `variables.env`.

Add a secret key to `variables.env`.

```
AUTH_SECRET_KEY = "Secret Key"
```

And add your mongodb uri with your credentials in `variables.env`:

```
MONGO_URI = "Mongo uri with credentials"
```

### 3.2 Running

You can run as a web app, mobile app, or desktop app.

#### Running the Backend

You must run the backend first. The backend requires MongoD to be running first.

In `./backend`:

Begin MongoD.

```
mongod
```

Then run the server

```
npm run dev || yarn dev || npm run start || yarn start
```

Running the script `dev` will use `nodemon` which restarts the server upon
changes in code.

The back-end will be running in localhost:4000 with current settings.

#### Running the Frontend

The front-end will run in localhost:3000 with current settings.

In `./frontend`:


For Web:

```
npm run web || yarn web
```

For Mobile:

```
npm run start || yarn start || exp start
```

For Desktop:

```
npm run desktop || yarn desktop
```
