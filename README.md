# DRIVENT - BACKEND

This is the backend of a white-label app designed for selling events and facilitating talk subscriptions, with the added capability of booking accommodations in partner hotels.

## About

Introducing a web application for easy getting the clients for your events. Key features include:

- User Sign Up
- Secure Login
- Event Subcription
- Ability to sell both In-person and Remote Ticket
- Seamless integration with partner hotels, simplifying the booking process for users across a wide range of options.
- Direct Credit Card Payments
- Capacity Management for event venues.
- Hotel Room Booking Management.
- Users have the flexibility to switch rooms if desired.
- Tracking of subscribed users for each activity.
- Generation of certifications after the event concludes.

## Technologies
The following tools and frameworks were used in the construction of the project:<br>

<p>
  
  [![My Skills](https://skillicons.dev/icons?i=jest,nodejs,ts,postgres,redis,git,express,prisma)](https://skillicons.dev)
  
</p>

## How to run for development

1. Clone this repository
2. Install all dependencies

```bash
npm i
```

3. Create a PostgreSQL database with whatever name you want
4. Configure the `.env.development` file using the `.env.example` file (see "Running application locally or inside docker section" for details)
5. Run all migrations

```bash
npm run dev:migration:run
```

6. Seed db

```bash
npm run dev:seed
```

6. Run the back-end in a development environment:

```bash
npm run dev
```

## How to run tests

1. Follow the steps in the last section
2. Configure the `.env.test` file using the `.env.example` file (see "Running application locally or inside docker" section for details)
3. Run all migrations:

```bash
npm run test:migration:run
```

4. Run test:

```bash
npm run test
```

## Building and starting for production

```bash
npm run build
npm start
```

## Running migrations or generate prisma clients

Before running migrations make sure you have a postgres db running based on `.env.development` or `.env.test` file for each environment. You can start a postgres instance by typing `npm run dev:postgres` or `npm run test:postgres`. The host name is the name of the postgres container inside docker-compose file if you are running the application inside a docker container or localhost if you are running it locally.

You can operate on databases for different environments, but it is necessary to populate correct env variables for each environment first, so in order to perform db operations type the following commands:

- `npm run dev:migration:run` - run migrations for development environment by loading envs from .env.development file. It uses [dotenv-cli](https://github.com/entropitor/dotenv-cli#readme) to load envs from .env.development file.
- `npm run test:migration:run` - the same, but for test environment

- `npm run dev:migration:generate -- --name ATOMIC_OPERATION_NAME` - generate and run migration and prisma client for development environment by loading envs from .env.development file. Replace `ATOMIC_OPERATION_NAME` by the name of the migration you want to generate.

## What to do when add new ENV VARIABLES

There are several things you need to do when you add new ENV VARIABLES:
- Add them to `.env.example` file
- Add them to your local `.env.development` and `.env.test` files
