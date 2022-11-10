# What is this repository for?

A JupyterLab server designed to be deployed with Docker Compose.

***How we use this repository to run our Jupyter server***<br>
```bash
# Running this on your personal computer puts your computer
# at risk. We run this on a virtual private server.
ssh test@127.123.456.789
git clone https://github.com/Augie-Environmental-Studies/jupyter-server.git
cd jupyter-server
docker compose up -d
```

For better security, we don't directly expose
our server to the internet. Instead, we use Cloudflare Tunnel
to proxy every traffic and user authentication. We followed the installation instructions at
https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/install-and-setup/tunnel-guide/

So, when we go to our Jupyter Server website,
we can login by using our school email.
We can only get in with our school email because Cloudflare
Tunnel checks the domain name of the mail we put in.
This means anyone from outside our school - at least theoretically -
cannot have access to our website.

<br>
<br>
