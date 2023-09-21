<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master" target="_blank"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#9" alt="Coverage" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

## Description
This is a login authentication project with routes for user creation, token refresh, and a protected route with JWT (JSON Web Tokens) guard that fetches users from the database. The API is built using Nest.js and TypeScript and utilizes the class-validator library for request body validation. In addition, the project employs bcrypt for password protection. The project is structured into three modules: user, auth, and within the auth module, there is a guards layer that handles both access tokens and refresh tokens.


## How to run the app
1. Create an .env file that has:
* DATABASE_URL for dev.db location for prisma
* jwtSecretKey for tokens
* jwtRefreshTokenKey for refresh tokens

2. Run the application:

```bash
$ npm install

$ npm run start
```

## Routes
This app runs on port 8000.

POST - `/auth/register`
```
{
	"name": "user",
	"email": "user@gmail.com",
	"password": "pass"
}
```
POST - `/auth/login`
```
{
{
	"username": "user@gmail.com",
	"password": "pass"
}
}
```
It should return the tokens for access and refresh.

POST - `/auth/refresh`
This is the route to refresh your tokens. You should pass your Refresh Token in the Authorization header:
  <div class="center-image">
    <img src="https://github.com/normyee/nestjs-authentication-jwt/assets/63208510/3b3f448f-bf71-48e3-afe3-01f44d5f7ace" alt="Image">
  </div>
  It should return an Access Token refreshed and a new Refresh Token.<br></br>

GET - `/user/:id` *THIS ROUTE IS PROTECTED BY JWT GUARD*</br>
This is the GET route for this app. You should provide the user's ID to retrieve information. However, to access this route, you must include the bearer token since it is protected by the JWT guard:
  <div class="center-image">
    <img src="https://github.com/normyee/nestjs-authentication-jwt/assets/63208510/5a11ca0f-9334-4cd3-a10c-5c3c662c6202" alt="Image">
  </div>

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://kamilmysliwiec.com)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](LICENSE).
