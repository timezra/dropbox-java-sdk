dropbox-java-sdk
====================================================

This project started life as a fork of the dropbox-java-sdk v1.5.3 (https://www.dropbox.com/developers/reference/sdk) in order to install the Dropbox code into a local Maven repository for use in a Maven Dropbox plugin. None of the main java code has been touched, except for the pom.xml, which had gotten out of synch with the dependencies in the rest of the project; the DropboxAPITest#search method, which sporadically fails because of an assumption about the ordering of returned search results (see https://forums.dropbox.com/topic.php?id=96439&replies=1#post-526540); and the mechanism for setting up and tearing down test data in DropboxAPITest, which does not clean up artifacts uploaded to the Dropbox integration test repository.

System properties for running integration tests
----------------------------------------------------
Note that in order to run the tests for this project, you must go through the process of setting up a Dropbox application specifically for testing the app, then request an oauth access token. You will need to configure a local config/dev.properties file with the following properties in it:

\# This is the app key and secret you get when you setup the Dropbox test app

app_key=&lt;App key&gt;

app_secret=&lt;App secret&gt;

\# This is the oauth key and secret you get from the call to https://api.dropbox.com/1/oauth/access_token

access_key=&lt;oauth_token&gt;

access_secret=&lt;oauth_token_secret&gt;

