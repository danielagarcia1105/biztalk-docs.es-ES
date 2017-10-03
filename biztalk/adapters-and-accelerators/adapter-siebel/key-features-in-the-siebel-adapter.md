---
title: "Características en el adaptador de Siebel clave | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- features, performance-related
- adapter features, new
- features, technology-related
- features, metadata-related
- adapter features, operations-related
- adapter features, performance-related
- features, new
- features, operations-related
- adapter features, metadata-related
ms.assetid: 4612c9ab-810e-4c69-9168-a25c58682e71
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 295ff8b13358109a5d4737fb5f9325b3c9caa0f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-the-siebel-adapter"></a>Características clave en el adaptador de Siebel
Esta sección enumeran las nuevas características de [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].  
  
> [!NOTE]
>  En este tema se ha utilizado desde la versión anterior de [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] ayuda.  
  
## <a name="new-features-in-the-siebel-adapter"></a>Nuevas características en el adaptador de Siebel  
 Los siguientes son las nuevas características introducidas en esta versión de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
### <a name="technology-related-features"></a>Características relacionadas con la tecnología  
  
|Característica|Comentario|  
|-------------|-------------|  
|Compatibilidad para usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Microsoft Office SharePoint Server (MOSS)|Puede utilizar los adaptadores para presentar los datos en el sistema Siebel en un portal MOSS. Para obtener más información, consulte [usa el adaptador de Siebel con Microsoft Office SharePoint Server](https://msdn.microsoft.com/library/dd788017.aspx).|  
  
### <a name="operations-related-features"></a>Características relacionadas con las operaciones  
  
|Característica|Comentario|  
|-------------|-------------|  
|Soporte para la operación de asociación en componentes empresariales|Los clientes de adaptador pueden asociar registros especificando expresiones de búsqueda primarios y secundarios. Esto es aplicable sólo para los componentes empresariales con campos de grupo con varios valores (MVG). Tenga en cuenta que las expresiones de búsqueda deben utilizar un filtro exactamente un registro para el elemento primario y el secundario componentes empresariales.|  
|Soporte para la operación de DESASOCIAR en componentes empresariales|Los clientes de adaptador pueden anular la asociación de registros mediante la especificación de expresiones de búsqueda primarios y secundarios. Esto es aplicable sólo para los componentes empresariales con campos de grupo con varios valores (MVG). Tenga en cuenta que las expresiones de búsqueda deben filtrar exactamente un registro para el elemento primario y el secundario componentes empresariales.|  
|Compatibilidad con las consultas de vínculo con varios valores|Los clientes de adaptador pueden consultar los registros secundarios asociados a un registro primario especificando el registro primario y el nombre del campo con varios valores. Esto es aplicable sólo para los componentes empresariales con campos de grupo con varios valores (MVG).|  
  
### <a name="other-features"></a>Otras características  
  
|Característica|Comentario|  
|-------------|-------------|  
|Nueva forma de utilizar el adaptador en[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]|La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF-Siebel en BizTalk. Si desea utilizar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto personalizado de WCF, no es necesario agregar el puerto personalizado de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto de WCF-Siebel, primero debe agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener más información, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).|  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)