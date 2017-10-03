---
title: 'Tarea 1: Crear el Ports2 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 097504c3-67de-4a0b-99a5-648121aff1e5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f41f02d464b15841c3f5a00dbd0601f65e18b510
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="task-1-create-the-ports"></a>Tarea 1: Crear los puertos
Cree los siguientes puertos, BeginDoc y EndDocOut a la izquierda y JDEPort con 3 operaciones a la derecha.  
  
|Nombre y configuración|Operación|Tipo de mensaje > esquema|  
|-----------------------|---------------|--------------------------|  
|BeginDoc<br /><br /> BeginDocType/Unidireccional/Interno<br /><br /> Siempre recibir mensajes en este puerto<br /><br /> Especificar más tarde|Solicitud de operación 1-|BeginDocTest.B4200310Service_1.<br />F4211FSBeginDoc|  
|EndDocOut<br /><br /> EndDocType/Unidireccional/Interno<br /><br /> Siempre enviaré los mensajes en este puerto<br /><br /> Especificar más tarde|Solicitud de operación 1-|BeginDocTest.B4200310Service_1.<br />F4211FSEndDocResponse|  
|JDEPort<br /><br /> JDEPortType/Solicitud-respuesta/Interno<br /><br /> Podrá siempre que se va a enviar una solicitud y recibiré una respuesta<br /><br /> Especificar más tarde **Nota:** para operaciones adicionales, haga clic en el puerto y seleccione **nueva operación**.|Solicitud de operación 1-<br /><br /> Respuesta de la operación 1-<br /><br /> Solicitud de operación 2-<br /><br /> Respuesta de la operación 2-<br /><br /> Solicitud de operación 3 -<br /><br /> Respuesta de operación 3 -|BeginDocTest.B4200310Service_1.<br />F4211FSBeginDoc<br /><br /> BeginDocTest.B4200310Service_1.<br />F4211FSBeginDocResponse<br /><br /> BeginDocTest.B4200310Service_1.<br />F4211FSEditLine<br /><br /> BeginDocTest.B4200310Service_1.<br />F4211FSEditLineResponse<br /><br /> BeginDocTest.B4200310Service_1.<br />F4211FSEndDoc<br /><br /> BeginDocTest.B4200310Service_1.<br />F4211FSEndDocResponse|  
  
## <a name="see-also"></a>Vea también  
 [Tarea 2: Crear los mensajes](../core/task-2-create-the-messages1.md)   
 [Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes1.md)   
 [Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape2.md)   
 [Tarea 5: Configurar la forma transformación](../core/task-5-configure-the-transform-shape1.md)