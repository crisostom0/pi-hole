## 🇧🇷 Português

# Pi-hole com Docker Compose 🇧🇷

[![Docker](https://img.shields.io/badge/docker-ready-blue?logo=docker)](https://www.docker.com/)
[![License](https://img.shields.io/github/license/crisostom0/pi-hole)](./LICENSE)
[![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)](https://github.com/crisostom0/pi-hole)
[![Last Commit](https://img.shields.io/github/last-commit/crisostom0/pi-hole)](https://github.com/crisostom0/pi-hole)

Este repositório disponibiliza um arquivo `docker-compose.yml` para rápida e fácil implementação do [**Pi-hole**](https://pi-hole.net/) utilizando Docker.

## 📌 O que é o Pi-hole?

O **Pi-hole** é um servidor DNS que atua como um filtro de anúncios e rastreadores a nível de rede.

### ✅ Benefícios:

- Bloqueio de anúncios em toda a rede
- Aumento da velocidade de navegação
- Redução no consumo de dados
- Melhoria da privacidade digital

## 📁 Sobre este projeto

Este projeto consiste num arquivo `docker-compose.yml` para deploy automatizado do Pi-hole com persistência de dados, configurável com variáveis de ambiente.

## ⚙️ Serviços configurados

| Serviço  | Porta Externa | Função Principal                  |
|----------|----------------|-----------------------------------|
| Pi-hole  | 8080:80        | Interface Web para administração |
| DNS      | 53/udp         | Serviço DNS local                 |

Volumes locais:
- `./etc-pihole`
- `./etc-dnsmasq.d`

## 🚀 Instruções de instalação

### Pré-requisitos

- Docker
- Docker Compose

### Passos

```bash
git clone https://github.com/crisostom0/pi-hole.git
cd pi-hole
mkdir -p etc-pihole etc-dnsmasq.d
```

Crie um arquivo `.env` (opcional):

```env
TZ=America/Sao_Paulo
WEBPASSWORD=coloque_aqui_uma_senha_segura
```

Inicie o container:

```bash
docker-compose up -d
```

Acesse: http://localhost:8080

## 🧪 Comandos úteis

```bash
docker-compose logs -f
docker-compose restart
docker-compose pull && docker-compose up -d
```

## 🧯 Problemas comuns

- **Porta 53 em uso**: pare o serviço `systemd-resolved`
- **Permissões nos volumes**:
```bash
sudo chown -R 999:999 etc-pihole etc-dnsmasq.d
```

## 🧾 Referências

- https://pi-hole.net/
- https://hub.docker.com/r/pihole/pihole

---

## 🇺🇸 English

# Pi-hole with Docker Compose 🇺🇸

[![Docker](https://img.shields.io/badge/docker-ready-blue?logo=docker)](https://www.docker.com/)
[![License](https://img.shields.io/github/license/crisostom0/pi-hole)](./LICENSE)
[![Status](https://img.shields.io/badge/status-in%20development-yellow)](https://github.com/crisostom0/pi-hole)
[![Last Commit](https://img.shields.io/github/last-commit/crisostom0/pi-hole)](https://github.com/crisostom0/pi-hole)

This repository provides a `docker-compose.yml` file for quickly deploying [**Pi-hole**](https://pi-hole.net/) using Docker.

## 📌 What is Pi-hole?

**Pi-hole** is a DNS server that works as a network-wide ad and tracker blocker.

### ✅ Benefits:

- Ad blocking for all devices on the network
- Faster web browsing
- Reduced data usage
- Improved privacy

## 📁 About this project

This project contains a `docker-compose.yml` file to deploy Pi-hole with persistent volumes and customizable via environment variables.

## ⚙️ Configured Services

| Service  | External Port | Main Function                      |
|----------|----------------|------------------------------------|
| Pi-hole  | 8080:80        | Admin Web Interface                |
| DNS      | 53/udp         | Local DNS Service                  |

Local volumes:
- `./etc-pihole`
- `./etc-dnsmasq.d`

## 🚀 Installation Instructions

### Requirements

- Docker
- Docker Compose

### Steps

```bash
git clone https://github.com/crisostom0/pi-hole.git
cd pi-hole
mkdir -p etc-pihole etc-dnsmasq.d
```

Create an optional `.env` file:

```env
TZ=America/Sao_Paulo
WEBPASSWORD=your_secure_password_here
```

Start the container:

```bash
docker-compose up -d
```

Access via browser: http://localhost:8080

## 🧪 Useful Commands

```bash
docker-compose logs -f
docker-compose restart
docker-compose pull && docker-compose up -d
```

## 🧯 Common Issues

- **Port 53 in use**: stop `systemd-resolved` service
- **Volume permissions**:
```bash
sudo chown -R 999:999 etc-pihole etc-dnsmasq.d
```

## 🧾 References

- https://pi-hole.net/
- https://hub.docker.com/r/pihole/pihole
