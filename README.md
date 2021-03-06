## Clinic Sign In

This is a template for creating a monorepo with a React frontend and a Node.js backend.

## Installation

1. Clone this repo
2. Create a new repo and push the code
3. Login to Heroku and create a new pipeline with a `staging` and `production` api and web service.
4. Add a these buildpacks: https://github.com/timanovsky/subdir-heroku-buildpack, heroku/node.js -- the subdir buildpack needs to come first.
5. Add `PROJECT_PATH=services/server` to the api Heroku env variables and `PROJECT_PATH=services/website` to the react Heroku app.
6. Login to CircleCI and follow your new repo
7. Add `HEROKU_APP_NAME` and `HEROKU_API_KEY` env variables to the new CircleCI project settings. (heroku profile/account settings/ towards the bottom)
8. Use CircleCI to generate an api token and add adjust the environments table below (in this README) to use the new token and the new addresses

## Developing

1. make sure there is a `.env` file at `services/server/.env` -- even if it is empty
2. type `docker-compose up`

This will fire up the Node.js api on port 10020 and the react app on port 10060.

## Important commands

run server tests:

```
docker-compose exec server yarn test
```

reset server test db:

```
docker-compose exec server yarn build
```

## Environments

| Environment | Branch  | URL                                             | CI                                                                                                                                                                                                                      | Documentation |
| ----------- | ------- | ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| Development | develop | https://template-for-zach-staging.herokuapp.com | [![CircleCI](https://circleci.com/gh/briankeane/template-for-zach/tree/develop.svg?style=svg&circle-token=88650b09967067d46fb759f808318edeaf19cd5c)](https://circleci.com/gh/briankeane/template-for-zach/tree/develop) |
| Production  | master  | https://template-for-zach.herokuapp.com         | [![CircleCI](https://circleci.com/gh/briankeane/template-for-zach/tree/master.svg?style=svg&circle-token=88650b09967067d46fb759f808318edeaf19cd5c)](https://circleci.com/gh/briankeane/template-for-zach/tree/master)   |
