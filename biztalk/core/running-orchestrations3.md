---
title: Ejecuta Orchestrations3 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, running
- Receive shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Call Orchestration shape [Orchestration Designer], starting orchestrations
- Receive shape [Orchestration Designer], activating orchestrations
ms.assetid: 5bfe61c9-80e0-4a0a-b6b1-ab48037e665e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 550fc1e03f3583215a817028917000c9a9c3074a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-orchestrations"></a>Orquestaciones en ejecución
Las instancias de orquestación están diseñadas para ser activen mediante una llamada explícita desde otra orquestación, mediante un **orquestación de llamada** forma o **Iniciar orquestación** forma, o mediante la recepción de un mensaje de activación. El esquema de mensaje de activación se especifica en el **mensaje** propiedad. Debe diseñar la orquestación según corresponda, y establecer el **activar** propiedad en un **recepción** forma en true, o asegúrese de que una orquestación de llamada existe y está configurada correctamente para ejecutar el nueva orquestación.  
  
 Para poder ejecutar una instancia, primero debe enlazar e implementar el ensamblado de BizTalk y, a continuación, dar de alta el motor de orquestaciones e iniciarlo para comenzar el proceso. Para obtener más información, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) y [implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md). Cuando se invoca una orquestación desde otra o aparece un mensaje en el motor que coincide con los criterios de una recepción de activación, el motor crea una nueva instancia de la orquestación y ejecuta esa instancia. Se pueden ejecutar distintas instancias simultáneamente.  
  
## <a name="calling-and-starting-orchestrations"></a>Llamar e iniciar orquestaciones  
 El **orquestación de llamada** forma y **Iniciar orquestación** forma se puede usar para activar otra orquestación. En ambos casos, el autor de la llamada puede pasar parámetros para intercambiar información con la otra orquestación. Para obtener más información, consulte [cómo agregar parámetros a orquestaciones](../core/how-to-add-parameters-to-orchestrations.md).  
  
## <a name="using-activation-receives-with-filter-expression"></a>Usar recepciones de activación con expresión de filtro  
 El **recepción** forma también puede usar una expresión de filtro para requerir más criterios para la activación. Si el mensaje es del tipo correcto y alguna propiedad o propiedades del mensaje cumplen todos los criterios de la expresión de filtro, el **recepción** forma acepta el mensaje y la orquestación está activada. Una forma de recepción de ese tipo se conoce como un *recepción de activación*.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar la forma de orquestación de llamada](../core/how-to-configure-the-call-orchestration-shape.md)   
 [Cómo configurar la forma Iniciar orquestación](../core/how-to-configure-the-start-orchestration-shape.md)   
 [Cómo configurar la forma recepción](../core/how-to-configure-the-receive-shape.md)   
 [Generar y ejecutar orquestaciones](../core/building-and-running-orchestrations.md)