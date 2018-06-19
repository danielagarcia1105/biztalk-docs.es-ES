---
title: Extender HL7 2.X esquemas con objetos de Z | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, Z objects
- Z objects, extending 2.X schemas
ms.assetid: 0980d919-eb81-4c65-b0f7-f17f7cfef6b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27ef2bea3e13904f04449a5b77d05672c2b2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204660"
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a>Extender HL7 2.X esquemas con objetos de Z
La organización de HL7 define HL7 2.X esquemas y se espera que todos los remitentes y receptores reconocer y utilizar estos esquemas, tal y como define la organización. Conforme a los esquemas garantiza para la interoperabilidad. Sin embargo, el estándar HL7 le permite personalizar HL7 existente 2.X esquemas para sus fines locales específicos. También puede definir objetos y esquemas completamente nuevos. Para ello, con qué las HL7 estándares llamadas a objetos de Z.  
  
 El estándar HL7 no define el valor de los objetos de Z. Los esquemas de HL7 publicados no incluirlos. Definirlos localmente y usarlos de acuerdo con todas las partes locales. La organización de HL7 reserva todos los tipo de mensaje, evento de desencadenador, segmento, tipo de datos y los nombres de tabla que empiezan por "Z" para este uso local. Por el prefijo, el estándar HL7 llama a estos objetos de objetos definidos por el sitio Z.  
  
> [!NOTE]
>  Cuando se agrega un objeto de Z en un esquema definido de HL7 existente, puede acabar con varias versiones de ese esquema. La mejor manera de controlar estos varias versiones consiste en utilizar la característica de Namespace en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. Puede encontrar esta característica en el **validación** ficha [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración (en el nivel de entidad). También necesitará cambiar la propiedad de espacio de nombres del esquema que se implementan para ese proyecto.  
  
 Al crear o procesar Z objetos, debe seguir las reglas que haya establecido la organización HL7 para objetos de Z...  
  
 Al agregar un objeto de Z en un esquema existente o crear un nuevo esquema de mensaje de Z, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usará el esquema con los objetos de Z para procesar el mensaje con codificación HL7. Este tipo de objeto de Z es un objeto declarado de Z. También puede usar un segmento de Z no declarado, que el motor de integración no se procesará según el esquema de mensaje. Para obtener más información acerca de este tipo de segmento de Z, consulte [control no declarado Z segmentos](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Crear segmentos de Z declarado](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [Crear tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [Crear tablas personalizadas en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [Extender las enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [Personalización de mensajes a través de objetos de Z](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)