please do not forget to Set AWS configurations in environment variables:

export AWS_ACCESS_KEY_ID="Your AWS Access Key ID"
export AWS_SECRET_ACCESS_KEY="Your AWS Secret Access Key"
export AWS_REGION="us-east-1"

I created a Javascript Class "Dynamo" to handled most of the util functions. All the functions are built from scratch.

Only used dynamoose.js in the unit test and test helper. I am capable of using dynamoose.js to finish the entire project.

Created an Extra Counter database to handle the User_id count.

# Indorse

This repo has the code lambda functions for API service.

## Problem Statement

### Scope of Assignment

- Create an API service in AWS that will accept data from incoming connections and insert / update in AWS Dynamo DB / Cloud hosted Mongo DB

- Create AWS Lambda module(s) in NodeJS 8.x to complete all the features.

### Basic feature of the application should include:

- Lambda to create user profile. User profile will include user_id, name, email, mobile number, address, company, title

- Lambda to update user profile when the email or mobile number matches in the incoming api request

- Lambda to update user interests  including sports, food, media and more. Come up with relevant fields that can be added to user profile and add the same as parameter for the function

- All data should go to AWS Dynamo DB

- Configure AWS API gateway and create relevant APIs for create and update user records. Configure security for the API and configure rate limiting for the APIs

- Use async/await calls in the Node JS functions

- Add relevant code comments and modularise the code properly. Create more than one Lambda wherever required and make inter Lambda calls if required

- Write an automated test for this lambda


## Run the project locally

Run the following command and the APIs will the available locally for testing and development.

```closure
unzip the folder
cd indorse-backend-master
npm install
npm run offline
```

## Deploy Project

Run the following command once the setup is working locally on your system.

```closure
npm run deploy
```

## Lint Project

```closure
npm run lint  # for cheking the lint error
npm run lint-fix # for fixing the minor lint error
```

## Run Tests

Used [Mocha](https://mochajs.org/)

```closure
npm run test  # for running tests
```

## Generate Documentation

Used [API Docs](http://apidocjs.com/)

```closure
npm run generate-docs  # for generating documentation
```

## Basic Feature

- [X] Lambda to create user profile. User profile will include user_id, name, email, mobile number, address, company, title
- [X] Lambda to update user profile when the email or mobile number matches in the incoming api request
- [X] Lambda to update user interests  including sports, food, media and more. Come up with relevant fields that can be added to user profile and add the same as parameter for the function
- [X] All data should go to AWS Dynamo DB / Mongo Cloud Hosted Server
- [X] Configure AWS API gateway and create relevant APIs for create and update user records. Configure security for the API and configure rate limiting for the APIs
- [X] Use async/await calls in the Node JS functions
- [X] Add relevant code comments and modularise the code properly. Create more than one Lambda wherever required and make inter Lambda calls if required
- [X] Write an automated test for this lambda

## Deployed Information

``` closure
Service Information
service: indorse-backend
stage: dev
region: us-east-1
stack: indorse-backend-dev
api keys:
  None
endpoints:
  GET - https://m0mlmbw42g.execute-api.us-east-1.amazonaws.com/dev/get
  POST - https://m0mlmbw42g.execute-api.us-east-1.amazonaws.com/dev/create-profile
  POST - https://m0mlmbw42g.execute-api.us-east-1.amazonaws.com/dev/update-profile
  POST - https://m0mlmbw42g.execute-api.us-east-1.amazonaws.com/dev/update-interest
functions:
  get: indorse-backend-dev-get
  createProfile: indorse-backend-dev-createProfile
  updateProfile: indorse-backend-dev-updateProfile
  updateInterest: indorse-backend-dev-updateInterest
```

## Postman Collections

For Localhost: [https://www.getpostman.com/collections/d68d6ba1212d8d1c5c05](https://www.getpostman.com/collections/d68d6ba1212d8d1c5c05)

For Deployed Version: [https://www.getpostman.com/collections/4e63dc0d46edea1867f3](https://www.getpostman.com/collections/4e63dc0d46edea1867f3)

## Documentation

Docs reside in ./docs folder. You can either host them or view index.html in your browser.

Note: For running the npm run deploy command you need initialise serverless with the proper credentials of user with access to lambda, api_gateway, IAM and cloudfront.
