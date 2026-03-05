# WireGuard Mesh Role

Configures a host as part of a WireGuard mesh using `wg-quick`.

## What It Does

- Installs `wireguard`
- Renders `/etc/wireguard/{{ wireguard_interface }}.conf`
- Allows the WireGuard UDP port in UFW
- Enables and starts `wg-quick@{{ wireguard_interface }}`

## Required Host Variables

- `wireguard_address`
- `wireguard_public_key`
- `wireguard_private_key`

For mesh peers, these are read from `hostvars` of hosts in the `wireguard` group.

## Optional Variables

See defaults in `defaults/main.yml` for tunables such as:
- interface and port
- keepalive
- shared/override preshared keys
- extra non-mesh peers
