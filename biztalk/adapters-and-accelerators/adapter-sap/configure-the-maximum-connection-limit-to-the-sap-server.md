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
# <a name="configure-the-maximum-connection-limit-to-the-sap-server"></a>Configurar el límite máximo de conexiones al servidor SAP
El proveedor de datos para SAP permite a los clientes de adaptador controlar el número máximo de conexiones que se pueden abrir internamente por el proveedor. Puede controlar esto estableciendo la variable de entorno CPIC_MAX_CONV.  
  
 Por ejemplo, si CPIC_MAX_CONV se establece en cualquier valor numérico, el número de conexiones de RFC abiertas en cualquier momento será menor o igual a ese valor numérico.  
  
> [!NOTE]
>  El valor numérico se pueden aplicar para cada servidor individualmente en el proceso y appdomain que establece este valor.  
  
 Por ejemplo, si una aplicación usa el proveedor de datos para SAP, estableció su variable de entorno en el nivel de proceso a "x" y se conecta a dos servidores diferentes A y B, a continuación, el número máximo de conexiones para ambos A y B será "x" respectivamente.