# selfhosting
This repository includes all basic services that i selfhost on my local network, like: traefik, pihole, portainer, uptime-kuma. 
You can expand the basics. 

## I wanted: 

  HTTPS/SSL on all services with a webinterface: Traefik, Portainer, pihole (only the adminpanel/webinterface, not port 53), Uptime-Kuma)
  Everything should work behind Traefik and should be reachable via an offical domain (from Hetzner for example) with Let's Encrypt Certificates. 
  The peculiarity here is that I don't have an open port to the outside via my OPNsense. 
  Therefore, the certificates are generated via DNS challenge.

Currently I'm running everything on a raspberry-pi.

Meanwhile i switched to Unraid. This Repo will not be expanded. 

## To-Do:

During the deployment of your containers, you have to wait for a few minutes, until Traefik receives the Certificates. 
After that you have to set a local dns record on your dns-server (pihole, ad-guard, unbound) to redirect all your subdomains to traefik. 
If your Traefik runs on 1.2.3.4, you have to redirect portainer.yourdomain.com to 1.2.3.4 (same for all other services). 
