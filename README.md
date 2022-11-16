# Nodejs and MongoDB CRUD Template

Much of the code in this was borrowed from [Tien Nguyen](https://github.com/tienbku). Please check him out!

This repo runs a CRUD app which allows you to add and delete tutorials. A tutorial has the shape:

```json
{
  "title": "Learning to code",
  "description": "How to learn the best skill in the world",
  "published": true
}
```

To run this template out of the box on Brev click here:

[![](https://uohmivykqgnnbiouffke.supabase.co/storage/v1/object/public/landingpage/pill-border-lg.png)](https://console.brev.dev/environment/new?repo=https://github.com/brevdev/CRUD-nodejs-mongodb)

## Running everything in docker-compose:

There are two services in this repo: the backend node api and the database. Running:

```bash
docker-compose up
```

will spin them both up.

## Running the backend outside of Docker Compose:

You can then pull the backend node service out of docker compose and run it locally:

1. Comment out lines 15 to 30 of docker-compose.yml
2. Run:

```bash
docker-compose up
```

3. Then cd into backend and run it via npm:

```bash
cd backend
npm i
npm start
```

## Making calls to your server:

To view all tutorial entries:

```bash
curl http://localhost:8080/api/tutorials
```

To add a new tutorial:

```bash
curl --request POST \
  --url http://localhost:8080/api/tutorials \
  --header 'Content-Type: application/json' \
  --data '{
	"title": "Learning to code",
	"description": "How to learn the best skill in the world",
	"published": true
}'
```

## Forwarding ports:

To forward a port to your local machine (if you're using Brev), in VScode you should see a ports section next to terminal. Enter port 8080 to forward.
