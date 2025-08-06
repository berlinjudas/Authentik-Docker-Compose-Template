# Authentik Docker Compose Template

A complete Docker Compose setup for Authentik - a modern Identity Provider and SSO solution.

## 🚀 Quick Start

### 1. Clone Repository
```bash
git clone https://github.com/berlinjudas/Authentik-Docker-Compose-Template.git
cd Authentik-Docker-Compose-Template
```

### 2. Configure Environment Variables
```bash
# Copy the example file
cp .env.example .env

# Edit the .env file and replace the placeholders
nano .env
```

### 3. Generate Secrets

**Generate PostgreSQL Password:**
```bash
openssl rand -base64 36
```

**Generate Authentik Secret Key:**
```bash
openssl rand -base64 60
```

Copy these values into your `.env` file and replace:
- `YOUR_PG_PASSWORD_HERE` with the PostgreSQL password
- `YOUR_SECRET_KEY_HERE` with the Authentik secret key

### 4. Start Containers
```bash
docker-compose up -d
```

### 5. Setup Authentik

Open your browser and navigate to:
- **HTTP:** `http://localhost:9000/if/flow/initial-setup/`
- **HTTPS:** `https://localhost:9443/if/flow/initial-setup/`

Follow the setup wizard to create an admin user.

## ⚙️ Configuration

### Customize Ports

Default ports can be changed in the `.env` file:
```env
COMPOSE_PORT_HTTP=9000    # HTTP Port
COMPOSE_PORT_HTTPS=9443   # HTTPS Port
```

### Logging

Log level can be adjusted:
```env
AUTHENTIK_LOG_LEVEL=info  # debug, info, warning, error
```

## 📂 Project Structure

```
├── docker-compose.yml    # Main configuration
├── .env.example         # Environment variables template
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## 🔧 Services

- **PostgreSQL 16:** Database backend
- **Redis:** Cache and session store
- **Authentik Server:** Web interface and API
- **Authentik Worker:** Background tasks

## 🔒 Security

- All sensitive data is configured via environment variables
- The `.env` file is excluded in `.gitignore`
- PostgreSQL and Redis are only accessible internally
- Use strong, random passwords

## 📖 Further Documentation

- [Authentik Documentation](https://goauthentik.io/docs/)
- [Docker Compose Reference](https://docs.docker.com/compose/)

## 🤝 Contributing

Feel free to create issues or submit pull requests!

## 📄 License

This project is licensed under the MIT License.
