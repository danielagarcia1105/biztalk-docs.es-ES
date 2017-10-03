---
title: Desarrollar las aplicaciones de SAP mediante el adaptador de BizTalk | Documentos de Microsoft
description: "Crear mis aplicaciones de SAP con WCF, BizTalk Server o ADO.NET con el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, use adapters
- adapters, working with
- working with adapters
ms.assetid: e8315c0d-923b-433e-9d11-4e8a53e0a1d9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50e8501249c460285f6f8dd429f8990d39e810e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-your-sap-applications"></a>Desarrollar las aplicaciones de SAP

## <a name="overview"></a>Información general
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Las aplicaciones cliente pueden utilizar la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para invocar operaciones en artefactos SAP. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] pueden utilizarse:  
  
-   A través de un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Mediante la invocación de métodos en una instancia de un proxy de cliente.  
  
-   Como un servicio WCF hospedado.  
  
-   Mediante el envío de mensajes SOAP a través de una instancia de canal en el código que usa el modelo de canal WCF.  
  
-   A través de una interfaz ADO.NET.  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>Canal de vs de servicio WCF de BizTalk vs WCF frente a ADO.NET
  
 En la tabla siguiente:  
  
-   Enumera las distintas operaciones que se pueden realizar en un sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Indica cuál de los enfoques ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], modelo, modelo de canal WCF o ADO.NET interfaz de servicio de WCF) puede utilizarse para realizar las operaciones.  
  
-   Proporciona vínculos para obtener más información acerca de cómo realizar la tarea mediante el método elegido.  
  
|Tarea|BizTalk Server|Modelo de servicio WCF|Modelo del canal de WCF|Interfaz de ADO.NET|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|Invocar RFC en un sistema SAP|[Invocar RFC en SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)|[Invocar RFC en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)|[Invocar operaciones en el sistema SAP mediante el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)|[Invocación de RFC y BAPI utilizando el comando EXEC en SAP](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)|  
|Recibir llamadas entrantes de RFC de un sistema SAP|[Recibir llamadas de RFC de entrada de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)|[Recibir llamadas de RFC de entrada en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)|[Operaciones de entrada de recepción desde el sistema SAP mediante el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|Invocar tRFCs en un sistema SAP|[Invocar tRFCs en SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)|[Invocar tRFCs en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)|[Invocar operaciones en el sistema SAP mediante el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|Recibir llamadas de tRFC entrante desde un|[Recibir llamadas de tRFC entrada de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)|[Recibir llamadas de tRFC entrante en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)|[Operaciones de entrada de recepción desde el sistema SAP mediante el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|Realización de transacciones en un sistema SAP|[Ejecutar BAPI transacciones en SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)|[Invocar BAPI en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)|[Invocar operaciones en el sistema SAP mediante el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|Enviar un IDOC a un sistema SAP|[Enviar los IDOC a SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)|[Enviar los IDOC a SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)|[Invocar operaciones en el sistema SAP mediante el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|Recibir un IDOC desde un sistema SAP|[Recibir IDOC desde SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)||[Operaciones de entrada de recepción desde el sistema SAP mediante el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  

## <a name="next-steps"></a>Pasos siguientes

 Los temas siguientes proporcionan información sobre los procedimientos y ejemplos para desarrollar aplicaciones que consumen la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tanto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], y [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] programación de soluciones. 

- [Crear una conexión con el sistema SAP.](create-a-connection-to-the-sap-system.md)
- [Obtiene los metadatos para operaciones de SAP en Visual Studio](get-metadata-for-sap-operations-in-visual-studio.md)
- [Trabajar con las propiedades de enlace](read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)
- [Transmisión por secuencias y el adaptador SAP](streaming-and-the-sap-adapter.md)
- [Desarrollar aplicaciones de BizTalk con el adaptador SAP](develop-biztalk-applications-using-the-sap-adapter.md)
- [Desarrollar aplicaciones mediante el modelo de servicio de WCF](develop-sap-applications-using-the-wcf-service-model.md)
- [Desarrollar aplicaciones mediante el modelo de canal de WCF](develop-sap-applications-using-the-wcf-channel-model.md)
- [Obtener metadatos mediante programación](get-metadata-programmatically-from-sap.md)
- [Usar el proveedor de datos de .NET Framework para mySAP](use-the-net-framework-data-provider-for-mysap-business-suite.md)
- [Utilizar el adaptador SAP con SharePoint](use-the-sap-adapter-with-sharepoint.md)
- [Ejemplos](samples-for-the-sap-adapter.md)
- [Utilizar svcutil.exe](use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md) 
 
  
## <a name="see-also"></a>Vea también  
 [Crear el URI de conexión de sistema SAP](create-the-sap-system-connection-uri.md)