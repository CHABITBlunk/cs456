docker-compose.yml
```yaml
version: '4.0'
services:
  dvwa:
    image: vulnerables/web-dvwa:latest
    container_name: dvwa
    hostname: dvwa
    detach: true
    restart: unless-stopped
  cowrie:
    image: stackware/docker-cowrie:latest
    container_name: cowrie
    hostname: cowrie
    detach: true
    restart: unless-stopped
  smb:
    image: demisto/smb:latest
    container_name: smb
    hostname: smb
    detach: true
    restart: unless-stopped
  samba:
    image: dockurr/samba:latest
    container_name: samba
    hostname: samba
    detach: true
    restart: unless-stopped
networks:
  labnet:
    external: true
```
