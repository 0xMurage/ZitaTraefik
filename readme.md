# ZitaTraefik

This project demonstrates how to set up Zitadel behind a Traefik reverse proxy using Docker Compose.
Follow these instructions to get the demo up and running on your local machine.

## Prerequisites

Before you begin, ensure you have the following installed on your system:
- Docker
- Docker Compose

## Getting Started

### 1. Clone the Repository

Start by cloning this repository to your local machine:
```sh
git clone git@github.com:0xMurage/ZitaTraefik.git

cd ZitaTraefik
```

### 2. Configure Environment Variables

Copy the example environment configuration file and update it with your settings:
```sh
cp .env.example .env
```

Edit the `.env` file and set the following variables as needed:
- `TRAFFIK_DASHBOARD_DOMAIN`: The domain for the Traefik dashboard.
- `ZITADEL_APP_DOMAIN`: The domain for the Zitadel app.
- Other required environment variables for Zitadel and Traefik.

### 3. Configure DNS Resolution

Ensure that the domains specified in `.env` for both Traefik and Zitadel can be resolved.
For local development, you may need to add aliases in your `/etc/hosts` file. Example entries might look like:
```
127.0.0.1    dashboard.abaer.in
127.0.0.1    auth.abaer.in
```

### 4. Start the Services

Run the following command to start both the Zitadel and Traefik services, along with any additional services defined in `compose.override.yaml`:
```sh
docker compose up
```

This command will start the services defined in `compose.yaml` and override configurations in `compose.override.yaml`.
The override file includes services for issuing TLS certificates and a PostgreSQL database necessary for this demo.

### 5. Access the Applications

- **Zitadel App**: Open your browser and navigate to the Zitadel application domain specified in your `.env` file. Use the first human account credentials provided in `.env` to log in.

- **Traefik Dashboard**: Open your browser and navigate to the Traefik dashboard domain specified in your `.env` file to ensure everything is up and running.

### Troubleshooting

If you encounter issues, check the following:
- Ensure Docker and Docker Compose are properly installed and running.
- Verify that the domain names resolve correctly (check `/etc/hosts` if using local development).
- Review the logs for both Traefik and Zitadel to identify any errors or issues:


## Notes

- This setup is intended for demonstration and development purposes. It is not suitable for production environments.
- For production use, consider configuring additional security features and using production-grade services for TLS and database management.

## Contributing

If you have any improvements or fixes, feel free to submit a pull request or open an issue in the repository.

## License

This project is licensed under the MIT License. 

# Contact
For questions or support, please open an issue on the GitHub repository.

