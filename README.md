# Hackathon TS Monorepo Template

This is a monorepo template for a TypeScript-based web application. It includes a client-side NextJS application and a server-side NestJS application, with PostgreSQL database through sequelize .

## Getting Started

### Prerequisites

- NodeJS (24.x.x)
- PNPM (10.14.0)
- Docker (28.x.x, with Docker Compose) (Optional for dockerized development; Required for dockerized deployment)
- PostgreSQL (17.x.x)

### Development

#### Local Development

1. Clone the repository
2. Run `pnpm install` from the root directory to install dependencies
3. Run `pnpm dev` to start the development server (client and server); alternatively, you may start the development server individually using `pnpm dev:web` and `pnpm dev:server`

This will start the NextJS development server on port 3000 by default, and the NestJS server on port 4000 by default

#### Dockerized Development

1. Clone the repository
2. Run `pnpm docker:dev` to start the development server (client and server) using Docker Compose

This will start the NextJS development server on port 3000 by default, and the NestJS server on port 4000 by default.

The ports can be configured in the respective application's `.env.dev` configuration file. For example, the NextJS development server port can be changed by modifying the `PORT` variable in the `./apps/client/.env.dev` file.

The port mapping for the Docker Compose configuration can be found in the root `.env` file. Both development and production configurations use the same `.env` for mapping.

Note: the client and server applications maybe independently dockerized using a few other commands defined in the root `package.json` file.

### Deployment

1. Clone the repository
2. Run `pnpm docker:prod` to build and deploy the application using Docker Compose

If required, update the `.env` file in the root directory to configure the port mapping and deployment environment.
