---
title: 'Lección 2: Recibir y filtrar notificaciones | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5ec679c-1c67-4bf4-aa88-0787373343f5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f28d0479510078b3717d68f99976808ee19aa7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222556"
---
# <a name="lesson-2-receive-and-filter-notifications"></a>Lección 2: Recibir y filtrar notificaciones
En esta lección, empezar a crear una orquestación que recibe las notificaciones de cambios en el **empleado** tabla. Una vez que la orquestación recibe la notificación, extrae el tipo de notificación y si el tipo de notificación es para una operación de inserción en el **empleado** tabla, una condición "if" se usa para realizar las tareas subsiguientes. En esta lección, realizará las tareas siguientes:  
  
1.  Agregar un unidireccional puerto de recepción y un **recepción** forma a la orquestación para recibir el mensaje de notificación.  
  
2.  Agregar un **expresión** forma que contenga una consulta xpath para extraer el tipo de notificación.  
  
3.  Después de que se conoce el tipo de notificación, agregar un filtro a la orquestación mediante la inclusión de un **decidir** forma. Esta forma se decide si la notificación es para una notificación de inserción y, a continuación, realiza las operaciones posteriores. Si la notificación no es para una operación de inserción, la orquestación no hace nada.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Agregar formas de orquestación para recibir una notificación](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [Paso 2: Extraer el tipo de notificación de mensaje de notificación](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [Paso 3: Agregar un filtro para las notificaciones de inserción](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)