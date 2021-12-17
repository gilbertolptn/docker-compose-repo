# Wireguard (VPN)

# Docker command line:

```sh
docker run \
  --name wireguard \
  --cap-add=NET_ADMIN \
  --cap-add=SYS_MODULE \
  -e PUID=1000 -e PGID=1000 \
  -e TZ=Europe/London \
  -e SERVERURL=159.89.187.146 \
  -e PEERS=mobile,laptop \
  -e PEERDNS=auto \
  -p 51820:51820/udp \
  -v wireguard_config:/config \
  -v /lib/modules:/lib/modules \
  --sysctl="net.ipv4.conf.all.src_valid_mark=1" \
  --restart=unless-stopped \
  linuxserver/wireguard
```
