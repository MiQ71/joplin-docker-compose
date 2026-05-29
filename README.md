# Joplin Docker Compose Example

Example Docker Compose setup for running a self-hosted Joplin Server with PostgreSQL behind Traefik.

This repository provides a simple and reproducible starting point for hosting Joplin Server with Docker Compose and a reverse proxy.

## Why this repository exists

This repository contains the example configuration used in my article about self-hosting Joplin.

The goal is to provide a simple and reproducible setup that can be used as a starting point for your own installation.

The configuration is intentionally kept simple and focuses on the components I use in my own homelab environment.


## Features

* Joplin Server
* PostgreSQL database
* Docker Compose
* Traefik reverse proxy integration
* HTTPS support via Traefik

## Prerequisites

Before starting, make sure you have:

* Docker
* Docker Compose
* A working Traefik installation
* An external Docker network named `traefik`
* A public DNS entry pointing to your server

## Quick Start

Clone the repository:

```bash
git clone https://github.com/MiQ71/joplin-docker-compose.git
cd joplin-docker-compose
```

Create your environment file:

```bash
cp .env.example .env
```

Edit `.env` and adjust:

* Database password
* Joplin URL (`APP_BASE_URL`)
* Any mail settings you want to use

Update the Traefik hostname in `compose.yml`:

```yaml
traefik.http.routers.joplin.rule=Host(`joplin.example.com`)
```

Start the stack:

```bash
docker compose up -d
```

## Directory Structure

```text
.
├── compose.yml
├── .env.example
├── README.md
└── data/
    └── postgres/
```

## Security Notes

This repository is intended as an example configuration.

For production environments you should:

* Use strong passwords
* Keep Docker images updated
* Restrict unnecessary network access
* Create regular backups
* Monitor logs and system health

## Related Article

A detailed explanation of why I use Joplin and how it fits into a self-hosted workflow can be found here:

English:
https://kerezovic.de/en/blog/real-world/joplin-onenote-alternative/

German:
https://kerezovic.de/de/blog/praxis/joplin-onenote-alternative/

## License

MIT License

---

<details>
<summary>🇩🇪 Deutsche Version</summary>

Beispielkonfiguration für einen selbst gehosteten Joplin Server mit PostgreSQL und Traefik als Reverse Proxy.

Dieses Repository bietet einen einfachen und nachvollziehbaren Einstieg für alle, die Joplin mit Docker Compose betreiben möchten.

## Warum dieses Repository existiert

Dieses Repository enthält die Beispielkonfiguration, die auch im zugehörigen Artikel über selbst gehostetes Joplin verwendet wird.

Ziel ist es, eine einfache und nachvollziehbare Ausgangsbasis bereitzustellen, die als Grundlage für eine eigene Installation dienen kann.

Die Konfiguration wurde bewusst übersichtlich gehalten und orientiert sich an den Komponenten, die ich selbst in meinem Homelab einsetze.


## Funktionen

* Joplin Server
* PostgreSQL Datenbank
* Docker Compose
* Traefik Integration
* HTTPS über Traefik

## Voraussetzungen

Vor dem Start sollten folgende Komponenten vorhanden sein:

* Docker
* Docker Compose
* Eine funktionierende Traefik-Installation
* Ein externes Docker-Netzwerk mit dem Namen `traefik`
* Ein DNS-Eintrag für die gewünschte Domain

## Schnellstart

Repository klonen:

```bash
git clone https://github.com/MiQ71/joplin-docker-compose.git
cd joplin-docker-compose
```

Beispielkonfiguration kopieren:

```bash
cp .env.example .env
```

Anschließend die Datei `.env` anpassen:

* Datenbankpasswort setzen
* Eigene Domain bei `APP_BASE_URL` eintragen
* Optional Mail-Einstellungen konfigurieren

In der Datei `compose.yml` die Domain anpassen:

```yaml
traefik.http.routers.joplin.rule=Host(`joplin.example.com`)
```

Container starten:

```bash
docker compose up -d
```

## Sicherheitshinweise

Diese Konfiguration dient als Beispiel.

Für produktive Umgebungen sollten zusätzlich folgende Punkte berücksichtigt werden:

* Starke Passwörter verwenden
* Docker-Images regelmäßig aktualisieren
* Regelmäßige Backups erstellen
* Logs überwachen
* Nicht benötigte Dienste und Ports deaktivieren

## Weiterführender Artikel

Deutsch:
https://kerezovic.de/de/blog/praxis/joplin-onenote-alternative/

Englisch:
https://kerezovic.de/en/blog/real-world/joplin-onenote-alternative/

## Lizenz

MIT License
</details>


## About

Maintained by Mirko Kerezovic.

Website:
https://kerezovic.de

GitHub:
https://github.com/MiQ71

Topics:
Linux, Docker, Proxmox, Selfhosting, Infrastructure, Privacy and Security.
