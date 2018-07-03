---
title: Las características del adaptador de Siebel clave | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4896256555ea6b721d917c992c9c41fd3737f101
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018331"
---
# <a name="key-features-in-the-siebel-adapter"></a>Características clave del adaptador de Siebel
Esta sección enumeran las nuevas características de [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].  
  
> [!NOTE]
>  En este tema se ha usado desde la versión anterior de [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] ayuda.  
  
## <a name="new-features-in-the-siebel-adapter"></a>Nuevas características del adaptador de Siebel  
 Los siguientes son las nuevas características introducidas en esta versión de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
### <a name="technology-related-features"></a>Características relacionadas con la tecnología  
  
|                                                                    Característica                                                                     |                                                                                                               Comentario                                                                                                               |
|------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Compatibilidad para usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Microsoft Office SharePoint Server (MOSS) | Puede usar los adaptadores para presentar los datos en el sistema Siebel en un portal MOSS. Para obtener más información, consulte [con el adaptador de Siebel con Microsoft Office SharePoint Server](https://msdn.microsoft.com/library/dd788017.aspx). |
  
### <a name="operations-related-features"></a>Características relacionadas con las operaciones  
  
|Característica|Comentario|  
|-------------|-------------|  
|Soporte técnico para la operación de asociación en componentes empresariales|Pueden asociar a los clientes del adaptador registros mediante la especificación de las expresiones de búsqueda para el elemento primario y secundario. Esto sólo es aplicable para los componentes de negocio con los campos de grupo con varios valores (MVG). Tenga en cuenta que las expresiones de búsqueda deben filtrar exactamente un registro para los componentes empresariales primario o secundario.|  
|Soporte técnico para la operación de DESASOCIAR en componentes empresariales|Los clientes del adaptador pueden desasociar registros mediante la especificación de las expresiones de búsqueda para el elemento primario y secundario. Esto sólo es aplicable para los componentes de negocio con los campos de grupo con varios valores (MVG). Tenga en cuenta que las expresiones de búsqueda deben filtrar exactamente un registro para los componentes empresariales primario o secundario.|  
|Compatibilidad con las consultas de vínculo con varios valores|Los clientes del adaptador pueden consultar los registros secundarios asociados con un registro principal especificando el registro primario y el nombre del campo multivalor. Esto sólo es aplicable para los componentes de negocio con los campos de grupo con varios valores (MVG).|  
  
### <a name="other-features"></a>Otras características  
  
|                                                        Característica                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Comentario                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nueva forma de utilizar el adaptador en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] | El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF-Siebel en BizTalk. Si desea usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto de WCF-Custom, es necesario agregar el puerto de WCF-Custom para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto de WCF-Siebel, primero debe agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener más información, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md). |
  
## <a name="see-also"></a>Vea también  
 [Definición del adaptador de BizTalk para las aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)