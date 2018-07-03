---
title: Características para los clientes del adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- features, of the adapter
ms.assetid: 11792629-a692-4378-b522-d33484ee8acb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29d461b5ac656b9f3b84e58d0ecb2d4e6b5cff5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004453"
---
# <a name="features-for-siebel-adapter-clients"></a>Características para los clientes del adaptador de Siebel
Además de las características se tratan en los temas de [información general sobre el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md), el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] proporciona las siguientes características son útiles para los clientes del adaptador:  
  
- **Compatibilidad con la configuración de los adaptadores que usan propiedades de enlace**. Pueden configurar los clientes del adaptador el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] especificando ciertas propiedades de enlace al generar los metadatos. Para obtener más información, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
- **Compatibilidad con valores null para los parámetros de operación**. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] permite a los clientes del adaptador proporcionar valores nulos para parámetros de operación del objeto comercial con el atributo "nillable" XSD. El adaptador no pasar los campos con valores null al sistema Siebel.  
  
- **Compatibilidad con el streaming de datos XML**. Los clientes del adaptador pueden transmitir datos desde o hacia la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] utilizando el **XMLReader** o **XMLWriter** interfaces.  
  
- **Compatibilidad con puertos dinámicos en BizTalk Server**. A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es compatible con un puerto dinámico que permite el enrutamiento dinámico de los mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje. Para obtener más información, consulte [configurar puertos dinámicos con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/configure-dynamic-ports-with-the-siebel-adapter.md).  
  
- **Compatibilidad con versiones de mensaje**. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite mensajes de control de versiones. Esto habilita la compatibilidad con esquemas de mensaje diferente en versiones futuras de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [compatibilidad de versiones de mensaje](../../adapters-and-accelerators/adapter-siebel/message-versioning-support2.md).  
  
- **Compatibilidad con contadores de rendimiento**. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es compatible con los contadores de rendimiento basados en WCF que pueden usar los clientes del adaptador. Para obtener más información sobre los contadores de rendimiento, consulte [usar contadores de rendimiento con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md).  
  
  > [!NOTE]
  >  Esta característica no proporciona compatibilidad con versiones anteriores con las versiones anteriores del adaptador.  
  
- **Compatibilidad con la codificación de nombres de elementos XML**. El[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] presenta las entidades de aplicaciones empresariales como nombres de elemento XML. Caracteres de subrayado son los únicos caracteres especiales que pueden incluirse en los nombres de elemento. Por lo tanto, los caracteres de subrayado se usan para codificar los nombres de elemento con los caracteres especiales. Por ejemplo, `emp$name` se codifica como `emp_x0024_name`.  
  
## <a name="see-also"></a>Vea también  
 [Información general del adaptador de BizTalk para las aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)