# Hosting a Searxng Instance Locally

This tutorial guides you through setting up a Searxng instance on any Linux machine, using a NanoPi-M4 with Debian 12 Bookworm as an example. This can be applied to virtually any hardware. We'll configure the server with a static IP, such as `192.168.10.10/24`, to ensure accessibility within your LAN.

To find you local ip, run `ip a` and look under something like eth0 or wlan0

## Initial Setup

1. **Update your system** to ensure all packages are current:

    ```bash
    sudo apt update && sudo apt upgrade -y
    ```

2. **Reboot** your machine:

    ```bash
    sudo reboot
    ```

3. **Log back in** and **navigate** to `/usr/local`:

    ```bash
    cd /usr/local
    ```

4. **Install necessary packages**: Git, Docker, and Docker-compose:

    ```bash
    sudo apt install git docker.io docker-compose
    ```

5. **Handling Docker-Compose installation issues**:

   If you encounter an error like 'Docker-Compose error: "line 1: Not: command not found"', install Docker-Compose manually:

    ```bash
    sudo curl -L "https://github.com/docker/compose/releases/download/v2.6.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    sudo chmod +x /usr/local/bin/docker-compose
    ```

6. **Clone the Searxng Docker repository**:

    ```bash
    sudo git clone https://github.com/searxng/searxng-docker.git
    ```

7. **Change into the `searxng-docker` directory**:

    ```bash
    cd searxng-docker/
    ```

## Configuration

1. **Edit the `.env` file** to set your instance's IP address. First, list all files, including hidden ones, to find `.env`:

    ```bash
    ls -ah
    ```

2. **Open** `.env` with nano (or your preferred editor):

    ```bash
    sudo nano .env
    ```

3. **Configure** the `SEARXNG_HOSTNAME` with your static IP address. Leave `LETSENCRYPT_EMAIL` commented unless you're configuring SSL:

    ```plaintext
    SEARXNG_HOSTNAME=192.168.10.10
    # LETSENCRYPT_EMAIL=<email>
    ```

4. **Save and exit** nano.

5. **Add a secret key** to your `settings.yml` for security:

    ```bash
    sudo sed -i "s|ultrasecretkey|$(openssl rand -hex 32)|g" searxng/settings.yml
    ```

## Start Searxng

1. **Optionally reboot** your machine:

    ```bash
    sudo reboot
    ```

2. **Navigate back** to `/usr/local/searxng-docker/`:

    ```bash
    cd /usr/local/searxng-docker/
    ```

3. **Start Searxng** using Docker Compose:

    ```bash
    sudo docker-compose up -d
    ```

4. **Check running containers** to ensure it's up:

    ```bash
    sudo docker ps
    ```

## Restarting and Updating

- To apply changes or update, **stop** and then **start** the Docker containers:

    ```bash
    sudo docker-compose down
    sudo docker-compose up -d
    ```

## Accessing Searxng

- Now, Searxng should be accessible from any device on your LAN through the browser:

    ```
    https://192.168.10.10
    ```

Replace `192.168.10.10` with the static IP you configured for your VM.
