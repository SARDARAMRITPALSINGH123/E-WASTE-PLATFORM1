name: Deploy

on:
  push:
    branches: [main, master]
  workflow_dispatch:

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment:
      name: production
      url: https://ctrlfreaks-ecocycle.floot.app/
    steps:
      - name: Check site is live
        run: curl --fail --silent --show-error --location https://ctrlfreaks-ecocycle.floot.app/ > /dev/null

      - name: Done
        run: echo "Deployed to https://ctrlfreaks-ecocycle.floot.app/"
