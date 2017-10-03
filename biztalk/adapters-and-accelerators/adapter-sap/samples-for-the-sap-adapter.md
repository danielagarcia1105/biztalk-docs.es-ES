---
title: Ejemplos para el adaptador SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- samples, Data Provider for SAP
- samples, migration
- samples, BizTalk
- samples, WCF service model
- samples, WCF channel model
- samples
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0374aada037282a68e7575136b8671bba5ca181d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="samples-for-the-sap-adapter"></a>Ejemplos para el adaptador SAP
Ejemplos de [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] se clasifican en categorías:  
  
-   Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  
  
-   Ejemplos de modelo de servicio WCF  
  
-   Ejemplos de modelo de canal WCF  
  
-   Ejemplos de [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]  
  
-   Ejemplos de migración  
  
 Los ejemplos están disponibles en [http://go.microsoft.com/fwlink/?LinkID=196854](http://go.microsoft.com/fwlink/?LinkID=196854).  
  
 En la lista siguiente contiene los nombres y descripciones de los ejemplos para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="biztalk-server-samples"></a>Ejemplos de BizTalk Server  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|IDOCSend|Muestra cómo enviar un IDOC a un sistema SAP.|  
|ReceiveIDOC|Muestra cómo recibir un IDOC desde un sistema SAP.|  
|ReceiveIDOC_SYSREL|Muestra cómo recibir un IDOC desde un sistema SAP. El IDOC recibido tiene el número de versión menor que el SYSREL de SAP.|  
|RFCServer|Muestra cómo recibir una llamada de servidor RFC desde el sistema SAP.|  
|SAPTransaction|Muestra cómo realizar transacciones en un sistema SAP mediante.|  
|tRFCClient|Se muestra cómo realizar llamadas de cliente tRFC en un sistema SAP.|  
  
## <a name="wcf-service-model-samples"></a>Ejemplos de modelo de servicio WCF  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|SapIdocStringClientSM|Muestra cómo enviar un IDOC a un sistema SAP mediante la invocación de la operación de SendIdoc.|  
|SapRfcServerSM|Muestra cómo recibir una llamada de servidor RFC desde un sistema SAP.|  
|SapBapiTxClientSM|Muestra cómo invocar BAPI dentro de una transacción en un sistema SAP.|  
|SapTrfcClientSM|Muestra cómo invocar las llamadas de cliente tRFC en un sistema SAP.|  
  
## <a name="wcf-channel-model-samples"></a>Ejemplos de modelo de canal de WCF  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|SapIdocReceiveCM|Muestra cómo recibir IDOC desde un sistema SAP|  
|SapRfcServerCM|Muestra cómo recibir una llamada de servidor RFC desde el sistema SAP.|  
  
## <a name="data-provider-for-sap-samples"></a>Proveedor de datos para obtener ejemplos SAP  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|ado de SAP|Muestra cómo utilizar el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].|  
  
## <a name="migration-samples"></a>Ejemplos de migración  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|SAP_RFC_Migration|Muestra cómo utilizar un proyecto de BizTalk creado con la versión anterior del adaptador SAP y ponerla en marcha con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. El proyecto de BizTalk contiene una orquestación para invocar la solicitud de cambio de SD_RFC_CUSTOMER_GET.|  
|SendIDOC_Migration|Muestra cómo utilizar un proyecto de BizTalk creado con la versión anterior del adaptador SAP y ponerla en marcha con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. El proyecto de BizTalk contiene una orquestación para enviar un IDOC a un sistema SAP.|  
|ReceiveIDOC_Migration|Muestra cómo utilizar un proyecto de BizTalk creado con la versión anterior del adaptador SAP y ponerla en marcha con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. El proyecto de BizTalk contiene una orquestación para invocar la recepción un IDOC desde un sistema SAP.|  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)