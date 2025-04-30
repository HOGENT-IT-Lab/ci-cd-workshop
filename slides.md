---
marp: true
theme: gaia
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
---

![bg left:40% 80%](./img/logo.png)

# **CI/CD - GitHub Actions**

Slides voor CI/CD - GitHub Actions workshop van het IT-lab

---

# Github Actions

![bg left:100% 60%](./img/github-actions-logo.png) <!-- Plaats voor logo voor openingsslide, foefel gerust met de sizes van de bg -->

---

# Meevolgen op:

https://hogent-it-lab.github.io/ci-cd-workshop/slides <!-- URL naar de slides -->

![QR bg right contain](./img/link_qr.png) <!-- QR-code naar de slides -->

---

# Inhoud sessie (in a nutshell)

- Wat is CI/CD? 
- Waarom CI/CD gebruiken?
- Welke tooling bestaat er?
- Praktische toepassing: GitHub Actions

---

# Wat is CI/CD?

- Continuous Integration, Continuous Delivery(/Deployment)
- Code in de codebase wordt automatisch getest, gebouwd en opgezet
- Vaak in verschillende 'omgevingen' (Staging en Production) 
- Name of the game: **pipelines**!!


---

# CI/CD

![bg:10% 10%](./img/ci-cd-loop.png)

---

# Waarom CI/CD?

- Snelheid!
- Automatisatie!
- Transparantie en efficiëntie
- Testing!!

---

# DevOps - filosofie en practices

- Silo's van **Dev**elopment en **Op**eration**s** afbreken -> nauwe interactie tussen beide nodig!
- CI/CD staat **centraal** binnen de filosofie van DevOps
- Doel: automatisatie van testen, builden en deployen
- Verhoogde snelheid, frequentie én minder bugs

---

# Pipeline

![bg:60% 60%](./img/pipeline-image.png)

---

# Pipeline - standaard workflow

- Software testen (bv. syntax checking/linting, unit testen, ...)
- Software builden (afhankelijk van programmeertaal/setting)
- Software deployen
- Elke fase bevat één of meerdere stappen
---

# Tools - overview

<!-- Image van verschillende tools die bestaan -->

![bg:60% 60%](./img/ci-cd-examples.png)

---

# Tools - enkele voorbeelden

- **GitHub Actions** - built-in GitHub, goede integratie
- **Jenkins** - open-source, veel opties voor opzetten en configureren
- **GitLab CI/CD** - ~ GitHub Actions, maar dan voor GitLab
- CircleCI - cloud-based optie, ook free tier

---

# GitHub Actions

- CI/CD van GitHub
- Eenvoudig om op te zetten bij GitHub-repositories
- Integreert logischerwijs met heel wat features van GitHub!

---

# Praktische kennismaking - vandaag op het menu

- Praktische toepassing van GitHub Actions!
- Opzetten van GH-repository met basic statische website
- Pipeline: automatisch deployen van website met GitHub Pages

---

# GitHub repository opzetten

Twee opties:

1. Een eigen GitHub repository aanmaken
2. Clone nemen van onze template repository
---

# Repository aanvullen met code

- Zorg voor een statische website (HTML/CSS + JavaScript)
- Een eigen project of een nieuwe dummy site mag zeker
- 

---

# Pipeline gaan definiëren

- Verschillende stappen oplijsten:
  - Branch op remote repository
  - Broncode van de main repo binnenhalen
  - Branch gaan deployen met GitHub pages
- GitHub Actions: werkt met workflows op basis van `.yml` files!

---

# Voorbeeld - fragment publish-slides.yml file

```yml
name: "Export and publish slides"
on:
    # Add manual trigger option
    workflow_dispatch:

jobs:
  publish:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4
```
---

# GitHub - Actions bekijken