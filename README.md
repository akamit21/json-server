# Deployment `JSON Server` to `Heroku`

> Instructions how to deploy the full fake REST API [json-server](https://github.com/typicode/json-server) to heroku. Should only be used in development purpose but can act as a simpler database for smaller applications.

## Create your database

1 . Clone this repo to anywhere on your computer.

```bash
git clone https://github.com/akamit21/json-server.git
```

2 . Change `db.json` to **your own content** according to the [`json-server example`](https://github.com/typicode/json-server#example) and then `commit` your changes to git.

_this example will create `/posts` route , each resource will have `id`, `title` and `content`. `id` will auto increment!_

```json
{
  "users": [
    {
      "id": 1,
      "name": "Full name!",
      "email": "name@email.com"
    }
  ],
  "posts": [
    {
      "id": 0,
      "title": "First post!",
      "content": "My first content!"
    }
  ]
}
```

---

## Deploy to **Heroku**

Heroku is a free hosting service for hosting small projects. Easy setup and deploy from the command line via _git_.

---

### Install Heroku

1 . [Create your database](#create-your-database)

2 . Create an account on <br/>[https://heroku.com](https://heroku.com)

3 . Install the Heroku CLI on your computer: <br/>[https://devcenter.heroku.com/articles/heroku-cli](https://devcenter.heroku.com/articles/heroku-cli)

4 . Connect the Heroku CLI to your account by writing the following command in your terminal and follow the instructions on the command line:

```bash
heroku login
```

5 . Then create a remote heroku project, kinda like creating a git repository on GitHub. This will create a project on Heroku with a random name. If you want to name your app you have to supply your own name like `heroku create project-name`:

```bash
heroku create `project name`
```

6 . Push your app to **Heroku** (you will see a wall of code)

```bash
git push heroku master
```

7 . Visit your newly create app by opening it via heroku:

```bash
heroku open
```

8 . For debugging if something went wrong:

```bash
heroku logs --tail
```

---

#### How it works

Heroku will look for a startup-script, this is by default `npm start` so make sure you have that in your `package.json` (assuming your script is called `server.js`):

```json
 "scripts": {
    "start" : "node server.js"
 }
```

You also have to make changes to the port, you can't hardcode a dev-port. But you can reference herokus port. So the code will have the following:

```js
const port = process.env.PORT || port_number;
```

---
