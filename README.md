# RESTful API with Node.js, Express, and Postgres
---

Create, read, update, delete in a Node.js app with an Express server and Postgres database.

## Database

```bash
brew install postgresql
brew services start postgresql
psql postgres
```

```sql
CREATE ROLE postgres WITH LOGIN PASSWORD 'password';
ALTER ROLE postgres CREATEDB;
CREATE DATABASE banco;
GRANT ALL PRIVILEGES ON DATABASE banco TO postgres;
```

```bash
psql -d banco -U me
```

```sql
CREATE TABLE users (
  ID SERIAL PRIMARY KEY,
  name VARCHAR(30),
  email VARCHAR(30)
);

INSERT INTO users (name, email)
  VALUES ('Patrick', 'patrick@example.com'), ('Luby', 'Luby@example.com');
```

## Installation

```bash
git clone git@github.com:patricknascimento/node-api-postgres
cd node-api-postgres
npm install
node index.js
```

## Commands

- GET: `curl http://localhost:3000/users`
- POST: `curl --data "name=Jerry&email=jerry@example.com" http://localhost:3000/users`
- PUT: `curl -X PUT -d "name=George" -d "email=george@example.com" http://localhost:3000/users/1`
- DELETE: `curl -X "DELETE" http://localhost:3000/users/1`

## Author

- [Patrick Nascimento]

## License

This project is open source and available under the [MIT License](LICENSE).
