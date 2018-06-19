---
title: Tipos de correlaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, correlation types
- correlation types, correlation sets
- correlation types
- validating, correlation types
- correlation types, about correlation types
- correlation types, validating
ms.assetid: 1aa5ca5c-c37d-4091-9f5d-331a6b202d4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3da5fad8cb4edc1d6a528f481616b4f10efb71d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237780"
---
# <a name="correlation-types"></a>Tipos de correlación
Cada conjunto de correlaciones se basa en un **tipo de correlación**, que es simplemente una lista de propiedades. Éstas pueden ser propiedades de datos, que se encuentran en el propio mensaje, o propiedades de contexto, que describen detalles del sistema o de mensajes no relacionados con los datos transmitidos en el mensaje.  
  
 Puede usar un tipo de correlación en más de un conjunto de correlaciones. Si necesita establecer correlaciones entre distintos valores de las propiedades de un tipo de correlación, debe crear un nuevo conjunto de correlación, se puede inicializar una sola vez cada conjunto de correlaciones.  
  
 Puede promocionar las propiedades de un esquema de propiedades para declarar que algunas de las propiedades de un mensaje están accesibles para la orquestación. Para obtener más información, consulte [promocionar propiedades](../core/promoting-properties.md).  
  
> [!CAUTION]
>  No establezca la propiedad definida por el sistema **BTS. CorrelationToken** que está asociado a cada mensaje. El motor la usa en la correlación de mensajes y establecerla podría dar lugar a la pérdida de mensajes en la orquestación.  
  
## <a name="validating-message-correlation-on-send-actions"></a>Validar la correlación de mensajes en las acciones de envío  
 Puede validar las propiedades de un mensaje enviado desde la orquestación a fin de asegurarse de que refleje las propiedades de su conjunto de correlaciones. De manera predeterminada, esta validación está deshabilitada. Para obtener información sobre cómo habilitarlo, consulte [validación en tiempo de ejecución para el motor de orquestaciones](../core/runtime-validation-for-the-orchestration-engine.md).