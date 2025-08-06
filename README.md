# Authentik Docker Setup

Einfaches Docker Compose Setup für [Authentik](https://goauthentik.io/) - eine moderne Identity Provider und Single Sign-On Lösung.

## 🚀 Schnellstart

### Voraussetzungen
- Docker und Docker Compose
- `openssl` für sichere Passwort-Generierung

### Installation

1. **Repository klonen und wechseln:**
   ```bash
   git clone <your-repository-url>
   cd authentik-docker
   ```

2. **Umgebungsdatei erstellen:**
   ```bash
   cp .env.example .env
   ```

3. **Sichere Passwörter generieren:**
   ```bash
   echo "PG_PASS=$(openssl rand -base64 36 | tr -d '\n')" >> .env
   echo "AUTHENTIK_SECRET_KEY=$(openssl rand -base64 60 | tr -d '\n')" >> .env
   ```

4. **Container starten:**
   ```bash
   docker-compose up -d
   ```

5. **Setup abschließen:**
   Öffne: **http://YOUR-SERVER-IP:9001/if/flow/initial-setup/**
   - Benutzername: `akadmin`
   - Passwort: Wähle ein sicheres Passwort

## 🌐 Zugriff

- **Web Interface:** http://YOUR-SERVER-IP:9001
- **Initial Setup:** http://YOUR-SERVER-IP:9001/if/flow/initial-setup/

## 📚 Hilfreiche Links

- **Video Tutorial:** https://www.youtube.com/watch?v=N5unsATNpJk
- **Dokumentation:** https://docs.goauthentik.io/docs/
