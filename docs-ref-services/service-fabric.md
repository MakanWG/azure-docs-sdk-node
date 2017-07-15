---
title: Azure Service Fabric module for Node.js
description: Reference for Azure Service Fabric module for Node.js
keywords: Azure,SDK,API,Service Fabric, Node.js
author: tomarcher
ms.author: tarcher
manager: douge
ms.date: 06/30/2017
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: nodejs
ms.service: Service Fabric
---

# Azure Service Fabric module for Node.js

## Overview

Azure Service Fabric is a distributed systems platform that makes it easy to package, deploy, and manage scalable and reliable microservices and containers. 

Learn more about [Azure Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-overview).

## Management Package

### Install npm module

Use npm to install the Azure Service Fabric module for Node.js
```bash
npm install azure-arm-servicefabric
```

### Example

This example shows how you can list the clusters for an Azure subscription.
```javascript
const msRestAzure = require('ms-rest-azure');
const ServiceFabricManagement = require('azure-arm-servicefabric');

const subscriptionId = 'your-subscription-id';

msRestAzure
  .interactiveLogin()
  .then(credentials => {
    const client = new ServiceFabricManagement(
      credentials,
      subscriptionId
    );
    return client.clusters.list();
  })
  .then(clusters => {
    console.log('List of clusters:');
    console.dir(clusters, { depth: null, colors: true });
  });
```

### Samples

Explore more [sample Node.js code](https://azure.microsoft.com/resources/samples/?platform=nodejs) you can use in your apps.