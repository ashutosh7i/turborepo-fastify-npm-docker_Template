# Turborepo npm Docker starter

This is a turborepo template which contains a project including a nodejs api server and a nextjs frontend, and it uses nodejs as package manager, use it to monorepo for nodejs + npm based projects.


## What's inside?

This Turborepo includes the following:

### Apps and Packages

- `web`: a [Next.js](https://nextjs.org/) app
- `api`: an [Express](https://expressjs.com/) server
- `@repo/ui`: a React component library
- `@repo/logger`: Isomorphic logger (a small wrapper around console.log)
- `@repo/eslint-config`: ESLint presets
- `@repo/typescript-config`: tsconfig.json's used throughout the monorepo
- `@repo/jest-presets`: Jest configurations

Each package/app is 100% [TypeScript](https://www.typescriptlang.org/).

### Docker

This repo is configured to be built with Docker, and Docker compose. To build all apps in this repo:

```
# Install dependencies
npm install

# Create a network, which allows containers to communicate with each other, by using their container name as a hostname
# (Skip this if the network already exists)
docker network create app_network

# Build prod using new BuildKit engine
$env:COMPOSE_DOCKER_CLI_BUILD=1
$env:DOCKER_BUILDKIT=1
docker-compose -f docker-compose.yml build

# Start prod in detached mode
docker-compose -f docker-compose.yml up -d
```

Open http://localhost:3000.

To shutdown all running containers:

```
# Stop running containers started by docker-compse
 docker-compose -f docker-compose.yml down
```
### Utilities

This Turborepo has some additional tools already setup:

- [TypeScript](https://www.typescriptlang.org/) for static type checking
- [ESLint](https://eslint.org/) for code linting
- [Jest](https://jestjs.io) test runner for all things JavaScript
- [Prettier](https://prettier.io) for code formatting
