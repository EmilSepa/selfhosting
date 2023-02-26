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
