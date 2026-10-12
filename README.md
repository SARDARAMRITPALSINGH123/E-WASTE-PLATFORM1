name: Deployment

on:
  push:
    branches: [main]
  workflow_dispatch:

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment:
      name: production
      url: https://ctrlfreaks-ecocycle.floot.app/
    steps:
      - run: echo "Live at https://ctrlfreaks-ecocycle.floot.app/"
