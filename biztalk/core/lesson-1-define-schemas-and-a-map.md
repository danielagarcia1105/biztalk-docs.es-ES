---
title: 'Lección 1: Definir esquemas y una asignación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, creating solutions
ms.assetid: 4fe7720d-722e-4fa0-a556-477fc66ffa12
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1e017239fc70186660812ea941fe11209506b1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980373"
---
# <a name="lesson-1-define-schemas-and-a-map"></a>Lección 1: Definir los esquemas y una asignación
En esta lección creará y generará el primer proyecto de la solución de integración de aplicaciones empresariales (EAI). El primer proyecto contiene dos esquemas de mensaje y una asignación.  
  
 En la solución EAI, un sistema de almacén envía una solicitud de mensaje de reposición de inventario a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para su procesamiento. En esta lección se crearán los siguientes elementos:  
  
- La solución EAI que contiene el proyecto.  
  
- El proyecto que contiene los esquemas y la asignación.  
  
- El esquema del mensaje que el almacén envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para solicitar la reposición de inventario.  
  
- El esquema para el mensaje que el almacén está esperando cuando se rechaza una solicitud.  
  
- Una asignación para cambiar el formato de un mensaje de solicitud para crear un mensaje de declinación de solicitud.  
  
  Por último, generará el proyecto antes de iniciar [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md). En la Lección 2, creará el proceso empresarial que enruta los mensajes y que evalúa el contenido del mensaje de solicitud de reposición de inventario con respecto a criterios de aprobación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Crear el proyecto EAISchemas](../core/step-1-create-eaischemas-project.md)  
  
-   [Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md)  
  
-   [Paso 3: Crear el esquema de declinación de la solicitud](../core/step-3-create-the-request-decline-schema.md)  
  
-   [Paso 4: Crear la asignación](../core/step-4-create-the-map.md)  
  
-   [Paso 5: Generar el proyecto EAISchemas](../core/step-5-build-the-eaischemas-project.md)  
  
## <a name="see-also"></a>Vea también  
 [Antes de comenzar el Tutorial](../core/before-you-begin-the-tutorial.md)   
 [Lección 2: Definir el proceso empresarial](../core/lesson-2-define-the-business-process.md)   
 [Lección 3: Implementar la solución](../core/lesson-3-deploy-the-solution.md)