# Discretion App

Discretion is a full-stack application that allows users to make anonymised posts.

This application has 3 key elements:

- An API that allows for the creation of user accounts, and allows users to view, create and delete posts
- A database storing data on users, their login session tokens, and posts
- A front-end that leverages the API routes to allow:
  - The registering, logging in and logging out of users
    - Login session tokens are created when the user logs in, and deleted when the user logs out
  - The creation, viewing and deletion of posts
    - Posts can only be viewed by users with a login session token
    - Posts can only be deleted by the post author or an admin

## Setup

1. Clone the repository and `cd` into the `api` directory:

   ```sh
   git clone git@github.com:nine96as/02_auth_exercise.git && cd 02_auth_exercise && cd api
   ```

2. Install required `npm` dependencies:

   ```sh
   npm install #install dependencies from package.json
   ```

3. Complete the steps in the **Configuration** section, then run the API with:

   ```sh
   npm run dev #nodemon listens for file changes
   ```

   > **Note**: The `dev` script will run the API with [nodemon](https://nodemon.io), which will automatically restart the API when changes are made to the source code.

4. Go to http://localhost:3000 to access the API

5. `cd` into the `client` directory:

   ```sh
   cd ../client
   ```

6. Install required `npm` dependencies:

   ```sh
   npm install #install dependencies from package.json
   ```

7. Run the front-end with:

   ```sh
   npm run start
   ```

## Configuration

The API requires:

- A `DB_URL` to execute the necessary SQL queries to ensure the API's operation
- A `PORT` to deploy the API with (`3000` will be used)
- A `BCRYPT_SALT_ROUNDS` value to provide the hashing level required for the user password (`12` will be used)

---

1. Fetch the `DB_URL` by creating a database instance, [using this guide](https://www.elephantsql.com/docs/index.html), where [ElephantSQL](https://www.elephantsql.com/) is used as the database provider

2. Create a `.env` file within the `api` directory, and fill it in as shown below:

   ```env
   DB_URL=postgres://...
   PORT=3000
   BCRYPT_SALT_ROUNDS=12
   ```
