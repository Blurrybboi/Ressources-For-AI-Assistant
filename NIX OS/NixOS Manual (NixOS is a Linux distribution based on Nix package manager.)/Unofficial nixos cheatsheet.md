---
title: 
source: https://gist.githubusercontent.com/dacr/b6dddb42b346c724361d01d45a8c7f4a/raw/494d3849bae0242b5ca065916fac1e5e50555304/nixos.md
author: 
published: 
created: 2025-06-10
description: 
tags:
  - clippings
---
## 🪡
- 



--- 
## 🪢 
- Below:: 
- 

- Before:: 
- 

- Behind::
- 

---
## 🧣 
- !ngWith:: 
- 

- Synergiz!ngWith:: 
- 

- Conflict!ngWith:: 
- 

---
## 🧵 
- #📄
- 
- 
---
## 🧷 
- 




```
<!--
// summary : nixos cheat sheet
// keywords : cheatsheet, nixos
// publish : gist
// authors : David Crosson
// license : Apache NON-AI License Version 2.0 (https://raw.githubusercontent.com/non-ai-licenses/non-ai-licenses/main/NON-AI-APACHE2)
// id : 9e9f9a93-ca32-46a9-bad3-6f6d2977ca8f
// created-on : 2022-05-15T19:02:35+02:00
// managed-by : https://github.com/dacr/code-examples-manager
-->

# nixos cheat sheet

## Notes
- https://nixos.wiki/index.php?title=Cheatsheet&useskin=vector

## Installing NIXOS

### make ISO image

\`\`\`
lsblk
sudo dd of=/dev/sdh if=~/Downloads/nixos-gnome-21.11.337514.4c560cc7ee5-x86_64-linux.iso
sudo dd of=/dev/sdc1 if=nixos-gnome-22.05.2676.b9fd420fa53-x86_64-linux.iso
\`\`\`

## Operating NIXOS

- \`sudo vi /etc/nixos/configuration.nix\`
- \`sudo nixos-rebuild switch\`
- encoding users password in configuration.nix
  1. \`mkpasswd -m sha-512\`
  2. And in configuration.nix : \`hashedPassword="..."\`
  3. OF course this is not a best practice ;)

### Search for packages

- by regex        :
  \`\`\`
  nix-env -qa 'i3.*'
  nix-env -qa '.*idea.*'
  \`\`\`
- by package name : \`nix search xfce\`  (experimental)
- by command name : \`command-not-found make\`
- which package   : \`nix-locate /bin/sh\`

### Updates

\`\`\`
sudo nix-channel --update
sudo nixos-rebuild switch
\`\`\`

### Upgrades

\`\`\`
sudo nix-channel --list
sudo nix-channel --add https://nixos.org/channels/nixos-22.05 nixos
sudo nix-channel --add https://nixos.org/channels/nixos-22.11 nixos
sudo nix-channel --add https://nixos.org/channels/nixos-23.11 nixos
 \`\`\`

### Cleanup

\`\`\`
nix-collect-garbage
nix-collect-garbage -d
\`\`\`

### Cleanup boot
For example when build fail because no more space in \`/boot/\` file system 
\`\`\`
nix-env --list-generations --profile /nix/var/nix/profiles/system

nix-env --delete-generations --profile /nix/var/nix/profiles/system --delete-generations +5
nix-env --delete-generations --profile /nix/var/nix/profiles/system 199 198 197
\`\`\`

### Unstable channel

\`\`\`
sudo nix-channel --add https://nixos.org/channels/nixos-unstable nixpkgs-unstable
\`\`\`

And to make it available in \`/etc/nixos/configuration.nix\` as for example \`unstable.jetbrains.idea-ultimate\` :
\`\`\`
{ config, pkgs, ... }:

let
  unstable = import <nixpkgs-unstable> {
    config.allowUnfree = true;
  };
in
{{ config, pkgs, ... }:

let
  unstable = import <nixpkgs-unstable> {
    config.allowUnfree = true;
  };
in
{
...
}
\`\`\`

### Temporary install :)

- ephemeral install : \`nix-shell -p nmap\`
  - just for the started shell session life time !!!!! :)
```