# Nginx Multicolor Reverse Proxy / Load Balancer 

This project demonstrates a basic Nginx setup with reverse proxy and load balancing across multiple Docker services. It includes three main routes:
- **Blue Service** at `http://app-blue-127-0-0-1.nip.io` – directed to the `webcolorblue` service.
- **Green Service** at `http://app-green-127-0-0-1.nip.io` – directed to the `webcolorgreen` service.
- **Load-Balanced Service** at `http://app-web-127-0-0-1.nip.io` – distributed across `web1`, `web2`, and `web3`.

This project utilizes [nip.io](https://nip.io/) for DNS resolution based on IP address and port configuration.

## Prerequisites
- Docker installed
- Docker Compose installed

## Setup and Run

1. Clone the repository.
   ```bash
   git clone git@github.com:murichristopher/nginx-multicolor.git
   cd nginx-multicolor
   ```

2. Make sure `nginx.conf` is located in the root directory.

3. Run the services with Docker Compose:
   ```bash
   docker-compose up -d
   ```

4. Access the services:
   - Blue Service: [http://app-blue-127-0-0-1.nip.io](http://app-blue-127-0-0-1.nip.io)
   - Green Service: [http://app-green-127-0-0-1.nip.io](http://app-green-127-0-0-1.nip.io)
   - Load-Balanced Service: [http://app-web-127-0-0-1.nip.io](http://app-web-127-0-0-1.nip.io)

5. Stop the services:
   ```bash
   docker-compose down
   ```

## Notes
- Make sure `nip.io` correctly resolves to your local machine IP.
- This configuration allows you to test reverse proxy, blue/green deployment, and load balancing in a Docker environment.
