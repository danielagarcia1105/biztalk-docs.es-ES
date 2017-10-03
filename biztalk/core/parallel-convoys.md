---
title: Convoyes en paralelo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Parallel Task shape [Orchestration Designer], concurrent receive tasks
- messages, convoys
- correlation sets, concurrent receive tasks
- correlation sets, Parallel Task shape [Orchestration Designer]
- orchestrations, messages
- messages, correlating to orchestrations
ms.assetid: 036aa8c0-f49c-47f0-ac1e-6c667bca3811
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c6993aa3c5dd47cb5b554dd8ab2080020ebb80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="parallel-convoys"></a>Convoyes paralelos
Un convoy paralelo permite agrupar varios mensajes individuales para lograr un resultado requerido. El conjunto de mensajes relacionados puede llegar en cualquier orden, pero BizTalk Server debe recibir todos ellos antes de empezar el proceso.  
  
 Por ejemplo, cuando un hospital admite a un nuevo paciente, el hospital necesita varios datos del paciente, incluida la información del seguro, su historial médico anterior y la información de contacto. Varias personas distintas pueden recopilar esta información, entre otros, un experto en seguros, una enfermera y un recepcionista. Esta información se procesa en varios sistemas diferentes. No se garantiza en qué orden se recopile y envía esta información. Por ejemplo, es posible que las personas encargadas de obtener los datos estén ocupadas con otros pacientes, que el departamento de historiales médicos esté sobrecargado o que el sistema de seguros no funcione correctamente. Reunir toda esta información del paciente de manera organizada debe realizarse durante el tiempo que el paciente pasa en el hospital. Esto garantiza que el paciente reciba la atención apropiada y una factura precisa.  
  
 El escenario anterior es un ejemplo de escenario empresarial que requiere el procesamiento de mensajes en convoy paralelo. Los requisitos empresariales exigen la recepción de tres tipos de mensajes distintos antes de admitir al paciente en el hospital. Estos tres mensajes son los mensajes Seguro, Historial y Paciente. Cualquiera de estos mensajes puede ser el primero en llegar para un paciente, y esto crea una condición de anticipación. Para resolver este problema, tres **recepción** formas se colocan en un **acciones paralelas** forma y cada recepción se marca como activar = True. De este modo, cualquiera de los tres mensajes puede iniciar la orquestación. La instancia de orquestación espera hasta que los otros dos mensajes lleguen antes de continuar con el procesamiento ulterior.  
  
## <a name="implementing-parallel-convoys"></a>Implementar convoyes paralelos  
 Puede implementar convoyes paralelos mediante el patrón de diseño de mensajería de recepciones correlacionadas paralelas de BizTalk Server. Correlacionadas paralelas recibe se ponen en correlación las instrucciones de recepción en dos o más ramas de un **acciones paralelas** forma. Si se inicia una correlación en más de una tarea paralela, cada recepción correlacionada debe inicializar exactamente el mismo conjunto de correlaciones. La tarea de este tipo que recibe un mensaje correlacionado realiza primero la inicialización real y se realiza la validación de las demás tareas en el **acciones paralelas** forma de orquestación.  
  
 Para obtener un ejemplo de implementación de convoy paralelo, consulte el ejemplo SDK "Parallel Convoy" en [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con escenarios de convoyes](../core/working-with-convoy-scenarios.md)   
 [Convoyes secuenciales](../core/sequential-convoys.md)