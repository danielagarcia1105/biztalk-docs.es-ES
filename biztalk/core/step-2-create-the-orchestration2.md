---
title: 'Paso 2: Crear la Orchestration2 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08d65525-77a9-4be2-a509-40ea60fa7401
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13973edb14fbaed331a33eff429d623a33c3ff71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-orchestration"></a>Paso 2: Crear la orquestación
La configuración de orquestación se realiza de la siguiente forma, mediante un proyecto denominado BeginDocTest:  
  
 • Puertos  
  
 • Mensajes  
  
 • Envío y recepción  
  
 • Construir mensaje  
  
 • Transformaciones  
  
 La orquestación no realiza ningún control de excepciones. J.D. Edwards EnterpriseOne realiza las operaciones BeginDoc y operaciones siguientes dentro de una transacción implícita que se revertirán si la conexión agota el tiempo de espera. Por lo tanto, la orquestación de BizTalk no necesita hacer nada para revertir los cambios que realiza J.D. Edwards EnterpriseOne. Sin embargo, el tiempo de espera provocará una excepción en la orquestación de BizTalk. BizTalk registrará la excepción en el registro de eventos. Si desea agregar control de excepciones a la orquestación, vea "Cómo agregar un bloque de excepción de filtrado " y "Cómo agregar un bloque de compensación" en la ayuda principal de Microsoft BizTalk 2006.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Tarea 1: Crear los puertos](../core/task-1-create-the-ports1.md)  
  
-   [Tarea 2: Crear los mensajes](../core/task-2-create-the-messages2.md)  
  
-   [Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes2.md)  
  
-   [Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape1.md)  
  
-   [Tarea 5: Configurar la forma transformación](../core/task-5-configure-the-transform-shape2.md)