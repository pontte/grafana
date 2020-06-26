# Grafana Docker image

This topic contains instructions for installing Grafana using the Docker image.

## Configuration

Create a new file called .env at the root folder with tha following content:

```
ENV=development
EB_DOMAIN=localhost
EB_PORT=3000
DB_TYPE=mysql
DB_HOST=
DB_NAME=
DB_USER=
DB_PASSWORD=
GITHUB_CLIENT_ID=
GITHUB_CLIENT_SECRET=
SMTP_HOST=
SMTP_LOGIN=
SMTP_PASSWORD=
SMTP_MAIL_ADDRESS=
```

## Deploy to EB

#### To Production

Steps:

- Create a new EB app to run a single Docker instance WITHOUT a proxy
- Set the en variables like the .env file 
- Just add all files to a zip file and upload to EB service.

#### To Development

You can try to run it locally running:

```
docker build -f grafana .
docker run -it -p 3000:3000 --env-file=.env grafana
```