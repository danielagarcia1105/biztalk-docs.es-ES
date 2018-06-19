---
title: Características en el adaptador SAP clave | Documentos de Microsoft
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
ms.openlocfilehash: 4b34a695e34f617f6444b728e92cb544f91448c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218388"
---
# <a name="key-features-in-the-sap-adapter"></a>Características clave en el adaptador SAP
Esta sección enumeran las características nuevas y en desuso en [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].  
  
> [!NOTE]
>  En este tema se ha utilizado desde la versión anterior de [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] ayuda.  
  
## <a name="features-in-the-sap-adapter"></a>Características en el adaptador SAP  
 Los siguientes son las características introducidas en las versiones anteriores de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
### <a name="technology-related-features"></a>Características relacionadas con la tecnología  
  
|Característica|Comentario|  
|-------------|-------------|  
|Con la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SQL Server Reporting Services (SSRS).|Los programas cliente ahora pueden usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] para importar datos desde un back-end SAP en un proyecto SSRS y generar informes fuera de los datos. Para obtener más información sobre cómo usar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] con SSRS, consulte [usa el proveedor de datos para SAP con SSRS](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md). Para obtener más información acerca de SSRS, consulte [SQL Server Reporting Services](https://msdn.microsoft.com/library/ms159106.aspx).|  
|Soporte técnico para invocar las consultas definidas en un sistema SAP|La [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] expone una operación, EXECQUERY, que puede utilizarse para ejecutar las consultas definidas en un sistema SAP. Para obtener más información sobre cómo usar la característica EXECQUERY, consulte [compatibilidad para ejecutar consultas de SAP

](https://msdn.microsoft.com/library/dd788118.aspx).|  
|Compatibilidad para usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Microsoft Office SharePoint Server (MOSS) | Puede utilizar los adaptadores para presentar los datos desde el sistema SAP en un portal MOSS. Para obtener más información, consulte [utilizar el adaptador de SAP con SharePoint](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md). |  
  
### <a name="metadata-related-features"></a>Características relacionadas con metadatos  
  
|Característica|Comentario|  
|-------------|-------------|  
|**DataTypesBehavior** propiedad de enlace|El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] proporciona una propiedad de enlace complejo, **DataTypesBehavior**, que permite a los clientes de adaptador controlar el comportamiento del adaptador cuando se encuentran valores especiales en el sistema SAP. Para obtener una explicación detallada acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).|  
  
### <a name="operations-related-features"></a>Características relacionadas con las operaciones  
  
|Característica|Comentario|  
|-------------|-------------|  
|Soporte técnico para invocar programas externos necesarios para una solicitud de cambio|El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] proporciona una propiedad de enlace, **RfcAllowStartProgram** que se pueden establecer para habilitar la biblioteca de cliente RFC invocar programas externos, si lo hubiera, requiere una RFC determinada. Para obtener más información acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).|  
|Compatibilidad para enviar varios IDOC en una sola llamada|El adaptador SAP admite ahora el envío varios IDOC del mismo tipo en una llamada única del adaptador.|  
  
### <a name="other-features"></a>Otras características  
  
|Característica|Comentario|  
|-------------|-------------|  
|Nueva forma de utilizar el adaptador en[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]|La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF SAP en BizTalk. Si desea utilizar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto personalizado de WCF, no es necesario agregar el puerto personalizado de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto de SAP de WCF, primero debe agregar el adaptador SAP de WCF para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener más información, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).|  
  
## <a name="deprecated-features-in-the-sap-adapter"></a>Características en desuso en el adaptador SAP  
 En las secciones siguientes se enumeran las características que se admiten en la versión anterior del adaptador, pero que no se admiten en la versión actual de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
### <a name="enablebusinessobjects-binding-property-deprecated"></a>Propiedad de enlace de EnableBusinessObjects en desuso  
 Esta propiedad de enlace ha quedado obsoleta en [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Esta propiedad de enlace se usa para determinar si se muestra el nodo BAPI durante la generación de metadatos al usar [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)