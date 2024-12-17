# WebTech Monorepo

## Setup

First install required tooling

- Node.js & npm: https://nodejs.org/
- Docker: https://docs.docker.com/get-started/get-docker/

Under windows the wsl is also required (install with `wsl --install`)
Under linux docker has to be configured to run in user mode

To initialize run `npm install`, `npm run dev-db:init` and `npx playwright install`

## Running in DEV-Mode

### Starting in one console

To start the entire app-stack run `npm run dev` and make sure the dev db is running.

### Starting in different Consoles

First run `npm run shared:watch` to continues compile the shared package. Then run `npm run frontend:dev` to start the frontend on a local dev server. To start the backend first run `npm run dev-db:run` to start the _dev-db_ (if the db scheme changed run `npm run dev-db:reinit` instead) then run `npm run backend:watch` to continues compile the backend. Then run `npm run backend:dev` to launch a local dev server.

## Running Tests

Before running any tests make sure that your setup is complete. Then you can run unit and integration test with `npm run test:backend` for the backend and `npm run test:frontend`. Unit tests for the shared package can be run with `npm run test:shared` To run the e2e tests run `npm run test:e2e`
