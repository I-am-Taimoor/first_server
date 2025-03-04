Add Docker files by default to new apps: Dockerfile, .dockerignore, bin/docker-entrypoint. These files can be skipped with --skip-docker. They're intended as a starting point for a production deploy of the application. Not intended for development (see [Docked Rails](https://github.com/rails/docked) for that).

Example:
docker build -t app .
docker volume create app-storage
docker run --rm -it -v app-storage:/rails/storage -p 3000:3000 --env RAILS_MASTER_KEY=<see config/master.key> app
