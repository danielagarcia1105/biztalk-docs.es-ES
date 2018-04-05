---
title: Desarrollar aplicaciones de SAP mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, developing applications by using
ms.assetid: 1ce70c8b-5eeb-4585-97af-b0a7b4398dac
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13015cb042d26c946abfa3c99a4f67034b8d9708
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sap-applications-using-the-wcf-channel-model"></a>Desarrollar aplicaciones de SAP mediante el modelo de canal de WCF
Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] mediante el envío de mensajes XML directamente a través de una instancia del canal creado con el enlace de SAP.  
  
 Una ventaja de usar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que expone el modelo de servicio WCF es que el modelo del canal proporciona un control más minucioso sobre las operaciones que se realizan en el sistema SAP. ¿Por qué? En el modelo del canal WCF controla directamente el contenido de los mensajes que envía a través del canal.  
  
 Otra ventaja clave que proporciona el modelo de canal WCF en el modelo de servicio WCF es más completa compatible con transmisión por secuencias de datos. Mediante el modelo de canal WCF puede realizar:  
  
-   Nodo de mensaje en todos los mensajes intercambiados entre el código y el adaptador de transmisión por secuencias.  
  
-   Nodo de mensaje-valor transmisión por secuencias en las operaciones de SendIdoc y ReceiveIdoc.  
  
 Esto es porque en el modelo de canal WCF puede controlar directamente cómo proporcionar el cuerpo del mensaje en mensajes que se envían al adaptador y cómo consumir el cuerpo del mensaje en los mensajes que recibe el adaptador.  
  
 En cambio, el adaptador no proporciona compatibilidad con transmisión por secuencias en el modelo de servicio WCF. Ya que, en el modelo de servicio WCF, el tiempo de ejecución WCF serializa y deserializa mensajes entre sus representaciones de objeto de código administrado y XML, se realiza una copia en memoria completa de cada mensaje que intercambia con el adaptador.  
  
 Las secciones en este tema explica cómo realizar operaciones en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante el modelo de canal WCF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo del canal de WCF con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-channel-model-with-the-sap-adapter.md)  
  
-   [Crear un canal con SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)  
  
-   [Invocar operaciones en el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)  
  
-   [Recepción de las operaciones de entrada desde el sistema SAP mediante el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md) 
  
-   [Transmisión por secuencias IDOC de archivo plano en SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)