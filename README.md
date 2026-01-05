# Learn-Prisma
Repository to learn how to setup Prisma

## 🛠️ How to Setup Prisma
```text
- npm install prisma @prisma/client                 # to install prisma & add prisma client
- npx prisma init --datasource-provider [database]  # run command, replace [database] with your own database
- edit schema.prisma file                           # in generated schema.prisma file define user schema
- npx prisma generate                               # run command
- add/edit index.js                                 # Import the PrismaClient and initialize it in Javascript file
- node index                                        # run command to see database
```