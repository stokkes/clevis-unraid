# Clevis for Unraid

Automated encryption framework for LUKS devices on Unraid.

## Features

- Bind LUKS devices to Tang servers for network-based unlocking
- TPM2 support (if available)
- Manual unlocking of clevis-bound LUKS devices
- Full clevis-luks toolset

## Installation

1. Go to Unraid WebUI > Plugins > Install Plugin
2. Paste the plugin URL: https://raw.githubusercontent.com/stokkes/clevis-unraid/master/clevis.plg
3. Click Install

## Usage

```bash
# Bind a LUKS device to Tang server
clevis luks bind -d /dev/sdX tang '{"url":"http://tang-server:port"}'

# List bindings
clevis luks list -d /dev/sdX

# Unlock device
clevis luks unlock -d /dev/sdX -n my-disk

# Unbind
clevis luks unbind -d /dev/sdX -s 1

## Requirements

 - Unraid 6.9.0 or later
 - LUKS encrypted devices
 - Tang server (for Tang binding method)
