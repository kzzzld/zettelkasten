# How to Homelab for Beginners

Hello! Homelabbing is a great hobby. You can self-host a lot of things and be independent from monopolls.
Today, we're going deeply Homelab. Let's get started.

## 1. Installation of Ubuntu Server

Today, we're using Ubuntu Server, it's fast and stable. But in installation, there's some notes.

### 1.1. Don't Install any services in installation

Installer will ask things like "Do you want to install Nextcloud?". Say no.
We won't use any services from Snaps. We'll use Docker.

### 1.2. Enable Unattended Upgrades and Livepatch

It's a choice upon you but I prefer enabling it.
I don't want any security breach in my system.

## 2. Make server looking cool

Personally, I install `btop` and run it on my server's screen so it looks cool and I can check stats about my server.

To install that, let's run this command.

```bash
sudo apt install btop
```

## 3. Installation of Docker

We'll containerize all our applications. So, we'll use Docker for it.

To install Docker, you can check out [this](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository) guide.

## 4. Installation of Tailscale

To do that, we're going to install Tailscale with this command.

```bash
curl -fsSL https://tailscale.com/install.sh | sh
sudo tailscale up
```

And just authenticate.

### 4.1. Make your server exit node

Go to [admin panel](https://console.tailscale.com/admin/machines) then click to your homelab's three dot and enable exit node there.

### 4.2. Install Tailscale in your host device

I won't give any guide for that, I think you can do it on your own.

### 4.3. Fix: Can't access using name of the device

Solution: Disable secure DNS setting in your browser's settings page.

## 5. Installing Services

I won't tell you how you can do that but I'll give some links for compose files and if needed, I'll make you do some modifications on it.

- [Jellyfin](https://jellyfin.org/docs/general/installation/container/#installation-instructions)
- [Invidious](https://docs.invidious.io/installation/#docker-compose-method-production)
  - Remove `127.0.0.1:` from ports
  - Generate keys. Explained [here](https://docs.invidious.io/installation/#docker-compose-method-production)
- [Qbittorrent Web](https://docs.linuxserver.io/images/docker-qbittorrent/#docker-compose-recommended-click-here-for-more-info)
- [Radarr](https://docs.linuxserver.io/images/docker-radarr/#docker-compose-recommended-click-here-for-more-info)
- [Prowlarr](https://docs.linuxserver.io/images/docker-prowlarr/#docker-compose-recommended-click-here-for-more-info)
- [Sonarr](https://docs.linuxserver.io/images/docker-sonarr/#docker-compose-recommended-click-here-for-more-info)
