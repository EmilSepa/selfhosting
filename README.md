# selfhosting
This repository includes all basic services that i selfhost on my local network, like: traefik, pihole, and portainer. 
Feel free to expand.  
If you study the code, you will be able to add more contaainers with https

## I wanted: 

  HTTPS/SSL on all services with a webinterface: Traefik, Portainer, pihole (only the adminpanel/webinterface, not port 53), Uptime-Kuma)
  Everything should work behind Traefik and should be reachable via an offical domain (from Hetzner for example) with Let's Encrypt Certificates. 
  The peculiarity here is that I don't have an open port to the outside via my OPNsense. 
  Therefore, the certificates are generated via DNS challenge.

Currently I'm running everything on a raspberry-pi.

Meanwhile i switched to Unraid. This Repo will not be expanded. 

## To-Do:

### Before deployment:

Download all files and check for comments inside the code.  
I marked all lines that need a change. 

### During deployment:
During the deployment of your containers, you have to wait for a few minutes, until Traefik receives the Certificates.  
After that you have to set a local dns record on your dns-server (pihole, ad-guard, unbound) to redirect all your subdomains to traefik. 
If your Traefik runs on `1.2.3.4`, you have to redirect `portainer.yourdomain.com` to `1.2.3.4`(same for all other services). 
 
### After deployment: 

You have to add the following `Labels` to your pihole container.  
It is possible to create the whole pihole with portainer. Just use the compose-file as a blueprint. 


`traefik.enable=true` 

`traefik.http.routers.pihole.entrypoints=websecure` 

```traefik.http.routers.pihole.rule=Host(`pi.yourdomain.com`)```

`traefik.http.routers.pihole.service=pihole`

`traefik.http.routers.pihole.tls=true` 

`traefik.http.routers.pihole.tls.certresolver=myresolver`   

`traefik.http.services.pihole.loadbalancer.server.port=80`   


After that you can reach the webinterface with `pi.yourdomain.com/admin`
