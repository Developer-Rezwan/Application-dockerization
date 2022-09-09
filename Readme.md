# Dockerized Laravel 9.19

### Working procedures...

- Clone the repository
  <code> git clone https://github.com/Developer-Rezwan/Application-dockerization.git </code>
  <br />

* Inside the project folder > for the first time you need to run...
  <small> For Ubuntu </small>
  <code> sudo docker compose up --build -d </code>
  <small> For Mac </small>
  <code> docker-compose up --build -d </code>
  <small> For Windows </small>
  <code> docker-compose up --build -d </code>

<i>Note: For next time, you don't need to run with <code> --build </code> flag, just run <code> sudo docker compose up -d </code>
</i>

#### Used images :

         * Nginx:alpine
         * Php:8.0.23-fpm-alpine3.16
         * Mysql:latest
         * redis:alpine

###### After all done you will browse your app by <code> <i> https://localhost or https://127.0.0.1 </i></code>

<small> Note: Must run with <code>https://</code>. Because , SSL is configured by NGINX. </small>

### Extra Configuration :

If You want to run by you custom domain. like <code>https://laravel-app.dev </code> . You need to configure your local machine.
Go to <code>/etc/hosts </code> and configure your DNS.

<img src="/docs/dns.png"/>

### Application view :

<img src="/docs/app-view.png"/>
