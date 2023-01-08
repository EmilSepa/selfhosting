# selfhosting
This repository includes all services that i host myself on my local network. Like: traefik, pihole, portainer, uptime-kuma and more in the future. 

I wanted: 
  HPPTS/SSL on all services with a webinterface: Traefik, Portainer, pihole (only the adminpanel/webinterface, not port 53), Uptime-Kuma, SearXNG)
  Everything should work behind Traefik and should be reachable via a domain (from Hetzner for example) with Let's Encrypt Certificates. 
  The peculiarity here is that I don't have an open port to the outside via my OPNsense. Therefore, the certificates are generated via DNS challenge.
