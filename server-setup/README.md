## Server setup

It contains the scripts to manage the server for the various services

- `setup.sh` - To install all the required packages and setup the server.
    - Run `wget https://raw.githubusercontent.com/astrikos-sand/server-setup/master/setup.sh` to download the setup script
    - Run `chmod +x setup.sh` to make the script executable
    - Run `./setup.sh` to start the setup process

- `initial.sh` - To initialize the server
    - Run `wget https://raw.githubusercontent.com/astrikos-sand/server-setup/master/initial.sh` to download the script
    - Run `chmod +x initial.sh` to make the script executable
    - Run `./initial.sh` to start the initialization process

- `backend.sh` - To update the backend server.
    - Run `wget https://raw.githubusercontent.com/astrikos-sand/server-setup/master/backend.sh` to download the backend script
    - Run `chmod +x backend.sh` to make the script executable
    - Run `./backend.sh` to apply changes to the backend server

- `thingsboard.sh` - To update the thingsboard server.
    - Run `wget https://raw.githubusercontent.com/astrikos-sand/server-setup/master/thingsboard.sh` to download the thingsboard script
    - Run `chmod +x thingsboard.sh` to make the script executable
    - Run `./thingsboard.sh` to apply changes to the thingsboard server

- `astrikos.conf` - Nginx configuration file that directs the thingsboard requests to the thingsboard service and `/backend/$1` to the flow service

- `backend.conf` - Nginx configuration file for the admin panel

### Commands

- `lsb_release -a` - To check the ubuntu version
- `free -h` - To check the memory usage
- `df -h` - To check the disk usage
- `sudo systemctl status <service>` - To check the status of the service
- `sudo systemctl start <service>` - To start the service
- `sudo systemctl stop <service>` - To stop the service
- `sudo systemctl restart <service>` - To restart the service
- `nohup <command> > output.log 2>&1 &` - To run a command in the background that doesn't stop when the ssh session is closed. It also logs the output to `output.log`

#### Nginx

- `sudo nginx -t` - To test the nginx configuration
- `sudo ln -s /etc/nginx/sites-available/example.conf /etc/nginx/sites-enabled/example.conf` - To enable the site

#### Docker

- `docker ps` - To list the running containers
- `docker ps -a` - To list all the containers
- `docker logs <container>` - To check the logs of the container
- `docker exec -it <container> bash` - To get into the container
- `docker stop <container>` - To stop the container
