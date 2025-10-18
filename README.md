# Install Nextcloud AIO with Coolify

[Nextcloud AIO](https://github.com/nextcloud/all-in-one) is the recommended installation solution by Nextcloud for setting up the suite.

However, the installation constraints make it complicated when trying to integrate it with a [Coolify](https://coolify.io/) instance.

- The main container name must be identical (mastercontainer)
- Coolify's proxy doesn't integrate well with AIO's specific requirements

To address this, here's an adapted docker-compose file and a mini-tutorial:

1. (Best practice) Clone this repository locally
2. In your Coolify instance, go to New -> Repository (public if your repo is public, private if it's private and you're comfortable with deployment keys or GitHub App)
3. Insert your repository URL, and select the docker-compose option

We won't be using Coolify's proxy, but will instead create a Cloudflare tunnel
- Create an account in https://dash.cloudflare.com/
- Add you domain_name and allow cloudflare to manage it
- Go to Zero Trust -> Networks -> Tunnels
- Create a new tunnel
- Add the domain_name to the tunnel
- The tunnel must point to : http://nextcloud-aio-apache:11000 
  - nextcloud-aio-apache is the container-name
  - 11000 the port you configured in the docker-compose file. You can change the port if you want

- Retrieve the tunnel token and add it, in coolify, to the environment variables : TUNNEL_TOKEN
- Also, in the "advanced" menu, check the "Consistent Container Names" option 
- Uncomment the "TALK_PORT" line if you want to use TALK (optionnal)

Launch the repository and follow the procedure.