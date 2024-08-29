## Server setup

It contains the scripts to manage the server for the various services

- `setup.sh` - To install all the required packages and setup the server.
    - Run `wget https://raw.githubusercontent.com/nik-55/astrikos-server-setup/master/setup.sh` to download the setup script
    - Run `chmod +x setup.sh` to make the script executable
    - Run `./setup.sh` to start the setup process

- `update.sh` - To pull the latest code for the various services and update them.
    - Run `wget https://raw.githubusercontent.com/nik-55/astrikos-server-setup/master/update.sh` to download the update script
    - Run `chmod +x update.sh` to make the script executable
    - Run `./update.sh` to start the update process

- `astrikos.conf` - Nginx configuration file that directs the thingsboard requests to the thingsboard service and `/backend/$1` to the flow service

- `backend.conf` - Nginx configuration file for the admin panel
