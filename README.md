# What is this repository for?

JupyterLab server. Designed to run in a private virtual server.
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
our server to the internet. Instead, use Cloudflare Tunnel
to proxy every traffic. We followed installation instructions at
https://www.cloudflare.com/products/tunnel/

So, how does it look like? When we go to our
Jupyter Server website,
Cloudflare Tunnel is set up such that our website first
first requires users to login using GitHub oAuth.
Jupyter then asks the user to login using the password
we set earlier. This way, we have two layers of security.

<br>
<br>
