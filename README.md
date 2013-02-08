This project started life as a fork of the dropbox-java-sdk v1.5.3 (https://www.dropbox.com/developers/reference/sdk) in order to install push the dropbox code into a local Maven repository for use in a Maven Dropbox plugin. None of the main java code has been touched, except for the pom.xml, which had gotten out of synch with the dependencies in the rest of the project and the DropboxAPITest#search method, which sporadically fails because of an assumption about the ordering of returned search results (see https://forums.dropbox.com/topic.php?id=96439&replies=1#post-526540).
Note that in order to run the tests for this project, you must go through the process of setting up a Dropbox application specifically for testing the app, then request an oauth access token. You will need to configure a local config/dev.properties file with the following properties in it:

# This is the app key and secret you get when you setup the Dropbox test app
app_key=<App key>
app_secret=<App secret>

# This is the oauth key and secret you get from the call to https://api.dropbox.com/1/oauth/access_token
access_key=<oauth_token>
access_secret=<oauth_token_secret>

Note also that, if the size of your Dropbox is limited like mine, you must clean out the folder of the Dropbox SDK testing application because the tests themselves do not currently clean up after themselves.
