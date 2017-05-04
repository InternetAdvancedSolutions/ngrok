# hgrok - Introspected tunnels to localhost ([homepage](https://beta.hasura.io))
### ”I want to expose a local hasura project behind a NAT or firewall to the internet.”
![](https://dev.beta.hasura.io/rstatic/dist/d381a3c91a318589ac4b383222295d17.png)

## What is hgrok?
hgrok is a fork of ngrok for developers to expose their local hasura projects to the Internet via a secure tunnel.
Just like ngrok, hgrok is a reverse proxy that creates a secure tunnel from a public endpoint to a locally running web service. hgrok captures and analyzes all traffic over the tunnel for later inspection and replay.

## What can I do with hgrok?
- Expose any http service behind a NAT or firewall to the internet on a subdomain of hasura.me. If you choose a subdomain called 'john', requests to \*.john.hasura.me will come through the tunnel to your server.

Just like ngrok, you can also use hgrok to:
- Inspect all http requests/responses that are transmitted over the tunnel
- Replay any request that was transmitted over the tunnel


## What is hgrok useful for?
- Temporarily sharing your hasura project that is only running on your development machine
- Demoing an app at a hackathon without deploying to a cloud provider


## Usage
- Register an account at [hasura](https://beta.hasura.io)
- Configure your hasura.me subdomain at https://dev.beta.hasura.io/local-development
- Get your hasura.io api token from https://dev.beta.hasura.io/settings
- Download the hgrok binary for your OS from [to-be-added](#)

- Run the following command if you are running a server on minikube (mac/linux):

```
./hgrok -authtoken="<api-token>" -subdomain="<subdomain>" -proto=http $(minikube ip):80 
```

- Get your minikube ip, and substitute \<minikube-ip> in the command below:

```
./hgrok -authtoken="<api-token>" -subdomain="<subdomain>" -proto=http <minikube-ip>:80 
```

- Run the following command if you are running a server on localhost:80

```
./hgrok -authtoken="<api-token>" -subdomain="<subdomain>" -proto=http 80 
```
