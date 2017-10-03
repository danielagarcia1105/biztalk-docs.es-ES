---
title: Formas de utilizar el contenido del mensaje para controlar el procesamiento de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1e3792e-9cd4-42b6-8b9d-3c2a022a16d6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73d356496d07bb2227aa514ee68f2a2a51e2291b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a>Modos de usar el contenido de los mensajes para controlar el procesamiento de los mensajes
Hay dos tipos de promoción de propiedades: **campos distintivos** y **campos de propiedades**, la última de las cuales utiliza esquemas de propiedades. En el Editor de BizTalk, administra estos dos tipos de promoción de propiedades mediante la **promocionar propiedades** cuadro de diálogo, que es accesible mediante la **promocionar propiedades** propiedad de la  **Esquema** nodo.  
  
> [!NOTE]
>  Existen algunas restricciones en cuanto a los valores que puede promocionar. Para obtener más información, vea la tabla de [promocionar propiedades](../core/promoting-properties.md).  
  
 Debe decidir el tipo de promoción de propiedades que usará según los detalles de la situación concreta. Tenga en cuenta las siguientes diferencias entre **campo distintivo** promoción de propiedades y **campo de propiedad** promoción de propiedades:  
  
-   **Campos distintivos** no puede participar en el enrutamiento de mensajes y, por tanto, no aparecen en las expresiones de filtro. Solo están disponibles dentro del contexto de una orquestación, pero tienen menos sobrecarga al enviar o recibir mensajes.  
  
-   **Campos distintivos** no tiene ninguna limitación de tamaño. **Campos de propiedades** se limitan a 255 caracteres.  
  
-   **Campos distintivos** no requieren ningún independientes que se creen artefactos, mientras que **campos de propiedades** requieren la creación y mantenimiento de un esquema de propiedad.  
  
 Considerando lo anterior, debe promocionar los nodos como **campos de propiedades** sólo cuando se tiene pensado usar las propiedades promocionadas para enrutamiento de mensajes o con fines de seguimiento. En caso contrario, si sólo va a tener acceso a las propiedades promocionadas desde las orquestaciones, se deben aprovechar el hecho de que **campos distintivos** son mucho más económicos, más ligeros y más fácil de usar que  **Campos de propiedades**.  
  
 Propiedades promocionadas mediante la **campo distintivo** mecanismo solo son accesible desde dentro de las orquestaciones y no se puede tener acceso desde canalizaciones, puertos y así sucesivamente. Por otro lado, propiedades promocionan mediante la **campos de propiedades** y mecanismo de esquema de propiedad sean accesibles desde todos estos componentes. Otra diferencia importante es que los valores de los campos de propiedades tienen una limitación de 255 caracteres y que los de los campos distintivos no tienen dicha limitación.  
  
 En esta sección se proporciona información acerca de estos dos tipos de promoción de propiedades, incluida la información acerca de cómo establecer dichas propiedades promocionadas para un esquema de mensaje mediante el Editor de BizTalk.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Acerca de las propiedades de contexto de mensaje de BizTalk](../core/about-biztalk-message-context-properties.md)  
  
-   [Procesamiento de mensajes de instancia con campos distintivos](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [Procesamiento de mensajes de instancia con promoción de propiedades](../core/instance-message-processing-using-property-promotion.md)