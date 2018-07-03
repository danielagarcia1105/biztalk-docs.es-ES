---
title: Formas de usar el contenido del mensaje para controlar el procesamiento de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e3792e-9cd4-42b6-8b9d-3c2a022a16d6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0036b9b16faf64d0768d2d5cc7ce1f828cfbffe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009365"
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a>Modos de usar el contenido de los mensajes para controlar el procesamiento de los mensajes
Hay dos tipos de promoción de propiedades: **campos distintivos** y **campos de propiedades**, la última de las cuales utiliza esquemas de propiedad. En el Editor de BizTalk, administra estos dos tipos de promoción de propiedades mediante el **promocionar propiedades** cuadro de diálogo, que es accesible mediante la **promocionar propiedades** propiedad de la  **Esquema** nodo.  
  
> [!NOTE]
>  Existen algunas restricciones en cuanto a los valores que puede promocionar. Para obtener más información, vea la tabla en [promocionar propiedades](../core/promoting-properties.md).  
  
 Debe decidir el tipo de promoción de propiedades que usará según los detalles de la situación concreta. Tenga en cuenta las siguientes diferencias entre **campo distintivo** promoción de propiedades y **campo de propiedad** promoción de propiedades:  
  
- **Campos distintivos** no puede participar en el enrutamiento de mensajes y, por tanto, no aparecen en las expresiones de filtro. Solo están disponibles dentro del contexto de una orquestación, pero tienen menos sobrecarga al enviar o recibir mensajes.  
  
- **Campos distintivos** no tiene ninguna limitación de tamaño. **Campos de propiedades** se limitan a 255 caracteres.  
  
- **Campos distintivos** no requieren artefactos independientes para crearse, mientras que **campos de propiedades** requieren la creación y mantenimiento de un esquema de propiedad.  
  
  Considerando estas consideraciones, debe promocionar nodos como **campos de propiedades** solo cuando se va a usar las propiedades promocionadas para el enrutamiento de mensajes o con fines de seguimiento. En caso contrario, si solo va a obtener acceso a las propiedades promocionadas desde las orquestaciones, que debería aprovechar el hecho de que **campos distintivos** son mucho más barato, más ligero y más fácil de usar que  **Campos de propiedades**.  
  
  Las propiedades promocionadas mediante el **campo distintivo** mecanismo solo son accesible desde las orquestaciones y no es accesible desde las canalizaciones, puertos y así sucesivamente. Por otro lado, las propiedades promocionan mediante el **campos de propiedades** y mecanismo de propiedad de esquema son accesibles desde todos estos componentes. Otra diferencia importante es que los valores de los campos de propiedades tienen una limitación de 255 caracteres y que los de los campos distintivos no tienen dicha limitación.  
  
  En esta sección se proporciona información acerca de estos dos tipos de promoción de propiedades, incluida la información acerca de cómo establecer dichas propiedades promocionadas para un esquema de mensaje mediante el Editor de BizTalk.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Propiedades de contexto de mensaje de BizTalk](../core/about-biztalk-message-context-properties.md)  
  
-   [Procesamiento de mensajes de instancia con campos distintivos](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [Procesamiento de mensajes de instancia con promoción de propiedades](../core/instance-message-processing-using-property-promotion.md)