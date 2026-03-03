<h2 align="left">Diego Silva 💻</h2>

###

<p align="left">Olá! Sou estudante de Análise e Desenvolvimento de Sistemas na UNINTER.<br>Atualmente estou focado em desenvolvimento de software, com ênfase em lógica de programação e construção de sistemas.<br><br>Neste perfil, compartilho meus projetos, registro minha evolução prática e aplico melhoria contínua na minha trajetória como desenvolvedor.</p>

###

<img align="right" height="160" src="https://i.imgur.com/qlD8TyA.gif"  />

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="45" alt="javascript logo"  />
  <img width="17" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" height="45" alt="typescript logo"  />
  <img width="17" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="45" alt="html5 logo"  />
  <img width="17" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="45" alt="css3 logo"  />
  <img width="17" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="45" alt="python logo"  />
  <img width="17" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" height="45" alt="java logo"  />
</div>

###

<br clear="both">

name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

<img src="https://raw.githubusercontent.com/degedevv/degedevv/output/snake.svg" alt="Snake animation" />

###
