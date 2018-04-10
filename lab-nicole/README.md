# Google OAUTH

This app allows you to log in to the application using Google OAUTH. 

It utilizes the following npm packages:
  - superagent, dotenv, & express

Google makes a GET request to the route we have created at ```/oauth/google/code```, then we make a POST request to google's API's at ```https://www.googleapis.com/oauth2/v4/token```. Google response with a token, which we use to make another GET request to google at ```https://www.googleapis.com/plus/v1/people/me/openIdConnect```.

Google responds with the user profile, including the following information:
- gender: 'female',
- sub
- name
- given_name
- family_name
- profile
- picture
- email
- email_verified (boolean)
- locale

The application then redirects to the CLIENT_URL which is provided in the .env file.