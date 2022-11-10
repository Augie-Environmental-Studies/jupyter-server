<br>
<p align="center">
  <img alt="example screenshot" src="https://user-images.githubusercontent.com/19341857/201000605-2828bf29-da22-489d-8e09-649832c4b510.png">
</p>
<br>

# What is this repository for?

A JupyterLab server designed to be deployed with Docker Compose
as fast and easy as possible. Jupyter's
[real time collaboration feature](https://jupyterlab.readthedocs.io/en/stable/user/rtc.html)
is enabled by default, so that multiple users can
collaborate and edit at the same time.

<br>

***How we run this***<br>
```bash
# Running this on your personal computer puts your computer
# at risk. We run this on a virtual private server -- e.g. DigitalOcean.
ssh test@127.123.456.789  # Replace with your own username and IP address
git clone https://github.com/Augie-Environmental-Studies/jupyter-server.git
cd jupyter-server
docker compose up -d
```

<br>

For better security, we never expose
our server to the internet directly. Instead, we use Cloudflare Tunnel
to proxy every traffic and user authentication. We followed the installation instructions at
https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/install-and-setup/tunnel-guide/
After installation, we configure our proxy settings and authentication
settings at https://one.dash.cloudflare.com/

So, when we go to our Jupyter Server website,
we login with our school email.
Cloudflare Tunnel checks the domain name of
the email address and rejects if it's not one of
the preconfigured school domain names.

<br>
<br>
