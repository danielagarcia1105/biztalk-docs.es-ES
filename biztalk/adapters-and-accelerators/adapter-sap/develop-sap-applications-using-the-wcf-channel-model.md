---
title: Desarrollar aplicaciones de SAP mediante el modelo de canal WCF | Microsoft Docs
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
ms.openlocfilehash: e2bce6ad43b6efce111a2801ba7a5b44e73dce1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013133"
---
# <a name="develop-sap-applications-using-the-wcf-channel-model"></a>Desarrollar aplicaciones de SAP mediante el modelo de canal de WCF
Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] mediante el envío de mensajes XML directamente a través de una instancia de canal creada con el enlace de SAP.  
  
 Una ventaja de utilizar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que expone el modelo de servicio WCF es que el modelo de canal proporciona un control más minucioso sobre las operaciones que se realizan en el sistema SAP. ¿Por qué? En el modelo de canal WCF controla directamente el contenido de los mensajes que envían a través del canal.  
  
 Otra ventaja clave que proporciona el modelo de canal WCF con respecto al modelo de servicio WCF es compatible con más completa para la transmisión de datos. Mediante el modelo de canal WCF se puede realizar:  
  
- Nodo de mensaje en todos los mensajes intercambiados entre el código y el adaptador de transmisión por secuencias.  
  
- Mensaje: valor de nodo transmisión por secuencias en las operaciones de SendIdoc y ReceiveIdoc.  
  
  Esto es porque en el modelo de canal WCF directamente controlar cómo proporcionar el cuerpo del mensaje en mensajes que envía al adaptador y cómo consume el cuerpo del mensaje en mensajes que recibe desde el adaptador.  
  
  En cambio, el adaptador no proporciona compatibilidad con streaming en el modelo de servicio WCF. Porque, en el modelo de servicio WCF, el tiempo de ejecución WCF serializa y deserializa los mensajes entre su XML y representaciones de objeto de código administrado, se realiza una copia en memoria completa de cada mensaje que intercambia con el adaptador.  
  
  Las secciones de este tema explican cómo realizar operaciones en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con el modelo de canal WCF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo del canal de WCF con el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-channel-model-with-the-sap-adapter.md)  
  
-   [Crear un canal con SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)  
  
-   [Invocar operaciones en el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)  
  
-   [Recepción de operaciones de entrada desde el sistema SAP mediante el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md) 
  
-   [Streaming de archivos planos de IDOC en SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)