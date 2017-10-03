---
title: Declara las personalizaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- declared customizations
- Z objects, declared customizations
- customizing, Z objects
- customizing, declared customizations
ms.assetid: 484655e9-8bfa-4643-bbe6-4ef69cbd83ad
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 767fdd543b1cb5d87bf3ec1c1943ac81d91c6ea4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="declared-customizations"></a>Personalizaciones declaradas
Con personalizaciones declaradas, tiene la flexibilidad de modificar o agregar a los mensajes de HL7. Incluso puede definir un nuevo tipo de mensaje. Puede hacerlo en cualquiera de las maneras siguientes:  
  
-   Cambiar la definición de un mensaje mediante la definición de un nuevo evento de tipo o un desencadenador de mensaje  
  
-   Agregar un segmento nuevo a un tipo de mensaje existente  
  
-   Cambiar el tipo de datos de un elemento de mensaje existente (segmento, campo, componente o subcomponente)  
  
-   Cambiar los valores posibles que puede usar en un elemento de mensaje existente  
  
    > [!NOTE]
    >  Puede cambiar los valores de enumeración que se usan en objetos declarados de Z o los objetos estándares de esquemas de HL7. Para ello, consulte [extender enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).  
  
 Modificar o agregar a los mensajes HL7 agregando, mantener y asociar objetos personalizados dentro de los tipos de mensaje definidos actualmente. Los estándares de HL7 llamar a estos objetos personalizados "Objetos Z" para distinguirlos de los objetos existentes que cumplen el estándar HL7. Use el Editor de BizTalk para definir objetos de Z. Usar el Editor de BizTalk para trabajar con características que propagan las actualizaciones a un objeto de Z a través de todos los eventos de desencadenador y mensajes abstractos que incluyen. Para obtener más información acerca de cómo crear objetos de Z, consulte [extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md).  
  
 Puede usar objetos de Z para proporcionar las definiciones de locales a segmentos que utilizan de maneras que no se especifica en el estándar HL7. Realizar estos cambios en los esquemas que el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) instalado en el equipo Asistente para instalación. A continuación, puede compartir estos esquemas modificados con otros [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] instalaciones con la que intercambia mensajes.  
  
## <a name="types-of-z-objects"></a>Tipos de objetos de Z  
 Actualmente, el estándar HL7 (2.X) es compatible con las siguientes formas de personalización:  
  
-   **Eventos de desencadenador personalizado.** Si están en un área local y necesita una nueva estructura de mensaje, o para admitir un evento de desencadenador que no está incluido en el estándar, puede crear un nuevo evento de desencadenador utilizando un prefijo de Z, por ejemplo, Z05. En este caso, debe crear un nuevo esquema de mensaje local mediante la definición del mensaje abstracto y el patrón de segmentos incluidos.  
  
-   **Segmentos personalizados.** Si se encuentra en un área local, en el contexto de un evento de desencadenador ya admitidos y que necesita datos adicionales, puede crear un nuevo segmento o segmentos e incluyen los elementos de datos deseado en el segmento. Debe especificar los elementos dentro del segmento con los tipos de datos existentes de HL7. Puede crear segmentos de Z personalizados en el Editor de BizTalk, mediante la creación de un nuevo registro en el esquema. Para obtener más información, consulte [crear segmentos de Z declara](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md). Como alternativa, puede agregar un segmento de Z a través de la base de datos de Access y, a continuación, agregar ese segmento de Z a la estructura del mensaje. Para obtener más información, consulte [resolver errores de base de datos](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).  
  
-   **Subtipos de datos personalizados.** HL7 proporciona una lista de tipos de datos admitidos, por ejemplo, con el formato de texto, imagen, audio datos digitalizada. Sin embargo, si desea definir tipos de datos adicionales, puede hacerlo así, anteponiendo la tecla de acceso que se utiliza con una "Z", creando así una datos Z de tipo.  
  
    > [!NOTE]
    >  No está permitido dentro de los límites del estándar, para crear nuevos tipos de datos o para agregar elementos a un segmento existente. Aún menor es admisible para sacar un elemento que no se utiliza actualmente y para volver a definirla para cumplir algunos propósito adicional. Por otro lado, las organizaciones que admiten las interfaces heredadas que necesite dar cabida a tales prácticas.  
  
-   **Tablas personalizadas.** Muchos de los objetos existentes en los mensajes tienen un intervalo limitado de valores específicos, tal como se define mediante enumeraciones en tablas definidas por esquemas comunes de HL7. Puede modificar estas enumeraciones para habilitar valores adicionales mediante la creación de tablas de Z.  
  
## <a name="see-also"></a>Vea también  
 [Personalizaciones no declaradas](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)   
 [Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)