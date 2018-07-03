---
title: Ejemplos de adaptadores de SAP | Microsoft Docs
description: ejemplos de adaptadores WCF mySAP que pueden utilizarse con el proveedor de datos, modelo de servicio WCF, el modelo del canal WCF y BizTalk Server para SAP
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1926c9899d1c1198998c25845d5d6b4189884f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012069"
---
# <a name="samples-for-the-sap-adapter"></a>Ejemplos para el adaptador de SAP
Ejemplos para [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] se clasifican en categorías:  

- Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  

- Ejemplos de modelo de servicio WCF  

- Ejemplos de modelo de canal WCF  

- Ejemplos de [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]  


 Los ejemplos están disponibles en [BizTalk Adapter Pack 2010: ejemplos de adaptadores SAP](https://www.microsoft.com/download/details.aspx?id=1314). 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]

 En la lista siguiente describe los ejemplos.

## <a name="biztalk-server-samples"></a>Ejemplos de BizTalk Server  

|Nombre del directorio de ejemplo|Descripción|  
|---------------------------|-----------------|  
|IDOCSend|Muestra cómo enviar un IDOC a un sistema SAP.|  
|ReceiveIDOC|Muestra cómo recibir un IDOC desde un sistema SAP.|  
|ReceiveIDOC_SYSREL|Muestra cómo recibir un IDOC desde un sistema SAP. El IDOC recibido tiene el número de versión menor que el SYSREL de SAP.|  
|RFCServer|Muestra cómo recibir una llamada de servidor RFC desde el sistema SAP.|  
|SAPTransaction|Muestra cómo realizar transacciones en un sistema SAP mediante.|  
|tRFCClient|Se muestra cómo realizar llamadas de tRFC de cliente en un sistema SAP.|  

## <a name="wcf-service-model-samples"></a>Ejemplos de modelo de servicio WCF   

|Nombre del directorio de ejemplo|Descripción|  
|---------------------------|-----------------|  
|SapIdocStringClientSM|Muestra cómo enviar un IDOC a un sistema SAP mediante la invocación de la operación SendIdoc.|  
|SapRfcServerSM|Muestra cómo recibir una llamada al servidor RFC de un sistema SAP.|  
|SapBapiTxClientSM|Se muestra cómo invocar BAPI dentro de una transacción en un sistema SAP.|  
|SapTrfcClientSM|Muestra cómo invocar tRFC las llamadas del cliente en un sistema SAP.|  

## <a name="wcf-channel-model-samples"></a>Ejemplos de modelo de canal WCF  

|Nombre del directorio de ejemplo|Descripción|  
|---------------------------|-----------------|  
|SapIdocReceiveCM|Muestra cómo recibir los IDOC desde un sistema SAP|  
|SapRfcServerCM|Muestra cómo recibir una llamada de servidor RFC desde el sistema SAP.|  

## <a name="data-provider-for-sap-samples"></a>Proveedor de datos para obtener ejemplos SAP  

| Nombre del directorio de ejemplo |                                             Descripción                                              |
|-----------------------|------------------------------------------------------------------------------------------------------|
|        ado de SAP        | Muestra cómo usar el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]. |

## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones SAP](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)