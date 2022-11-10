# What is this repository for?

Jupyter Lab server. Designed to run in a private virtual server.
Designed to be deployed with Docker Compose.

***How we use this repository to run our Jupyter server***<br>
```bash
# Running this on your personal computer puts your computer
# at risk. We run this on a virtual private server.
ssh test@127.123.456.789
git clone https://github.com/Augie-Environmental-Studies/jupyter-server.git
cd jupyter-server
docker compose up -d

# Run the codes below only the first time you run.
# Skip these after the first time.
docker exec -it jupyter sh
jupyter lab password
# <Set the Jupyter access password>
# <Press ctrl + d to exit the docker process>
docker compose down
docker compose up -d
```

For better security, we don't directly expose
our server to the internet. Instead, we hide our
server behind Cloudflare Tunnel and let Cloudflare
aproxy everything for us. We followed installation instructions at
https://www.cloudflare.com/products/tunnel/

So, how does it look like now? When we go to our
Jupyter Server website, which we won't disclose
because it's only for testing and development purposes for now,
Cloudflare Tunnel first requires users to login using
GitHub oAuth. After that, Jupyter's built-in login
system requires users to login using the password we set earlier.

<br>
<br>
