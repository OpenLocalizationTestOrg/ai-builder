---
title: Security in AI Builder -  AI Builder | Microsoft Docs
description: Describes security information related to roles, privileges, and access in AI Builder and the services it connects to. 
author: Dean-Haas
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: 
ms.date: 09/06/2019
ms.author: v-dehaas
ms.reviewer: v-dehaas
---

# Security in AI Builder

AI Builder relies on environment security and Common Data Service security roles and privileges to grant access to AI features in PowerApps. For more information, see [Security overview](/power-platform/admin/wp-security).

Some privileges are set by default in Common Data Service, allowing built-in security roles to take advantage of AI Builder without further actions from system administrators.

- Environment makers can use AI Builder to create AI models.
- Common Data Service users can inference data using the models embedded in PowerApps.
- Administrators and system customizers can access all AI models created in the environment.

These security roles have already set the right privileges to the AI Builder entities from Common Data Service. Custom security roles will be able to create AI models as long as they have the same privileges to the AI Builder entities as the environment maker role.

> [!div class="mx-imgBorder"]
> ![Security roles screen](media/security-roles-screen.png "Security roles screen" )

Scenarios such as object detection, text classification, and prediction require read access to entities from Common Data Service. Make sure environment makers have access to them in case they need to use those entities as object to detect, tagged text, and input data respectively. For object detection and form processing, environment makers must also have full organization privileges over the **Note** entity from **Core Records**.

Some scenarios require at least system customizer privileges to publish AI models and allow consumption since these actions imply changes to the Common Data Service schema. Therefore, we recommend that administrators assign system customizer to users who need to create such AI models.

When you create a prediction AI model, a new field needs to be added to the input entity to store the prediction results from the prediction. Therefore, you need at least system customizer rights to publish the model for the first time.

For text classification AI models, an entity is created for every new model once the model runs for the first time. Therefore, only system customizers or administrators can run the model. After the model runs, administrators must modify the access rights to the newly created text classification entity in Common Data Service to allow users to use the results.

### Related topic

[Security concepts in Common Data Service](/power-platform/admin/wp-security-cds)
