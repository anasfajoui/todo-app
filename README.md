# Todo App

- [Frontend](the_project/) serves the Todo UI.
- [Backend](todo_backend/) stores todos in PostgreSQL and publishes changes to NATS.
- [Broadcaster](broadcaster/) logs todo events in staging and forwards them to Discord in production.

Each directory contains its Dockerfile, npm package and lockfile, and HTTP request examples.

## Deployment

A push to `main` deploys to staging. Pushing a Git tag deploys the tagged commit to production. The workflow sends the commit SHA and environment to the configuration repository. Its workflow builds the three images and updates the Argo CD Application. [Configuration repository](https://github.com/anasfajoui/devops-with-kubernetes)
