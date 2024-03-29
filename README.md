# homelab-microk8s-setup
This repo will contain all configuration files for my home kubernetes lab consisting of 3 Lenovo M910 tiny pcs's with i5 and 16GB of RAM each.
All three machines are running Ubuntu Server 22.04 at the moment, for kubernetes I decided to use microk8s.

Might in the future reinstall with ODK as I am used to the fancy OpenShift web interface. The regular kubernetes dashboard doesn't really convince me.

## Network setup
Kubernetes home lab is in a separate subnet behind a mikrotik router. Fritzbox is configured to port forward port 443 and 80 to the cluster accordingly.
Port 80 is required to be open for letsencrypt issueing with http01 challenge.

## Roadmap (outstanding work)
For now, as letsencrypt issueing uses http-01 challenge we cannot request a wildcard certificate, meaning subdomains routed with traefik cannot use the letsencrypt certificate.
Therefore the goal is to switch to dns-01 challenge long term. Need to have properly setup a custom DNS Server for the domain for this though.

https://microk8s.io/docs/addon-cert-manager

## Warning
This is a work in progress and not guaranteed to be complete, nor work.

