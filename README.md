# Prisma 6
Repository to learn how to setup Prisma 6.

## 🛠️ How to Setup Prisma with PostgreSQL
```text
- npm install prisma@6 --save-dev                           # install Prisma CLI v6
- npm install @prisma/client@6                              # install Prisma Client v6
- create database in pgAdmin (e.g., "mini_store_db")        # setup your PostgreSQL
- npx prisma init                                           # initialize Prisma folder
- edit .env file:
  DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/DATABASE_NAME?schema=public"
- edit prisma/schema.prisma (Ensure URL is inside the datasource block):
  generator client {
    provider = "prisma-client-js"
    output   = "../src/generated/prisma"
  }

  datasource db {
    provider = "postgresql"
    url      = env("DATABASE_URL")
  }

  model posts {
    id        Int      @id @default(autoincrement())
    title     String
    content   String
    author    String
    createdAt DateTime @default(now())
  }
- npx prisma generate                                       # run command, to generate the client code
- npx prisma migrate dev --name init                        # push schema to PostgreSQL
- create src/connection/client.ts, insert this code:

import { PrismaClient } from '@prisma/client';
export const prisma = new PrismaClient();

- 

```

## 🚀 Implementation Flow
```text
1. Setup TypeScript: Configure the compiler and folder structure.
2. Setup Prisma 6: Install specific version 6 to match learning materials.
3. Model Definition: Define the Product table in schema.prisma.
4. Migration: Use npx prisma migrate dev to create the table in PostgreSQL.
5. Controller Logic: Use prisma.product.create/findMany/update/delete in your controllers.

```

#### Notes

- prisma documentation : https://www.prisma.io/docs/getting-started/prisma-orm/add-to-existing-project/postgresql
- prisma CRUD : https://www.prisma.io/docs/orm/prisma-client/queries/crud