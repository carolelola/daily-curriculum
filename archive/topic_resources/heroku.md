## Deploying to Heroku

Heroku is a cloud platform that allows you to deploy your web applications without needing a server. Let's take our practice Sinatra practice and deploy it using Heroku.

Heroku uses git, so first we'll make sure our project is using git:
```bash
git status
```

If this command results in a message like `fatal: Not a git repository (or any of the parent directories): .git` then we'll need to setup git for our project:
```bash
git init
git add .
git commit -m "initial commit"
```

This is the normal git flow of initializing a dir, adding, and committing all of the code.

Heroku is the service that will actually host our application. We will use the [Heroku Toolbelt](https://toolbelt.heroku.com). First we'll use a command that will create a repo on Heroku's server for us to push our application into.

```bash
heroku create kari-sinatra
```

Use a unique name where I used `kari-sinatra`, if you cannot think of a name leave it empty an Heroku will come up with a random name for you (this can be changed later). You should see out put that looks similar to:

```bash
Creating kari-sinatra... done, stack is cedar
http://kari-sinatra.herokuapp.com/ | git@heroku.com:kari-sinatra.git
Git remote heroku added
```

The `heroku create` command creates the repo on Heroku and also creates the git remote link on our computer.

Note: The git remote link is automatically called `heroku`, where in the past we've named this link `origin`.

Now push your app to Heroku:
```bash
git push heroku <YOUR BRANCH NAME>:master
```

You should see a bunch of output for about a minute. Heroku is receiving your application and deploying it. Now your app is available on the internet. Navigate to "http://YOURAPPNAME.herokuapp.com" where YOURAPPNAME is the name you gave to heroku, `kari-sinatra` in my case, so the full url is `http://kari-sinatra.herokuapp.com`. TADA!

Now if you log on to your Heroku account online, you will see your app listed under the name you gave it. 
