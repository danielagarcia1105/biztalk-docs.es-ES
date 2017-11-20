---
title: Ejemplo interactuar y mensajes de FileAct | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8552167c-2acc-4eae-a86a-55ba2e54d4a2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c2541e2ec3a6fe77de374843a47befacf3a791
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sample-interact-and-fileact-messages"></a><span data-ttu-id="49a73-102">Ejemplo interactuar y mensajes de FileAct</span><span class="sxs-lookup"><span data-stu-id="49a73-102">Sample InterAct and FileAct Messages</span></span>
<span data-ttu-id="49a73-103">Ejemplos de interacción y FileAct mensajes en tiempo real se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="49a73-103">Samples of InterAct and FileAct real-time messages are given below.</span></span>  
  
 <span data-ttu-id="49a73-104">**Mensaje de ejemplo interactuar en tiempo real**</span><span class="sxs-lookup"><span data-stu-id="49a73-104">**Sample InterAct real-time message**</span></span>  
  
```  
<SwInt-ExchangeRequest>  
<SwInt-Request>  
<SwInt-RequestPayload>  
TestPayloadRequestSnF  
</SwInt-RequestPayload>  
</SwInt-Request>  
</SwInt-ExchangeRequest>  
```  
  
 <span data-ttu-id="49a73-105">**Mensaje de ejemplo FileAct en tiempo real (solicitud put)**</span><span class="sxs-lookup"><span data-stu-id="49a73-105">**Sample FileAct real-time message (put request)**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Sw-ExchangeFileRequest>  
<Sw-FileRequest>  
<Sw-FileOpRequest>  
<Sw-PutFileRequest>  
<Sw-PhysicalName>%PhysicalFolderName%\sample_put.txt</Sw-PhysicalName>  
</Sw-PutFileRequest>  
</Sw-FileOpRequest>  
</Sw-FileRequest>  
</Sw-ExchangeFileRequest>  
```  
  
 <span data-ttu-id="49a73-106">**Mensaje de ejemplo FileAct en tiempo real (solicitud get)**</span><span class="sxs-lookup"><span data-stu-id="49a73-106">**Sample FileAct real-time message (get request)**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Sw-ExchangeFileRequest>  
<Sw-FileRequest>  
<Sw-FileOpRequest>  
<Sw-GetFileRequest>  
<Sw-PhysicalName>%PhysicalFolderName%\sample_get.txt</Sw-PhysicalName>  
</Sw-GetFileRequest>  
</Sw-FileOpRequest>  
</Sw-FileRequest>  
</Sw-ExchangeFileRequest>  
```  
  
