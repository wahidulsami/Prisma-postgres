# Prisma + PostgreSQL CRUD Application

A simple starter project for building a CRUD application with **Prisma** and **PostgreSQL**.

## Features

- Prisma ORM setup
- PostgreSQL database integration
- Create, read, update, and delete operations
- Clean project structure
- Easy to extend for real-world apps

## Tech Stack

- Node.js
- Prisma
- PostgreSQL
- Express.js

## Getting Started

### 1. Install dependencies

```bash
npm install
```

### 2. Configure environment variables

Create a `.env` file and add your database URL:

```env
DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/DB_NAME"
```

### 3. Run Prisma migrations

```bash
npx prisma migrate dev
```

### 4. Generate Prisma client

```bash
npx prisma generate
```

### 5. Start the app

```bash
npm run dev
```

## Example Prisma Schema

```prisma
generator client {
	provider = "prisma-client-js"
}

datasource db {
	provider = "postgresql"
	url      = env("DATABASE_URL")
}

model User {
	id        Int      @id @default(autoincrement())
	name      String
	email     String   @unique
	createdAt DateTime @default(now())
	updatedAt DateTime @updatedAt
}
```

## CRUD Routes Example

- `POST /users` - Create a user
- `GET /users` - Get all users
- `GET /users/:id` - Get a single user
- `PUT /users/:id` - Update a user
- `DELETE /users/:id` - Delete a user

## Folder Structure

```text
prisma/
	schema.prisma
src/
	routes/
	controllers/
	services/
	app.js
```

## License

MIT
