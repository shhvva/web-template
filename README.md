# Web template - Nextjs Prisma PostgreSQL Kinde Docker

This is a web template using Next 15, Kinde, and PostgreSQL using Prisma and Docker.

This helps anyone get a jump start on building a website by skipping the setup process. I have set up the next application with authentication and user management using kinde, It also helps in setting up a local PostgreSQL database using docker.

## Setting up kinde

First, Run the below code to install all the necessary packages and modules

```bash
npm install
```

Create an account in [`Kinde`](https://docs.kinde.com/developer-tools/sdks/backend/nextjs-sdk/) and start a new project/business

Select Nextjs as tech stack

Copy and paste the env. local file

## Starting the database

Run the command to start an instance of PostgreSQL

```bash
$ docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```
This will start a database. The default Postgres user and database are created in the entry point with initdb.

In the .env file change the POSTGRES_PASSWORD if you changed it in the above command

The .env file should not contain the Postgres URL since the next commits the .env file. We should manually add it to the .gitignore file.

## Setup the schema

This code has already set Prisma and by initializing and installing Prisma and Prisma client 

You can find the schema in `\webtemplate\prisma\schema.prisma`

Every time you change the schema you have to migrate the dev and generate a client

Prima automatically generates a client every time you migrate, you can do that using

```bash
npx prisma migrate dev
```

Here are [the Prisma docs](https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch/relational-databases/connect-your-database-node-postgresql)

## Start the local development

Run this code to start the website

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

Run this to manage the database

```bash
npx prisma studio
```

Open [http://localhost:5555](http://localhost:5555) with your browser to see the result.

You can start editing the page by modifying `app/page.js`. The page auto-updates as you edit the file.

Feel free to raise issues and contribute to this template

Check the package.json file to see the versions

Happy coding