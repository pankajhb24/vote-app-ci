 
Project Description:

 voting-app (Multi_Container_Docker_Compose_Project)

 This project deploys a multi-container application with the help of Docker-Compose.

  Pre-requisites:

- Docker (version 28.0.1) and Docker compose (version 1.29.2)
- Knowledge of docker-compose and YAML
- Basic understanding of Python and Javascript languages

 Project Overview:

This project is a web application designed to create a poll for the Popular Container Orchestration Tool using the Vote app [Python-based]. The application collects user choices and stores them on a Redis server. A Worker app [Python-based] then collects the data from the Redis server, processes the data to create poll results, and stores the result data in a Postgres database server. Finally, the Result app [NodeJs] retrieves data from the Postgres server and displays the poll results. This application provides an interface to conduct polls, and with the help of Docker Compose, it deploys multiple containerized services, making it a scalable and efficient solution for conducting polls.

 The application consists of the following services:

- Redis: a container running the Redis key-value store on port 6379, with a healthcheck that pings the Redis server.
- PostgresDB: a container running a Postgres database on port 5432, with a healthcheck that checks the readiness of the database server.
- Vote: a container running a voting application on port 8501 that communicates with Redis for storing vote data.
- Worker: a container running a worker process that communicates with Redis for processing vote data and with Postgres for storing the processed data.
- Result: a container running a result application on port 80 that communicates with Postgres for retrieving the processed data.

All the containers are connected to a network named "project-network" using the bridge driver. The services have dependencies on each other, specified using the "depends_on" keyword, which ensures that the necessary containers are started in the correct order. Additionally, each service has a health check that monitors the container's status and helps ensure that the application is running correctly.

  Setup Instructions:

For Cloning  pankajhb24/vote-app-ci: for voting app cicd  (https://github.com/pankajhb24/vote-app-ci) repo to our system we need to download .en file for this in which I already set docker logins there which I sharing in on drive link I am sharing . then select env file after running the script voteappcicd.sh present in the one drive link 
Steps for downloading and running script 
Download script and put in your server check all below requirements like
Prerequisites:
Install jq: Ensure jq is installed on your system for parsing JSON from the Docker Hub API:
sudo apt-get install jq  # For Debian/Ubuntu
sudo yum install jq      # For CentOS/RHEL
then provide necessary permission and run 
chmod +x voteappcicd.sh and run command ./voteappcicd.sh for Executing the script.



