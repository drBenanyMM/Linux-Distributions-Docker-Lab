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