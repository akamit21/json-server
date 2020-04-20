# Fake `JSON Server`

> If you want to use full fake REST API [json-server](https://github.com/typicode/json-server) that can be used in development purpose as a simpler database for smaller applications. You can use this repo for that.

## How to create your own fake REST API's using json server

1 . Clone this repo on your computer.

```bash
$ git clone https://github.com/akamit21/json-server.git
```

2 . Add your own content to `db.json` and then `commit` your changes to git.

_this example will create `/users` and `/posts` route , each resource will have their own data depending on what are adding o it. In the second example you can see that I have added {`id`, `name` and `email`} to users array and {`id`, `title` and `content`} to posts array. In both cases `id` will auto increment!_

```json
{
  "users": [],
  "posts": []
}
```

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

> In both cases data's are dummy you can have data of your own choice.

---

## Deploying it to **Heroku**

Heroku is a free hosting service for hosting small projects. Easy setup and deploy from the command line via _git_.

---

### Install Heroku

1 . [Create your server](https://github.com/akamit21/json-server.git)

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

6 . Open your project folder by writing the following command in your terminal and follow the instructions on the command line:

```bash
cd `project name`
```

7 . Push your app to **Heroku** (you will see a wall of code)

```bash
git push heroku master
```

8 . Visit your newly create app by opening it via heroku:

```bash
heroku open
```

9 . For debugging if something went wrong:

```bash
heroku logs --tail
```

---

## Run it locally on your PC

Heroku will look for a startup-script, this is by default `npm start` so make sure you have that in your `package.json` (assuming your script is called `server.js`):

1 . Clone repository

```bash
$ git clone https://github.com/akamit21/json-server.git
$ cd json-server
```

2 . Run `npm install` npm install will install all modules listed as dependencies in [package.json](package.json) file.

```bash
$ npm install
```

3 . Run `npm run start` It will run application in http://localhost:3000

```bash
$ npm run start
$ npm run dev `if you want to use nodemon`
```

```json
 "scripts": {
    "start" : "node server.js",
    "dev" : "nodemon server.js"
 }
```

4 . You also have to make changes to the port, you can't hardcode a dev-port.

```js
const port = process.env.PORT || port_number;
```

---

### Contribute

Contributions are always welcome!

#### Amit Kumar

> **Twitter :** @Amitaldo

> **Credit :** [Jesper Orb](https://github.com/jesperorb)
