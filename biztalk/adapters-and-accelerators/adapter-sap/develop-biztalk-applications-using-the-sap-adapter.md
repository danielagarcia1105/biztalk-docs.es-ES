---
title: Desarrollar aplicaciones de BizTalk con el adaptador SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
ms.assetid: 4aa10897-a08e-4fc3-9c1f-40485d204273
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75e70a52f12227b1bde3a43f9330c6fe373ac5a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-sap-adapter"></a>Desarrollar aplicaciones de BizTalk con el adaptador SAP
Desarrollo de aplicaciones de BizTalk implica la creación de un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y el uso de la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema XML. Una vez que haya generado el esquema, puede usar enrutamiento por contenidos (CBR) o crear orquestaciones de BizTalk para enviar y recibir mensajes que cumplen el esquema generado.  
  
 CBR puede utilizarse en escenarios donde los mensajes que se envían al sistema SAP no requieren ningún procesamiento intensivo. Por ejemplo, si sabe que el puerto de recepción va a recibir mensajes sólo de un tipo determinado, puede agregar un filtro al puerto de envío para enrutar los mensajes que coinciden con la expresión de filtro para el puerto de envío.  
  
 En las orquestaciones de BizTalk, creará el envío y puertos de recepción para enviar y recibir mensajes desde y hacia el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que a su vez envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Esta sección proporciona información sobre el uso de las orquestaciones de BizTalk para realizar operaciones en el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a su vez usa la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] adaptador que puede interactuar con un enlace de WCF.  
  
> [!IMPORTANT]
>  Para usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre se debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**. Para obtener información sobre cómo establecer propiedades de enlace, vea [configurar las propiedades de enlace para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Requisitos previos para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
-   [Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
  
-   [Invocar RFC en SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)  
  
-   [Recibir llamadas de RFC de entrada de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)  
  
-   [Invocar tRFCs en SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)  
  
-   [Recibir llamadas de tRFC entrada de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)  
  
-   [Ejecutar BAPI transacciones en SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)  
  
-   [Enviar los IDOC a SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)  
  
-   [Recibir IDOC desde SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)  
  
-   [Recibir IDOC de SAP en un contexto transaccional usando el servidor BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)