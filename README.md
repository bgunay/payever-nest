# PAYEVER | BACK-END ASSIGNMENT

## Content

[1. Getting Started](#getting-started)  
&emsp;[1.1 Requirements](#requirements)  
[2. API Resources](#api-resources)  
&emsp;[2.1 Endpoints](#endpoints)  
[3. Automated Tests](#automated-tests)  
[4. Tech Stack](#tech-stack)

### Requirements

You need to install the following technologies and run them locally:

- <https://nodejs.org/en/download/> - Node.js
- <https://www.mongodb.com/try/download/community> - MongoDB
- Used docker for mongo, to Run docker-compose.yml

```bash
docker compose up
```

PS.: For MongoDB, you can use its Atlas service so you don't have to install it on your machine. You can access it on <https://www.mongodb.com/atlas/database>.

- To build application

```bash
npm run build
```

- To run application

```bash
npm run start
```

- To debug application

```
npm run start:debug
```

## Github address

```bash
git clone https://github.com/bgunay/pe-assignment.git
```

- Mailer section Commented in Code ( user.service.ts),

```
    // Send email
    /*
    await this.mailerService.sendMail({
      to: createdUser.email,
      subject: 'Welcome to our app!',
      //template: './welcome',
      context: { name: createdUser.first_name },
    });
    */
```

- POSTMAN Collection file for making HTTP Rest requests:

```
  payever_userapi.postman_collection.json

```

- For make it work. Uncomment and complete missing values in .env file, like below:

```
MailerModule.forRoot({
   transport: {
        host: "smtp.gmail.com",
        port: "465",
        secure: true,
        auth: {
            user: "your_gmail_email",
            pass: "your_gmail_app_password"
        }
    }
})
```

- if you do not configure mailer values, you will get errors like : ERROR [MailerService] Error occurred while verifying the transporter}: getaddrinfo ENOTFOUND <YOUR-MAILER-HOST>

\*\* Steps from start lookup steps.txt

Alternatively, if you are reading this README after downloading the .zip file, you already have all the necessary files in the root folder so you can move along.

To keep using the dependencies in the containers, stop the application container (only the 'app' one) and connect to the other services by modifying the .env.example file as instructed in the file. You can also connect to the dependencies locally on your machine if you want to (MongoDB and RabbitMQ), but you will also have to modify their variable accordingly.

1. Open the _'.env.example'_ file and follow the instructions in it.

2. After setting up your environment variables, run `npm install` to install all dependencies.

3. `npm run start:dev` will start up the application using a nest.js script, running on port 3000. From this point on, you can starting sending request or running tests.

## API Resources

You can use an http client to send requests to this application, such as _Insomnia_, _Postman_ or even the _Thunder Client_ extension in VS Code.

### Endpoints

1. POST /api/users
2. GET /api/user/{userId}
3. GET /api/user/{userId}/avatar
4. DELETE /api/user/{userId}/avatar

## Automated Tests

You can find test files in this applications that were written to verify the integrity and efficiency of the code and its funcionalities.

The Unit Test files for each code file can be found right next to it, in the same directory. The Integration Tests consist of a single file called '_users-integration.spec.ts_' inside the '_test_' folder.

In order to run the tests, in any environment you are, just run:

```bash
npm run test
```

_npm run test:cov_ will give you the coverage of unit tests, which for this project is only missing the ones for the _users.service.ts_ file methods.

## Tech Stack

- [Node.js](https://nodejs.org/en/)
- [Nest.js](https://nestjs.com/)
- [MongoDB](https://www.mongodb.com/)
- [Typescript](https://www.typescriptlang.org/)
- [RabbitMQ](https://www.rabbitmq.com/)
