This is a demo project written in NextJS. It uses prisma for ORM (which means connects to database)

# Run on your local machine

- Step 1, clone this project to your local machine and within the project root folder 
  install dependencies
```bash
npm i
```
- Step 2, setup database of sqlite (which is just an in 
memory database only for the ease of testing)
    - make sure the prisma/schema.prisma file has this
  ```c
    datasource db {
      provider = "sqlite" 
      url      = env("DATABASE_URL")     
    }
  ```
    - Then Run a migration to create your database tables with Prisma Migrate
    ```bash
    npx prisma migrate dev --name init
    ```
- Step 3, run dev server to serve the NextJS web app
    ```bash
    npm run dev
    ```

# Run on aws ec2 with a mysql RDS

- Step 0, fire up ec2 and mysql rds, set up correctly with their security rules
    > By default, nextjs dev server run on port 3000 of http, so allow it's request
- Step 1, clone this project to the ec2 and within the project root folder
  install dependencies
```bash
npm i
```
- Step 2, setup database of mysql rds 
    - ***make sure the prisma/schema.prisma file has this***
  ```c
    datasource db {
      provider = "mysql" 
      url      = "mysql://USER:PASSWORD@HOST:PORT/DATABASE"  
    }
  ```
  > Change the USER, PASSWORD, PORT and DATABASE of your mysql rds, specifically
  > you have to have an existing DATABSE within mysql. 
  > Tables can be created by prisma

    - Then Run a migration to create your database tables with Prisma Migrate
    ```bash
    npx prisma migrate dev --name init
    ```
- Step 3, run dev server to serve the NextJS web app
    ```bash
    npm run dev
    ```


##














This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
