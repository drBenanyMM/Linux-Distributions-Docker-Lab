# 🐧 MultiLinux Docker Lab

Environnement de laboratoire Linux multi-distributions basé sur Docker.  
Ce projet permet d’exécuter simultanément plusieurs distributions Linux
dans des conteneurs isolés pour l’apprentissage, l’administration système,
les tests de compatibilité et les travaux pratiques DevOps.

---

## Objectif

Ce lab permet de :

- Comparer différentes distributions Linux
- Tester des commandes et outils système
- Pratiquer l'administration Linux
- Simuler des environnements multi-OS
- Former les étudiants en systèmes et DevOps

---

## 📦 Distributions incluses

| Distribution        |       Image Docker           | Conteneur    |
|---------------------|------------------------------|--------------|
| Debian              | `debian:latest`              | `lab-debian` |
| Fedora              | `fedora:latest`              | `lab-fedora` |
| Alpine              | `alpine:latest`              | `lab-alpine` |
| openSUSE Tumbleweed | `opensuse/tumbleweed:latest` | `lab-suse`   |


## 🐳 Docker Compose

```yaml
services:
  debian-lab:
    image: debian:latest
    container_name: lab-debian
    tty: true

  fedora-lab:
    image: fedora:latest
    container_name: lab-fedora
    tty: true

  alpine-lab:
    image: alpine:latest
    container_name: lab-alpine
    tty: true

  suse-lab:
    image: opensuse/tumbleweed:latest
    container_name: lab-suse
    tty: true

---
## 🚀 Installation et lancement

### 1️⃣ Cloner le dépôt

```bash
git clone https://github.com/drBenanyMM/Linux-Distributions-Docker-Lab.git
cd Linux-Distributions-Docker-Lab

### 2️⃣ Démarrer tous les conteneurs

```bash
docker compose up -d

### 3️⃣ Accéder à un conteneur

#### Pour Debian :

```bash
docker exec -it lab-debian bash
## 📄 Licence

Projet académique à but pédagogique.


## 🖥️ Commandes essentielles pour le Docker Lab

Cette section liste toutes les commandes que tu peux utiliser pour **installer, configurer et tester ton lab multi-distributions**.


### 1️⃣ Démarrage et gestion des conteneurs

- **Démarrer tous les conteneurs** :  

```bash
docker compose up -d

Accéder à un conteneur :

# Debian
docker exec -it lab-debian bash

# Alpine
docker exec -it lab-alpine sh

# Fedora
docker exec -it lab-fedora bash

# openSUSE
docker exec -it lab-suse bash

Arrêter les conteneurs sans perdre les données :

docker compose stop

Redémarrer les conteneurs :

docker compose start

Supprimer les conteneurs mais garder les volumes :

docker compose down

Supprimer conteneurs et volumes (tout est perdu) :

docker compose down -v

2️⃣ Mise à jour et outils système dans Debian

Mettre à jour le système :

apt update && apt upgrade -y

Installer les outils système indispensables :

apt install -y man-db sudo bash-completion

Ces outils permettent :

d’utiliser le manuel (man ls)

d’exécuter des commandes administrateur avec sudo

d’activer l’autocomplétion avec la touche TAB

Installer les outils de texte et réseau :

apt install -y nano curl wget

Installer les outils de surveillance système :

apt install -y htop procps

Installer l’outil de changement d’utilisateur et créer un étudiant :

apt install -y login
useradd -m etudiant

L’option -m crée automatiquement le dossier /home/etudiant.

