---
title: "Los pasos del desarrollo de una orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- designing, orchestrations
- orchestrations, designing
- orchestrations, creating
- creating, orchestrations
- Copy Local property
ms.assetid: 556b1e6c-63a6-4805-a0a5-e555f198fe4e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd0a19754871a6e736365e622513b193dcbf06a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="steps-in-orchestration-development"></a>Pasos del desarrollo de una orquestación
Para desarrollar una orquestación, normalmente se realizan las acciones básicas siguientes:  
  
-   Agregar formas para representar los procesos empresariales  
  
     El Diseñador de orquestaciones proporciona un cuadro de herramientas de formas que se puede utilizar para representar diferentes acciones u otras abstracciones. Para obtener más información, consulte [formas de orquestación](../core/orchestration-shapes.md).  
  
-   Definir esquemas para describir el formato de los mensajes  
  
     Puede definir esquemas con el Editor de BizTalk. Para obtener más información, consulte [cómo crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md).  
  
-   Definir los puertos a través de los que se envían y se reciben los mensajes  
  
     Puede definir puertos para especificar cómo y dónde se envían y reciben los mensajes. Para obtener más información, consulte [mediante puertos en orquestaciones](../core/using-ports-in-orchestrations.md).  
  
-   Enlazar **enviar** y **recepción** formas a puertos.  
  
     Puede conectar su **enviar** y **recepción** formas a puertos y especificar las operaciones de puerto que utilizan. Para obtener más información, consulte [cómo configurar la forma envío](../core/how-to-configure-the-send-shape.md). Consulte también [cómo configurar la forma recepción](../core/how-to-configure-the-receive-shape.md).  
  
-   Asignar o transformar datos entre mensajes  
  
     Puede usar el **construir mensaje** forma para asignar valores de mensaje o realizar transformaciones de mensajes. Para obtener más información, consulte [construir mensajes](../core/constructing-messages.md).  
  
-   Identificar cualquier componente personalizado que quizás desee escribir o agregar como referencia para trabajar en su orquestación  
  
> [!NOTE]
>  Si el **Copy Local** propiedad del ensamblado que se hace referencia está establecida en **True**, orquestación no será posible recoger los cambios realizados en el ensamblado externo después de la referencia del complemento inicial realiza Proyecto de BizTalk.  
  
-   Definir y asignar variables de orquestación para administrar datos en la orquestación que se está ejecutando  
  
     Puede utilizar la carpeta Variables de la ventana Vista orquestación para declarar las variables de orquestación, y el Editor de expresiones de BizTalk para editar expresiones que asignan y utilizan las variables en varias formas. Para obtener más información, consulte [tipos de datos de XLANG-s](../core/xlang-s-data-types.md).  
  
-   Generar la orquestación para comprobar su integridad  
  
     La orquestación se genera al compilar el proyecto o la solución que la contiene. Para obtener más información, consulte [cómo generar orquestaciones](../core/how-to-build-orchestrations.md).  
  
## <a name="see-also"></a>Vea también  
 [Generar y ejecutar orquestaciones](../core/building-and-running-orchestrations.md)   
 [Administrar orquestaciones](../core/managing-orchestrations.md)   
 [Crear orquestaciones mediante el Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md)