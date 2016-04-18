# Fresh Jobs Backend

## Explorer Mode

In this assignment you will create a back-end API the "Fresh Jobs" job board.

Below you'll find data models outlining the structure and relationships of the data for the job board. Your job is to create an API endpoint for each of the following tables:

* jobs
* companies
* applications
* tags

Before you begin you will need to create a new database `createdb freshJobs`.

### Migrations

For each data table you will need to create a migration file to create the data table. You can use the command `knex migrate:make jobs` for example, to create the migration file. You can use the [users](/migrations/20151009115505_create_users.js) and [authentication](/migrations/20151009155020_create_authentication.js) migrations (which are already created for you) as a reference.

Once your migrations are created, you can run them (ie. create the database tables) by running the `knex migrate:latest` command. You should not get any errors and you should be able to see the newly created database tables via the PSequel application.

### Models

You will also need to create a **back-end** model for each of the data tables. You will need to create these files manually in the `/models` (not /public/scripts/models) directory. You can use the [users](/models/User.js) and [authentication](/models//Authentication.js) models (which are already created for you) as a reference. Be very careful with pluarlization. By convention database table names are pluralized and models are singularized.

![Fresh Jobs Data Models](/FreshJobsDataModels.png)

### API

Once your migrations and models are created, you need to create an API as a way for the front-end to interact with your data (GET, POST, PUT, DELETE). The easiest way to do this is by using the [bookshelf-api]() module. You will first need to install it with npm and then connect it to a new route within your application. This will involve modifying the [app.js](/app.js) and [routes/api1.js](/routes/api1.js) files.

If this is configured correctly you should be able to run your server with `num run dev` and GET, POST, PUT and DELETE records using Postman. Remember, you must add the header **Accept** with value **application/json** for postman to work properly.

##### What to Submit
* Link:
  * A link to your repo
* Notes:
  * A link to a deployed version of your app on heroku. You can [follow these instructions]() to deploy your app.
  * Your confidence level for this assignment, 0-5. (0 is no confidence, 5 is master)
  * Less than 5? Submit 1 question and 1 answer on Breadcrumbs and include a link to them.
  * 5? Great! Submit 2 answers on Breadcrumbs and include a link to them.
  * Did you complete at least "Explorer Mode"?
  * If no, briefly explain why not.
  * If yes, how far past Explorer did you get?

## Adventurer Mode

Foreign keys allow your models to know about their related models. For example, each `authentication` has exactly one `user` associated with it. Read up on [bookshelf associations](http://bookshelfjs.org/#associations) and modify your models to have the correct associations. If everything is working you should be able to use query parameters within Postman to [query related models](https://github.com/alarner/bookshelf-api#pulling-related-models).

## Epic Mode

Certain API endpoints should not be able to be used unless a user is logged in. Read up on how to [access the logged in user](http://perkframework.com/api/authentication.html#accessing-the-logged-in-user) with Perk and modify your routes to prevent posting to any of the API endpoints unless a user is logged in.
