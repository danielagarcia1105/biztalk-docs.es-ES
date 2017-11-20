---
title: "Configurar el límite máximo de conexiones al servidor SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 858ed90e-b219-43cc-ad63-ae8e1eb2159a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 853a3b78b82e242750e30099f847045ff590f125
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-maximum-connection-limit-to-the-sap-server"></a><span data-ttu-id="39c4d-102">Configurar el límite máximo de conexiones al servidor SAP</span><span class="sxs-lookup"><span data-stu-id="39c4d-102">Configure the Maximum Connection Limit to the SAP Server</span></span>
<span data-ttu-id="39c4d-103">El proveedor de datos para SAP permite a los clientes de adaptador controlar el número máximo de conexiones que se pueden abrir internamente por el proveedor.</span><span class="sxs-lookup"><span data-stu-id="39c4d-103">The Data Provider for SAP enables adapter clients to control the maximum number of connections that can be opened by the provider internally.</span></span> <span data-ttu-id="39c4d-104">Puede controlar esto estableciendo la variable de entorno CPIC_MAX_CONV.</span><span class="sxs-lookup"><span data-stu-id="39c4d-104">You can control this by setting the environment variable, CPIC_MAX_CONV.</span></span>  
  
 <span data-ttu-id="39c4d-105">Por ejemplo, si CPIC_MAX_CONV se establece en cualquier valor numérico, el número de conexiones de RFC abiertas en cualquier momento será menor o igual a ese valor numérico.</span><span class="sxs-lookup"><span data-stu-id="39c4d-105">For example, if CPIC_MAX_CONV is set to any numerical value, the number of RFC connections opened at any time will be less than or equal to that numerical value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39c4d-106">El valor numérico se pueden aplicar para cada servidor individualmente en el proceso y appdomain que establece este valor.</span><span class="sxs-lookup"><span data-stu-id="39c4d-106">The numerical value will be applicable for every server individually under the process/appdomain which sets this value.</span></span>  
  
 <span data-ttu-id="39c4d-107">Por ejemplo, si una aplicación usa el proveedor de datos para SAP, estableció su variable de entorno en el nivel de proceso a "x" y se conecta a dos servidores diferentes A y B, a continuación, el número máximo de conexiones para ambos A y B será "x" respectivamente.</span><span class="sxs-lookup"><span data-stu-id="39c4d-107">For example, if an application using Data provider for SAP, has set its environment variable at process level to “x” and connects to two different servers A and B, then the maximum number of connections for both A and B will be “x” respectively.</span></span>