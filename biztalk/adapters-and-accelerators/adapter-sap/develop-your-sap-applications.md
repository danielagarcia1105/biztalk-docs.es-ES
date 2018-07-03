---
title: Desarrollar aplicaciones de SAP mediante el adaptador de BizTalk | Microsoft Docs
description: Creación de mis aplicaciones de SAP mediante WCF, BizTalk Server o ADO.NET con el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, use adapters
- adapters, working with
- working with adapters
ms.assetid: e8315c0d-923b-433e-9d11-4e8a53e0a1d9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a023f3890eff7b3b8c846f0c2c3e15cda4c1d35
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003165"
---
# <a name="develop-your-sap-applications"></a>Desarrollar aplicaciones de SAP

## <a name="overview"></a>Información general
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Las aplicaciones cliente pueden consumir el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para invocar operaciones en los artefactos SAP. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] pueden utilizarse:  
  
- A través de un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Mediante la invocación de métodos en una instancia de un proxy de cliente.  
  
- Como un servicio WCF hospedado.  
  
- Mediante el envío de mensajes SOAP a través de una instancia de canal en el código que usa el modelo de canal WCF.  
  
- A través de una interfaz ADO.NET.  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>Canal de vs de servicio WCF de BizTalk vs WCF frente a ADO.NET
  
 En la tabla siguiente:  
  
- Enumera las distintas operaciones que se pueden realizar en un sistema SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
- Indica cuál de los enfoques ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], modelo, modelo de canal WCF o ADO.NET interfaz de servicio de WCF) se puede usar para realizar las operaciones.  
  
- Proporciona vínculos para obtener más información acerca de cómo realizar la tarea mediante el enfoque elegido.  
  
|Tarea|BizTalk Server|Modelo de servicio WCF|Modelo del canal de WCF|Interfaz de ADO.NET|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|Invocar RFC en un sistema SAP|[Invocar RFC de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)|[Invocar RFC de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)|[Invocar operaciones en el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)|[Invocar RFC y BAPI mediante el comando EXEC en SAP](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)|  
|Recibir las llamadas entrantes de RFC de un sistema SAP|[Recibir llamadas de RFC de entrada de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)|[Recibir llamadas entrantes de RFC de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)|[Recibir operaciones de entrada desde el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|Invocar trfc en un sistema SAP|[Invocar trfc de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)|[Invocar trfc de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)|[Invocar operaciones en el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|Recibir llamadas de tRFC de entrada de un|[Recibir llamadas de tRFC de entrada de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)|[Recibir llamadas de tRFC de entrada de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)|[Recibir operaciones de entrada desde el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|Realización de transacciones en un sistema SAP|[Ejecutar transacciones de BAPI de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)|[Invocar BAPI de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)|[Invocar operaciones en el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|Enviar un IDOC a un sistema SAP|[Enviar los IDOC a SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)|[Enviar los IDOC a SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)|[Invocar operaciones en el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|Recibir un IDOC desde un sistema SAP|[Recibir los IDOC desde SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)||[Recibir operaciones de entrada desde el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  

## <a name="next-steps"></a>Pasos siguientes

 Los temas siguientes proporcionan información sobre los procedimientos y ejemplos para desarrollar aplicaciones que consumen el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tanto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], y [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] programación de soluciones. 

- [Crear una conexión con el sistema de SAP](create-a-connection-to-the-sap-system.md)
- [Obtener metadatos para operaciones de SAP en Visual Studio](get-metadata-for-sap-operations-in-visual-studio.md)
- [Trabajar con las propiedades de enlace](read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)
- [Streaming y el adaptador de SAP](streaming-and-the-sap-adapter.md)
- [Desarrollar aplicaciones de BizTalk con el adaptador de SAP](develop-biztalk-applications-using-the-sap-adapter.md)
- [Desarrollar aplicaciones con el modelo de servicio WCF](develop-sap-applications-using-the-wcf-service-model.md)
- [Desarrollar aplicaciones con el modelo de canal WCF](develop-sap-applications-using-the-wcf-channel-model.md)
- [Obtener metadatos mediante programación](get-metadata-programmatically-from-sap.md)
- [Usar el proveedor de datos de .NET Framework para mySAP](use-the-net-framework-data-provider-for-mysap-business-suite.md)
- [Usar el adaptador de SAP con SharePoint](use-the-sap-adapter-with-sharepoint.md)
- [Ejemplos](samples-for-the-sap-adapter.md)
- [Usar svcutil.exe](use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md) 
 
  
## <a name="see-also"></a>Vea también  
 [Crear el URI de conexión del sistema SAP](create-the-sap-system-connection-uri.md)