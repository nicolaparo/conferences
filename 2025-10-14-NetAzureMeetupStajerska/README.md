# Monitor your IoT Asset with Azure Free Services

Presentation for **.NET & Azure Meetup Štajerska**  
📅 Thursday, October 16, 2025 · 18:30 – 21:00 CEST  
📍 Tehnološki Park Ptuj, Vičava 1, 2250 Ptuj

**Speaker:** Nicola Paro  
Solution Architect | Microsoft MVP

## Overview

This presentation demonstrates how to build a cost-effective IoT monitoring platform using Azure's free tier services. The session covers real-world scenarios where budget constraints require creative solutions using Azure's free service offerings.

## Key Concepts

### IoT Data Classification

- **Hot Data**: Real-time notifications and data aggregates requiring immediate action
- **Warm Data**: Sampled data accumulated locally and uploaded every minute
- **Cold Data**: Contextual data from MES, ERP, and general registries
- **Hot Streaming**: Real-time streaming of warm data, enabled on-demand

### Monitoring Levels

1. **First Level**: Real-time streaming monitoring
2. **Second Level**: Warm data monitoring
3. **Third Level**: Cold data analytics (not real-time monitoring)

## Architecture Components

The monitoring platform consists of the following components:

### 1. Event Storage
**Options:** Azure Cosmos DB or Azure SQL Database

- **Cosmos DB Free Tier**: 1000 RU/s + 25 GB storage
- **Azure SQL Free Tier**: 100,000 seconds * vCore + 32 GB storage/month

### 2. Web Socket Communication
**Chosen:** Azure Web PubSub

- Real-time event notifications to frontend
- Free tier: 20,000 messages/day + 20 concurrent connections
- Supports multiple protocols (WebSocket, Server-Sent Events, Long Polling)

### 3. Receiver (Event Ingestion)
**Solution:** Azure Functions

- Receives occasional events from IoT devices
- Stores events in Event Storage
- Notifies via WebSocket
- Free grant: 400,000 GB-s + 1 million invocations/month

### 4. API Layer
**Chosen:** Azure Container Apps

- Reads events from Event Storage
- Performs small aggregates
- Exposes REST APIs for UI consumption
- Free grant: 180,000 vCPU-seconds + 360,000 GiB-seconds + 2 million requests/month

### 5. User Interface
**Solution:** Azure Static Web Apps

- Hosts static web application
- Integrated with Data API Builder for backend
- Free tier includes SSL, CI/CD, global distribution
- 100 GB bandwidth/month + unlimited hosting

## Demo Application

The demo showcases monitoring a Minecraft server using the RCON protocol, demonstrating the complete pipeline from edge collection to cloud visualization.

## Azure Free Services Used

All components utilize Azure's free tier offerings:

- ✅ Azure Cosmos DB or Azure SQL Database (Free Tier)
- ✅ Azure Web PubSub (Free Tier)
- ✅ Azure Functions (Free Grant)
- ✅ Azure Container Apps (Free Grant)
- ✅ Azure Static Web Apps (Free Tier)

## Required Tools

To work with this technology stack locally:

```bash
# Static Web App CLI
npm install -g @azure/static-web-apps-cli

# Data API Builder
dotnet tool install Microsoft.DataApiBuilder

# Blazor WebAssembly tools
dotnet workload install wasm-tools-net6
```

## Resources

- **Azure Free Services**: https://azure.microsoft.com/en-us/pricing/free-services
- **Static Web Apps CLI**: https://azure.github.io/static-web-apps-cli/docs/use/install/

## Connect with the Speaker

**Nicola Paro**
- LinkedIn: [linkedin.com/in/nicolaparo](https://linkedin.com/in/nicolaparo)
- GitHub: [github.com/nicolaparo](https://github.com/nicolaparo)

## Community

Join the discussion on Discord: https://discord.gg/K6F7pdP4xq

