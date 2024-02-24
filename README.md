# keycloak
## To run nginx in a vm with podman, 
1. sudo sysctl net.ipv4.ip_unprivileged_port_start=80
2. check if port 80 is binded to httpd.
3. sudo firewall-cmd --zone=public --add-port=80/tcp
4. sudo firewall-cmd --zone=public --add-port=443/tcp
5. Add keycloak hostname to /etc/hosts or DNS to point the hostname to the VM ip address. Do ip addr to find out the vm ip.

## Generating keycloak.crt and keycloak.key
1. Get the CA public and private key
2. Generate the CSR
3. Generate the keycloak crt and key.

## nginx.conf
Remember to add the following to the nginx.conf for https case. If not <keycloak>/admin will not be reached. 
```
location /auth {
  ....
}
``` 

## Mapper
https://www.baeldung.com/keycloak-custom-protocol-mapper

## References
1. https://docs.oracle.com/en/learn/podman-keycloak/#what-do-you-need
2. https://www.redhat.com/sysadmin/podman-nginx-multidomain-applications
