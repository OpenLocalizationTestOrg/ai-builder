---
title: Publish your text classification model | Microsoft Docs
description: Provides steps to publish your text classification model AI Builder.
author: Dean-Haas
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: 
ms.date: 06/10/2019
ms.author: v-dehaas
ms.reviewer: kvivek
---

# Publish your text classification model

[!INCLUDE[cc-beta-prerelease-disclaimer](./includes/cc-beta-prerelease-disclaimer.md)]

When you are satisfied with your model, you can publish it. When it’s published, your model is ready to run on your Common Data Service data. Please note that it will take up to two hours for the results to be available.

In the **Model settings** pane on the right side of the screen, you can turn on Common Data Service, and get important information on where the suggested tags will be stored.

>!IMPORTANT
>
>Currently, you can only schedule Common Data Service runs using the input entity and field you used for training. AI Builder creates a destination entity where the model will store the suggested tags and their confidence scores. This destination entity will have N:1 relationship with your source/input entity. 

>!NOTE
>
>AI Builder uses Microsoft Flow to schedule and run tagging on your data. When you publish your model to run on your Common Data Service data, this will consume Flow runs from your subscription.

For more information about publishing your AI Model, go to the [Publish a model in AI Builder](publish-model-ai-builder.md) section of this document.

## Where will suggested tags be stored?
The following entity will be created to your entity when you publish a model: **TC_{*Model_Name*}**.
Tags will be stored in a field called “**new_Tags**” under this entity.

> !NOTE
>
> Due to the character limitation of the field name, if the syntax provided creates text that is over the character limit, AI Builder cuts off the end of the text. This means that the project name may be incomplete or missing. You should choose shorter names so everything is visible.


### Next steps
[View generated predictions](text-classification-view-predictions.md)

### See also
[AI Builder Release Notes](/power-platform-release-notes/october19/ai-builder)<br/>
[PowerApps docs](https://docs.microsoft.com/powerapps/)<br/>
[Microsoft Flow docs](https://docs.microsoft.com/flow/getting-started)