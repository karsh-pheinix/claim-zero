# CLAIM ZERO4

A React landing page for the CLAIM ZERO4 online programme at Nelson Mandela University (14-17 September 2026). The project is built with Vite and can be served locally or packaged as an Nginx container.

## Requirements

- Node.js 22 or newer and npm
- Docker Desktop, if you want to build and run the container

## Run locally

```powershell
npm install
npm run dev
```

Vite prints the local URL after startup.

## Build and lint

```powershell
npm run build
npm run lint
```

The production files are generated in `dist/`.

## Run with Docker

Build the image from the project root:

```powershell
docker build -t claim-zero:latest .
```

Start the web server on `http://localhost:8080`:

```powershell
docker run --rm -p 8080:80 claim-zero:latest
```

## AWS workshop files

`terraform/` contains an AWS ECS-on-EC2 workshop configuration for `us-east-1`. It requires Terraform 1.5 or newer and AWS credentials configured through the AWS CLI or a standard AWS credentials profile. Review the Terraform plan and AWS costs before applying it.

The workshop security group opens inbound HTTP (port 80) to the internet. This is intended only for the temporary workshop environment; do not use this configuration as-is for a production deployment. Do not commit AWS credentials, Terraform state, or Terraform plan files. State can contain account identifiers, resource IDs, public IP addresses, and sensitive values.

Workshop walkthroughs are in [CLAIM_ZERO4_Day 1.md](./CLAIM_ZERO4_Day%201.md) and [CLAIM_ZERO4_Day 2.md](./CLAIM_ZERO4_Day%202.md).
