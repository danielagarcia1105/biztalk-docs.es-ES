---
title: Declarar personalizaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- declared customizations
- Z objects, declared customizations
- customizing, Z objects
- customizing, declared customizations
ms.assetid: 484655e9-8bfa-4643-bbe6-4ef69cbd83ad
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 091612d1ad15f7ea841b5936beba1fcf7fc26ddf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988269"
---
# <a name="declared-customizations"></a>Personalizaciones declaradas
Con personalizaciones declaradas, tiene la flexibilidad de modificar o agregar a los mensajes de HL7. Incluso puede definir un nuevo tipo de mensaje. Puede hacerlo en cualquiera de las maneras siguientes:  
  
- Cambiar la definición de un mensaje mediante la definición de un nuevo evento de desencadenador o de tipo de mensaje  
  
- Agregar un nuevo segmento a un tipo de mensaje existente  
  
- Cambiar el tipo de datos de un elemento de mensaje existente (segmento, el campo, componente o subcomponente)  
  
- Cambiar los valores posibles que puede usar en una parte de mensaje existente  
  
  > [!NOTE]
  >  Puede cambiar los valores de enumeración que se usan en objetos de Z declarados o el estándar en los esquemas de HL7. Para ello, consulte [extender las enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).  
  
  Modificar o agregar a los mensajes de HL7 agregando, mantener y asociar objetos personalizados dentro de los tipos de mensaje definidos actualmente. Los estándares de HL7 llamar a estos objetos personalizados "Objetos de Z" para distinguirlos de los objetos existentes que cumplen el estándar HL7. Utilice el Editor de BizTalk para definir objetos de Z. También se pueden utilizar el Editor de BizTalk para trabajar con las características que propagan las actualizaciones a un objeto Z entre todos los eventos de desencadenador y los mensajes abstractos que incluyen. Para obtener más información acerca de cómo crear objetos de Z, consulte [esquemas de ampliación de HL7 2.X con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md).  
  
  Puede utilizar objetos de Z para proporcionar a las definiciones locales para los segmentos que se usen de maneras que no se especifica en el estándar HL7. Realizar estos cambios en los esquemas que el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) instalado en el equipo Asistente para instalación. Estos esquemas modificados, a continuación, puede compartir con otros [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] instalaciones con la que intercambia mensajes.  
  
## <a name="types-of-z-objects"></a>Tipos de objetos de Z  
 El estándar HL7 (2.X) actualmente admite las siguientes formas de personalización:  
  
-   **Eventos de desencadenador personalizado.** Si están en un área local y necesita una nueva estructura de mensaje, o si desea admitir un evento de desencadenador que no se incluye dentro del estándar, puede crear un nuevo evento de desencadenador con un prefijo de Z, por ejemplo, Z05. En este caso, debe crear un nuevo esquema de mensaje local mediante la definición del mensaje abstracto y el patrón de segmentos incluidos.  
  
-   **Segmentos personalizados.** Si se encuentra en un área local, en el contexto de un evento de desencadenador ya eran compatibles y que necesitan datos adicionales, puede crear un nuevo segmento o segmentos e incluyen los elementos de datos deseado en el segmento. Debe especificar los elementos dentro del segmento con tipos de datos existentes de HL7. Puede crear segmentos de Z personalizados en el Editor de BizTalk, mediante la creación de un nuevo registro en el esquema. Para obtener más información, consulte [crear segmentos Z declarados](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md). Como alternativa, puede agregar un segmento de Z a través de la base de datos de Access y, a continuación, agregar ese segmento de Z a la estructura del mensaje. Para obtener más información, consulte [resolver errores de base de datos](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).  
  
-   **Subtipos de datos personalizados.** HL7 proporciona una lista de tipos de datos admitidos, por ejemplo, texto con formato, examina la imagen, los datos de audio. Sin embargo, si desea definir tipos de datos adicionales, puede hacerlo creando un datos Z escriba anteponiendo la tecla de acceso que se utiliza con una "Z".  
  
    > [!NOTE]
    >  No está permitido dentro de los confines del estándar, para crear nuevos tipos de datos o agregar elementos a un segmento existente. Aún menor es admisible para aceptar un elemento que no se utiliza actualmente y volver a definirlo para satisfacer cualquier propósito adicional. Por otro lado, las organizaciones que admiten las interfaces heredadas que deba dar cabida a estas prácticas.  
  
-   **Tablas personalizadas.** Muchos objetos existentes en los mensajes tienen un intervalo limitado de valores específicos, tal como se define mediante enumeraciones en tablas definidas por esquemas comunes de HL7. Puede modificar estas enumeraciones para habilitar valores adicionales mediante la creación de tablas de Z.  
  
## <a name="see-also"></a>Vea también  
 [Personalizaciones no declaradas](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)   
 [Extender esquemas HL7 2.X con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)