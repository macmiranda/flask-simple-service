# Simple Flask app that greets you

In order to run this app in production you need to have `docker` and `docker-compose` installed. You also need `git` if you want to clone the repository directly on the server. Optionally, you can download the zip package from GitHub.

To check out the repository, do:

    $ git clone https://github.com/macmiranda/compose-deployment-rasa.git

To build and run the containers, do:

    $ docker-compose up -d
    
The user running the command above needs write access to `/var/run/docker.sock`. That can be easily done by adding the user to the `docker` group or by running the command with `sudo`

That's it. Now you can be greeted by creating a POST request to the service on port 9090 and passing your name in the body of the request as JSON,like so:

    S curl -X POST -H "Content-Type: application/json" -d "{\"name\": \"Marco\"}" http://<your_server_ip>:9090

Make sure you replace `<your_server_ip>` with the appropriate IP address and that the port 9090 is open on your local firewall.