---
title: "Cómo configurar la forma Iniciar excepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Throw Exception shape [Orchestration Designer]
- orchestrations, errors
- Orchestration Designer, errors
ms.assetid: d3190f1b-db5e-4988-bff6-f7a276760ece
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07d156572484ba4fbe71533252ce4fe956136699
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-throw-exception-shape"></a>Cómo configurar la forma Iniciar excepción
Puede iniciar excepciones explícitamente en una orquestación mediante el uso de la **Iniciar excepción** forma. Cuando se lleva a cabo el inicio, el motor de tiempo de ejecución buscará el controlador de excepción más próximo que pueda controlar el tipo de excepción que se inicia.  
  
 En primer lugar, se busca un ámbito de inclusión en la orquestación actual y se consideran los controladores de excepción asociados del ámbito para buscar el controlador apropiado para el tipo de excepción que se inicia.  
  
 Si no se encuentra ningún controlador de excepción apropiado, se busca un ámbito que contenga el punto de la llamada a la orquestación en uso en la orquestación que llamó a la orquestación actual. Esta búsqueda continúa hasta que se encuentra un controlador de excepción que pueda controlar la excepción actual.  
  
 Una coincidencia exacta para la excepción es una clase de excepción de la misma clase o de una clase base que el tipo de excepción en tiempo de ejecución que se inicia.  
  
 Cuando se encuentra un controlador de excepción coincidente, el control se transfiere a la primera instrucción del controlador de excepción.  
  
 Si se produce un error en la búsqueda de controladores de excepción coincidentes, la orquestación se detiene. Las transacciones pueden ayudar a minimizar el impacto de dicha ocurrencia.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-configure-a-throw-exception-shape"></a>Para configurar la forma Iniciar excepción  
  
-   En la ventana Propiedades, seleccione un tipo de objeto disponible para iniciar desde el **objeto de excepción** lista desplegable.  
  
    > [!NOTE]
    >  Seleccione excepción General en el **Iniciar excepción** if de forma única el **Iniciar excepción** forma es dentro de un controlador de excepciones y desea volver a producir la excepción detectada en el controlador de excepción actual. Recibirá un error durante la compilación si utiliza excepción General para un **Iniciar excepción** forma en cualquier otro contexto.  
  
## <a name="see-also"></a>Vea también  
 [Excepciones](../core/exceptions.md)