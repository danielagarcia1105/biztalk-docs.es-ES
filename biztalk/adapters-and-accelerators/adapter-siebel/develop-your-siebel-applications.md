---
title: Desarrollar sus aplicaciones Siebel en BizTalk Server | Documentos de Microsoft
description: Crear aplicaciones de Siebel mediante WCF, o en el servidor BizTalk Server con el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bc04906-6d64-433c-b357-797ec5883279
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1535a3aa7861effdad998d4d997fbcdfced02c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222604"
---
# <a name="develop-your-siebel-applications"></a>Desarrollar las aplicaciones de Siebel

## <a name="overview"></a>Información general
El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Las aplicaciones cliente pueden utilizar la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para invocar operaciones en artefactos de Siebel. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] pueden utilizarse:  
  
-   A través de un enlace de puerto físico en una solución de BizTalk Server.  
  
-   Mediante la invocación de métodos en una instancia de un proxy de cliente.  
  
-   Como un servicio WCF hospedado.  
  
-   Mediante el envío de mensajes SOAP a través de una instancia de canal en el código que usa el modelo de canal WCF.  
  
-   A través de una interfaz ADO.NET.  
  
## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>Canal de vs de servicio WCF de BizTalk vs WCF frente a ADO.NET
 En la tabla siguiente:  
  
-   Enumera las distintas operaciones que se pueden realizar en un sistema Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
-   Indica cuál de los enfoques ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], modelo, modelo de canal WCF o ADO.NET interfaz de servicio de WCF) puede utilizarse para realizar las operaciones.  
  
-   Proporciona vínculos para obtener más información acerca de cómo realizar la tarea mediante el método elegido.  
  
|Tarea|BizTalk Server|Modelo de servicio WCF|Modelo del canal de WCF|Interfaz de ADO.NET|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|Operaciones básicas Insert, Update, Delete y consulta en los componentes empresariales|[Ejecutar operaciones en componentes empresariales mediante BizTalk Server y el adaptador de Siebel](run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)|[Ejecute las operaciones en los componentes empresariales con el adaptador de Siebel mediante el modelo de servicio de WCF](run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)|[Ejecute las operaciones en los componentes empresariales con el adaptador de Siebel mediante el modelo de canal de WCF](run-tasks-on-business-components-with-the-siebel-adapter-using-a-wcf-channel.md)|[Ejecutar una consulta SELECT en componentes empresariales con Siebel](run-a-select-query-on-business-components-with-siebel.md) **Nota:** sólo se puede realizar una operación SELECT mediante el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].|  
|Operaciones en los componentes empresariales con campos MVG|[Ejecuta operaciones en los componentes empresariales con MVG campos mediante BizTalk Server y el adaptador de Siebel](run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)|[Ejecute las operaciones en los componentes empresariales con campos de MVG con el adaptador de Siebel mediante el modelo de servicio de WCF](work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)|||  
|Operaciones en los componentes empresariales con campos de lista desplegable|[Ejecutar operaciones en los componentes empresariales con campos de lista desplegable mediante BizTalk Server y el adaptador de Siebel](run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)||||  
|Invocar los servicios de negocios|[Invocar métodos de servicio de negocio mediante BizTalk Server y el adaptador de Siebel](invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)|||[Ejecutar una operación de ejecución en los servicios de negocios con Siebel](run-an-execute-operation-on-business-services-with-siebel.md)|  
|Invocar los servicios de negocios con objetos de integración|[Invocar métodos de servicio de negocio con objetos de integración con el adaptador de Siebel](run-business-service-methods-with-integration-objects-using-the-siebel-adapter.md)||||  

## <a name="next-steps"></a>Pasos siguientes  
 Los temas de esta sección proporcionan información, procedimientos y ejemplos que le ayudarán a desarrollar aplicaciones que consumen la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] tanto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] programación de soluciones. 

- [Crear una conexión con el sistema Siebel](create-a-connection-to-the-siebel-system.md)
- [Obtiene los metadatos para operaciones de Siebel en Visual Studio](get-metadata-for-siebel-operations-in-visual-studio.md)
- [Identificadores de nodo de metadatos](metadata-node-ids1.md)
- [Trabajar con las propiedades de enlace](read-about-biztalk-adapter-for-siebel-binding-properties.md)
- [Desarrollar aplicaciones de BizTalk con el adaptador de Siebel](develop-biztalk-applications-using-the-siebel-adapter.md)
- [Desarrollar aplicaciones mediante el modelo de servicio de WCF](develop-siebel-applications-using-the-wcf-service-model.md)
- [Desarrollar aplicaciones mediante el modelo de canal de WCF](develop-siebel-applications-using-the-wcf-channel-model3.md)
- [Usar el proveedor de datos de .NET Framework para aplicaciones Siebel eBusiness](use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
- [Utilizar el adaptador de Siebel con SharePoint](use-the-siebel-adapter-with-sharepoint.md)
- [Ejemplos](samples-for-the-siebel-adapter.md)
- [Usar la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para Siebel eBusiness Applications](use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)