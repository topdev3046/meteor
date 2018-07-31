# Zirra Web

This is the repo for the main Zirra website.

## Dev Process and Versioning

For development we follow [this process](http://nvie.com/posts/a-successful-git-branching-model).

We version according to [semver](http://semver.org/), and track the version in tags. To see where we're at use:

`git describe --tags`

## Configuration

If this the first time you're starting webapp, run `meteor npm install` from webapp root.
In case of any "missing module" in the future try `meteor npm update`

We follow the standard [Meteor configuration](http://docs.meteor.com/#/full/meteor_settings) approach.

If you are running in development mode, you can put your configs in `settings.json` file and run meteor with `meteor --settings settings.json`.
See `settings.json.example` file for an example of the configuration file and supported config values.

If you are running in production mode, you can either either export the entire JSON as enviornment variable using `export METEOR_SETTINGS={JSON from settings.json}`,
or export the file using `export METEOR_SETTINGS=$(cat settings.json)`.

In addition to settings in `settings.json` there's a number of Meteor settings that can be set only through environment variables:

1. MAIL\_URL. This is the smtp address of the email server.
2. HTTP\_FORWARDED\_COUNT. Number of proxies your server runs behind. Typical value is 0.
3. MONGO\_URL. Set this variable if you want to connect to a remote DB. Don't set if you are running your local Mongo DB.
4. MONGO\_OPLOG\_URL. Set this variable if you want to connect to a remote DB. Don't set if you are running your local Mongo DB.
5. ELASTICSEARCH\_HOSTS. ElasticSearch connection string. Separate with commas if more that one host.
6. ELASTICSEARCH\_INDEX\_NAME. To keep development and production elasticsearch indexes separated. Defaults as "development" if not set. Required in production.
7. NODE\_ENV. Node environment. "production" and "development" are recognized, everything else is the same as not setting this variable.
8. ROOT\_URL. Should be set to the URL that clients will be accessing your application with. Required in production, otherwise optional.

## Testing
Meteor testing documentation: http://guide.meteor.com/testing.html

To make sure Meteor recognizes tests as tests they should go to `/test` folder and have `.tests.` (or `.test.`) suffix, for example `/test/lambda.tests.js`.

To test locally you need to run `meteor npm test`, wait until Meteor spins up and open localhost:3000 (or however you configured meteor) in browser.
# meteor
