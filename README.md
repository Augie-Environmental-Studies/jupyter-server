# What is this repository for?

Jupyter Lab server. Work in progress.
Designed to run in a private virtual server.
Designed to deployed with Docker Compose.

***How we use this repository to run our Jupyter server***<br>
```bash
git clone https://github.com/Augie-Environmental-Studies/jupyter-server.git
cd jupyter-server

# Run this only the first time you run.
# Skip these after the first time.
docker compose up -d
docker exec -it jupyter sh
jupyter lab password
<Set the Jupyter access password>
<Press ctrl + d to exit the docker process>
docker compose down
docker compose up -d
```

<br>
<br>
