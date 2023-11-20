# Progressive Web App - Move Permanently 301

A simple example showing how a PWA can be permanently redirected (code 301) to a new URL. 
`app1` represents the original service. `app2` represents a new service provided by a different domain. 
Our goal: New users as well as users who have installed the PWA should be redirected to `app2`.

## Procedure
1. Run `docker-compose.yml`. Two services, `app1` and `app2`, start on `:8090` and `:8091`, respectively.
2. Open [localhost:8090](http://localhost:8090).
3. Stop the services, reload the website. Thanks to the service worker, the page should still work.
4. In the `docker-compose.yml`, replace the nginx site configuration. Thus, comment the line starting with `- "./app1/default.conf...` and comment out the line after it.
5. Start the services again.
6. Open [localhost:8090](http://localhost:8090) in a private session -> it should instantly redirect to [localhost:8091](http://localhost:8091).
6. Reload [localhost:8090](http://localhost:8090) in your normal session -> it should also redirect to [localhost:8091](http://localhost:8091).