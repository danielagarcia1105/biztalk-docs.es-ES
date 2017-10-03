---
title: 'Paso 2: Crear la Orchestration1 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a88cafbb-3b6f-4d27-8516-79a2391b4e31
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1989fe18d9c9c81741ac83bd2f96627ea818eb91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-orchestration"></a>Paso 2: Crear la orquestación
La configuración de orquestación se realiza de la siguiente forma, mediante un proyecto denominado BeginDocTest:  
  
-   Puertos  
  
-   Mensajes  
  
-   Envío y recepción  
  
-   Construir mensaje  
  
-   Transformaciones  
  
 La orquestación no realiza ningún control de excepciones. J.D. Edwards OneWorld realiza las operaciones BeginDoc y operaciones siguientes dentro de una transacción implícita que se revertirá si la conexión agota el tiempo de espera. Por lo tanto, la orquestación de BizTalk no necesita hacer nada para revertir los cambios que realiza J.D. Edwards OneWorld. Sin embargo, el tiempo de espera provocará una excepción en la orquestación de BizTalk. BizTalk registrará la excepción en el registro de eventos. Si desea agregar control de excepciones a la orquestación, vea "Cómo agregar un bloque de excepción de filtrado" y "Cómo agregar un bloque de compensación" en la Ayuda de Microsoft BizTalk Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Tarea 1: Crear los puertos](../core/task-1-create-the-ports2.md)  
  
-   [Tarea 2: Crear los mensajes](../core/task-2-create-the-messages1.md)  
  
-   [Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes1.md)  
  
-   [Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape2.md)  
  
-   [Tarea 5: Configurar la forma transformación](../core/task-5-configure-the-transform-shape1.md)