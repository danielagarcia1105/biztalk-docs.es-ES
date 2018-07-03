---
title: Las características del adaptador de SAP clave | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, deprecated features
- features, technology-related
- adapters, new features
- features, deprecated
- features, metadata-related
- librfc32u.dll
- tRFC server
- features, new
- adapters, new and deprecated features
- queued tRFC client calls
- features, operations-related
- RFC server
ms.assetid: 30e3140c-447f-42ba-a3b0-13ae66e78b0c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e85f067b53c8a46238e4de343f240cfc2784885
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994573"
---
# <a name="key-features-in-the-sap-adapter"></a>Características clave del adaptador de SAP
Esta sección enumeran las características nuevas y en desuso en [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].  
  
> [!NOTE]
>  En este tema se ha usado desde la versión anterior de [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] ayuda.  
  
## <a name="features-in-the-sap-adapter"></a>Características del adaptador de SAP  
 Los siguientes son las características introducidas en las versiones anteriores de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
### <a name="technology-related-features"></a>Características relacionadas con la tecnología  
  
|                                                            Característica                                                             |                                                                                                                                                                                                                                                                                              Comentario                                                                                                                                                                                                                                                                                               |
|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SQL Server Reporting Services (SSRS). | Ahora pueden usar los programas cliente el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] para importar datos desde un back-end SAP en un proyecto SSRS y generar informes fuera de los datos. Para obtener más información sobre cómo usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SSRS, consulte [usar el proveedor de datos para SAP con SSRS](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md). Para obtener más información acerca de SSRS, consulte [SQL Server Reporting Services](https://msdn.microsoft.com/library/ms159106.aspx). |
|                                     Soporte técnico para invocar consultas definidas en un sistema SAP                                      |                                                                                                                                                           La [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] expone una operación, EXECQUERY, que puede utilizarse para ejecutar las consultas definidas en un sistema SAP. Para obtener más información sobre cómo usar la característica EXECQUERY, vea [compatibilidad para ejecutar consultas de SAP                                                                                                                                                            |

](https://msdn.microsoft.com/library/dd788118.aspx).|  
|Compatibilidad para usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Microsoft Office SharePoint Server (MOSS) | Puede utilizar los adaptadores para presentar los datos desde el sistema SAP en un portal MOSS. Para obtener más información, consulte [utilizar el adaptador de SAP con SharePoint](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md). |  
  
### <a name="metadata-related-features"></a>Características relacionadas con metadatos  
  
|                Característica                 |                                                                                                                                                                                                                                                                                                   Comentario                                                                                                                                                                                                                                                                                                    |
|----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **DataTypesBehavior** enlazar la propiedad | El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] proporciona una propiedad de enlace complejo **DataTypesBehavior**, que permite a los clientes del adaptador controlar el comportamiento del adaptador cuando se encuentran valores especiales en el sistema SAP. Para obtener una explicación detallada acerca de esta propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md). |
  
### <a name="operations-related-features"></a>Características relacionadas con las operaciones  
  
|                          Característica                          |                                                                                                                                                                                                                                                 Comentario                                                                                                                                                                                                                                                  |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Soporte técnico para invocar programas externos requeridos por una solicitud de cambio | El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] proporciona una propiedad de enlace, **RfcAllowStartProgram** que se pueden establecer para habilitar la biblioteca de cliente RFC invocar programas externos, si existe, requiere una RFC determinada. Para obtener más información acerca de esta propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md). |
|    Compatibilidad para enviar varios IDOC en una sola llamada    |                                                                                                                                                                                                      El adaptador SAP admite ahora el envío de IDOC múltiples del mismo tipo en una llamada única del adaptador.                                                                                                                                                                                                      |
  
### <a name="other-features"></a>Otras características  
  
|                                                        Característica                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                Comentario                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|-----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nueva forma de utilizar el adaptador en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] | El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF SAP en BizTalk. Si desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto de WCF-Custom, es necesario agregar el puerto de WCF-Custom para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto de SAP de WCF, primero debe agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener más información, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md). |
  
## <a name="deprecated-features-in-the-sap-adapter"></a>Características en desuso en el adaptador de SAP  
 Las secciones siguientes se enumeran las características que se admitían en la versión anterior del adaptador, pero que no se admiten en la versión actual de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
### <a name="enablebusinessobjects-binding-property-deprecated"></a>Propiedad de enlace EnableBusinessObjects en desuso  
 Esta propiedad de enlace ha quedado obsoleta en [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Esta propiedad de enlace se usa para determinar si se muestra el nodo BAPI durante la generación de metadatos al usar [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Definición del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)