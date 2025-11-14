Dutchie Integration Engine (Container Edition)

This repository hosts the containerized version of my Dutchie integration engine. It manages inbound webhooks, scheduled syncs, and outbound posting into accounting and ERP targets. The goal is simple: provide a reliable, cloud-ready path to move Dutchie data where it needs to go.

What This Repo Is

This repo exists so you can see how the container is built, how the service is structured, and how it deploys cleanly into Azure. It’s a reference implementation plus a transparent look at the architecture.

You can explore the source, learn from the shape of the project, and understand how the containerized pipeline runs.

What This Repo Is Not

This is not an open source project.
The code is not licensed for production use, commercial deployments, or derivative work.

If you want to run this engine in your environment, you’ll need a commercial license or SaaS access through Acadia Logic.

Features

Webhook endpoint for Dutchie events

Scheduled sync worker (via Azure Container Apps Jobs)

Scale to zero support

Rate limiting, retries, and request signing

Container-first design with .NET 8

Fully environment-driven configuration

Azure-optimized HTTP port, health checks, and logging

Local Development

You can test the container locally to understand the flow.

docker build -t dutchie-integrator .
docker run -p 8080:8080 dutchie-integrator

Visit http://localhost:8080/health to confirm it’s running.


Environment variables follow typical conventions:

DUTCHIE_API_KEY=
DUTCHIE_WEBHOOK_SECRET=
DB_CONNECTION_STRING=
TARGET_ENV=Local

Azure Deployment Overview

This engine is built to run on Azure Container Apps with the Consumption plan.

Recommended setup:

Container App for the webhook interface

Container Apps Job for the scheduled syncs

Storage for state and logs

Secrets in Azure Key Vault or Container Apps secrets

Scaling configured to zero for low-cost startup

This configuration keeps costs near zero until real traffic appears.

Licensing

All rights reserved.
Viewing is permitted.
Use is not.

No production use, redistribution, or commercial deployment is allowed without a paid license or explicit written permission.

See the LICENSE file for details.

Commercial Licensing or SaaS Access

If you want to deploy this engine, integrate it into an accounting stack, or use it as a managed SaaS offering, reach out:

Acadia Logic LLC
info@acadialogic.io
