Overview
========
This is a project to build a data pipeline to process stock data from the https://query1.finance.yahoo.com/v8/finance/chart/aapl?metrics=high?&interval=1d&range=1y then conduct ETL for analysis on a meta base

![Image](https://github.com/user-attachments/assets/d00fe301-39a8-448e-9ff7-ab6e324a256c)
Project Contents
================

Your Astro project contains files and folders:
- dags: This folder contains the Python files for your Airflow DAGs. 
- Dockerfile: This file contains a versioned Astro Runtime Docker image that provides a differentiated Airflow experience. If you want to execute other commands or overrides at runtime, specify them here.
- include: This folder contains any additional files that you want to include as part of your project. It is empty by default.
- packages.txt: Install OS-level packages needed for your project by adding them to this file. 
- requirements.txt: Install Python,minio,docker,slack packages needed for your project by adding them to this file.
- plugins: Add custom or community plugins for your project to this file.
- airflow_settings.yaml: Use this local-only file to specify Airflow Connections, Variables, and Pools instead of entering them in the Airflow UI as you develop DAGs in this project.

Deploy Your Project Locally
===========================

1. Start Airflow on your local machine by running 'astro dev start'.

This command will spin up 4 Docker containers on your machine, each for a different Airflow component:

- Postgres: Airflow's Metadata Database
- Webserver: The Airflow component responsible for rendering the Airflow UI
- Scheduler: The Airflow component responsible for monitoring and triggering tasks
- Triggerer: The Airflow component responsible for triggering deferred tasks

2. Verify that all 4 Docker containers were created by running 'docker ps'.

Note: Running 'astro dev start' will start your project with the Airflow Webserver exposed at port 8080 and Postgres exposed at port 5432. If you already have either of those ports allocated, you can either [stop your existing Docker containers or change the port](https://www.astronomer.io/docs/astro/cli/troubleshoot-locally#ports-are-not-available-for-my-local-airflow-webserver).

3. Access the Airflow UI for your local Airflow project. To do so, go to http://localhost:8080/ and log in with 'admin' for both your Username and Password.

You should also be able to access your Postgres Database at 'localhost:5432/postgres'.
You should also be able to access your Minio Database at 'http://localhost:9001'.

How to run in your machine
=================================
First,you have install docker.
Second,install Astro CLI using this command "winget install -e --id Astronomer.Astro".
Third,in your folder you got in github,run this command line in terminal "astro dev start",if you don't get airflow ui,run this "astro dev restart" then go to minio host and airflow host to see the result.

