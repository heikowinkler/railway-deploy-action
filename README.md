# Deploy to Railway GitHub Action

This GitHub Action simplifies deploying your applications to Railway using the Railway CLI.  It avoids the need for additional paid user slots on your Railway account that the official Railway GitHub integration requires, offering a more cost-effective solution.

## Features

* **Direct Railway CLI Deployment:** Uses the official Railway CLI for deployment, ensuring compatibility and access to the latest features.
* **Simplified Workflow:** Streamlines your deployment process by handling CLI installation and execution.
* **Environment Variables:** Securely passes your Railway project token and service name as environment variables.
* **Cost-Effective:** Eliminates the need for extra paid user slots on Railway, saving you money.

## Usage

### Inputs

| Input          | Description                               | Required |
|----------------|-------------------------------------------|----------|
| `project-token` | The Railway project token.                 | Yes      |
| `service-name` | The name of the service to deploy.        | Yes      |

### Example Workflow

```yaml
name: Deploy to Railway

on:
  push:
    branches:
      - main  # Or your preferred branch

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Deploy to Railway
        uses: all-win-solutions/deploy-to-railway@v1
        with:
          project-token: ${{ secrets.RAILWAY_PROJECT_TOKEN }}
          service-name: my-service-name # Replace with your service name
