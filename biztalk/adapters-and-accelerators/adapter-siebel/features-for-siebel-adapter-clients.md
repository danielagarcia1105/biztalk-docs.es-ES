---
title: "Características para los clientes de adaptador de Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter features
- features, of the adapter
ms.assetid: 11792629-a692-4378-b522-d33484ee8acb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f929b14415265c4ad9894a16b87294dccd4e906f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="features-for-siebel-adapter-clients"></a>Características para los clientes de adaptador de Siebel
Además de las características tratadas en todos los temas de [información general sobre el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md), el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] proporciona las siguientes características que son útiles para los clientes de adaptador:  
  
-   **Compatibilidad para la configuración de adaptadores que usan propiedades de enlace**. Pueden configurar los clientes de adaptador el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] especificando ciertas propiedades de enlace al generar los metadatos. Para obtener más información, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
-   **Compatibilidad con valores null para los parámetros de operación**. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes de adaptador proporcionar valores null para los parámetros de operación del objeto comercial con el atributo "nillable" XSD. El adaptador no pasar los campos con valores null en el sistema Siebel.  
  
-   **Compatibilidad con el streaming de datos XML**. Los clientes de adaptador pueden transmitir datos desde o hacia el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] mediante el uso de la **XMLReader** o **XMLWriter** interfaces.  
  
-   **Compatibilidad con puertos dinámicos en BizTalk Server**. A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite un puerto dinámico que habilita el enrutamiento dinámico de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje. Para obtener más información, consulte [configurar puertos dinámicos con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/configure-dynamic-ports-with-the-siebel-adapter.md).  
  
-   **Compatibilidad con versiones de mensaje**. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es compatible con las versiones del mensaje. Esto habilita la compatibilidad para esquemas de mensaje diferente en versiones futuras de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [compatibilidad de versiones de mensaje](../../adapters-and-accelerators/adapter-siebel/message-versioning-support2.md).  
  
-   **Compatibilidad con contadores de rendimiento**. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es compatible con los contadores de rendimiento basados en WCF que se pueden usar los clientes de adaptador. Para obtener más información sobre los contadores de rendimiento, consulte [utilizar contadores de rendimiento con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md).  
  
    > [!NOTE]
    >  Esta característica no proporciona compatibilidad con versiones anteriores con las versiones anteriores del adaptador.  
  
-   **Compatibilidad con nombres de elementos XML de codificación**. El[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] presenta las entidades de las aplicaciones empresariales como nombres de elementos en XML. Caracteres de subrayado son los únicos caracteres especiales que se pueden incluir en los nombres de elemento. Por lo tanto, los caracteres de subrayado se usan para codificar los nombres de elemento con caracteres especiales. Por ejemplo, `emp$name` se codifica como `emp_x0024_name`.  
  
## <a name="see-also"></a>Vea también  
 [Información general del adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)