# Discord Github
Send message for you commits using discord-webhook
## YML File
```
name: Clone and Use Code

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  clone-and-use-code:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3
      
      - name: Setup Git
        run: git config --global user.email "action@github.com"
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

      - name: Clone target repository
        run: |
          git clone https://github.com/Thecode764/Discord-Github
          cd Discord-Github
          
      - name: 
        run: |
          python3 main.py ${{ secrets.DISCORD_WEBHOOK }}
```
## Secrets
- DISCORD_WEBHOOK: You discord webhook url