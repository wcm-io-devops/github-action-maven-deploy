<img src="https://wcm.io/images/favicon-16@2x.png"/> github-action-maven-deploy
======

Composite GitHub Action that deploys Maven artifacts.

Usage example:

```yaml
# Deploy snapshots to Sonatype OSS repository

name: Deploy

concurrency: ${{ github.workflow }}

on:
  push:
    branches:
      - develop
  workflow_dispatch:

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
      - name: Maven Deploy
        uses: wcm-io-devops/github-action-maven-deploy@v1
        with:
          java-version: 21
          maven-executable: ./mvnw
          sonatype-username: ${{ secrets.SONATYPE_USERNAME }}
          sonatype-password: ${{ secrets.SONATYPE_PASSWORD }}
```

For all parameters, see [action.yml](action.yml).
