# MyRecipes sample application

Based on the "Professional Ruby on Rails Developer with Rails 5" course on Udemy.

## Getting started

First of all, do you have ruby v2.75 and rails v6.1.5 installed with postgres?
IMPORTANT: Remember the password you created! You will need this password later when setting up database credentials.

- Rails install for Windows 10: https://gorails.com/setup/windows/10
- Rails install for macOS: https://gorails.com/setup/osx/12-monterey

Do you have yarn installed? If not, install that too (version of yarn doesn't matter):

- Yarn install: https://linuxize.com/post/how-to-install-yarn-on-ubuntu-20-04/

---

IMPORTANT: Before proceeding, make sure that `ruby -v` returns `2.7.5` and `rails -v` returns `6.1.5`.

---

To get started with the app, clone the repo and `cd` into the directory:

```
$ git clone https://github.com/coderdave/myrecipes.git
$ cd myrecipes
$ git checkout initial
```

---

IMPORTANT: Switch to the `initial` branch. You will branch off from here to do your work for the Udemy course.

---

After switching to the `initial` branch, install the needed gems:

```
$ gem install bundler
$ bundle install
```

Install JavaScript dependencies:

```
$ npm install
```

Next, your local postgres database is expecting a password. If you want, check out the `database.yml` file for details on how rails connects to postgres. To set up credentials for the development database, run the following command (on mac):

```
$ EDITOR='code --wait' rails credentials:edit --environment development
```

For windows, run the following command

```
EDITOR="code --wait" rails credentials:edit -e development
```

VS Code will open to the credentials configuration file for development. Now insert the following with the password you set for postgres when you installed it.

```
pg:
  db_password: your_password
```

Save and close the file. Then, to set up credentials for the test database, run the following command on a mac:

```
$ EDITOR='code --wait' rails credentials:edit --environment test
```

For windows, run the following command:

```
EDITOR="code --wait" rails credentials:edit -e test
```

Again, insert the same information you entered for the development database, then save and close the file.

```
pg:
  db_password: your_password
```

After setting up credentials, create the database:

```
$ rails db:create
```

Finally, run the test suite to verify that everything is working correctly:

```
$ rails test
```

If the test suite passes, you'll be ready to run the app in a local server:

```
$ rails server
```

Open up your favorite browser (I hope it's Chrome!) and go to:

```
http://localhost:3000/
```

Create your own branch and start the Udemy course!
