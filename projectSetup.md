# Setting up and Deploying New Rails Project with Postgres
This project was created following the Odin Project's [Rails set up guide](https://www.theodinproject.com/lessons/ruby-on-rails-installing-rails)
<br>
<br>

## Step 1: Creating Project
Create an MVC rails app using `rails new <app name>`
<br>
<br>

## Step 2: Scaffold the first table
Create your first basic table using the `generate scaffold` command:
```
rails generate scaffold <model name> <column Name>:<data type>
```
Use `<column Name>:<data type>` as many times as needed to create all the necessary columns for creating a table. Each seperate column declaration seperated by a space character.
<br>
<br>

## Step 3: Test that the project works
Run `rails server` then go onto `http://localhost:3000/<model name>` to see the main view for the model. Test out the CRUD functionality.
<br>
<br>

## Step 4: Host on Github
Add the project to a GitHub repo to be used later on Heroku.
<br>
<br>

## Step 5: Create Heroku App
First create the app: `heroku create`<br>
Then run `git remote` and check that Heroku is listed.
<br>
<br>

## Step 6: Set up Gemfile for deployment
Open the `Gemfile` and replace `gem 'sqlite3'` with:
```ruby
group :development, :test do
 gem 'sqlite3'
end

group :production do
  gem 'pg'
end
```
<br>
<br>

## Step 7: Install Gems
`bundle config set --local without production` then `bundle install`
<br>
<br>

## Step 8: Push to remotes
Add and commit, then push both to GitHub (`git push`) and to the Heroku repo: <br>
```
git push heroku main
```
<br>
<br>

## Step 9: Migrate the DB on Heroku
Migrate the database so that we a DB to work with on the live server:
```
heroku run rails db:migrate
```
<br>
<br>

## Step 10: Check the App is working
Open the app in the browser by running `heroku open`

