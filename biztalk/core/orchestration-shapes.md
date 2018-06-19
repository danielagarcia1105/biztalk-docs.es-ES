---
title: Formas de orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer]
- Loop shape [Orchestration Designer]
- Throw Exception shape [Orchestration Designer]
- Expression shape [Orchestration Designer]
- Decide shape [Orchestration Designer]
- Receive shape [Orchestration Designer]
- Compensate shape [Orchestration Designer]
- orchestrations, shapes
- Suspend shape [Orchestration Designer]
- Send shape [Orchestration Designer]
- Group shape [Orchestration Designer]
- Listen shape [Orchestration Designer]
- shapes, about shapes
- Construct Message shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer]
- Call Rules shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer]
- Transform shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Role Link shape [Orchestration Designer]
- Call Orchestration shape [Orchestration Designer]
- Port shape [Orchestration Designer]
- shapes
- Scope shape [Orchestration Designer]
- Terminate shape [Orchestration Designer]
- Orchestration Designer, shapes
- Insufficient Configuration Smart Tag [Orchestration Designer]
ms.assetid: a1d03baa-a267-499d-94fc-700b3e959458
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181656208b757c595feb9d19ee786fe91f1b78f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264300"
---
# <a name="orchestration-shapes"></a>Formas de orquestación
El Diseñador de orquestaciones es una herramienta visual para crear orquestaciones Proporciona varias formas que puede situar en la superficie de diseño como representaciones visuales de acciones subyacentes y pueden serle útiles a la hora de diseñar e implementar eficientemente una orquestación.  
  
 **Acción de configuración incompleta**  
  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!NOTE]
>  La acción de configuración incompleta se muestra en el Diseñador de orquestaciones cuando este detecta que la forma asociada no está completamente configurada. Si una forma de una orquestación no está completamente configurada, la orquestación asociada no se compilará.  
  
 En la siguiente tabla se enumeran las formas disponibles junto a una breve descripción de la función de cada una.  
  
|Forma|Nombre de la forma|Finalidad|  
|-----------|----------------|-------------|  
|![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")|**Orquestación de llamada**|Permite que su orquestación llame a otra orquestación de forma sincrónica.|  
|![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")|**Reglas de llamada**|Permite crear una directiva de reglas de negocios para ejecutarla en la orquestación.|  
|![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")|**Compensar**|Permite llamar a código para deshacer o compensar operaciones ya realizadas por la orquestación cuando se produce un error.|  
|![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")|**Forma construir mensaje**|Permite construir un mensaje.|  
|![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")|**Decidir**|Permite que su orquestación se ramifique de forma condicional.|  
|![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")|**Retraso**|Permite generar retrasos en la orquestación en función de un intervalo de tiempo de espera.|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**Expresión**|Permite asignar valores a variables o realizar llamadas .NET.|  
|![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")|**Grupo**|Permite agrupar operaciones en una unidad única que puede contraerse o expandirse para mayor facilidad visual.|  
|![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")|**Escuchar**|Permite que la orquestación se ramifique de forma condicional según los mensajes recibidos o el vencimiento de un período de espera.|  
|![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")|**Bucle**|Permite que la orquestación se ejecute en bucle hasta que se cumpla una condición.|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**Asignación de mensajes**|Permite asignar valores de mensaje.|  
|![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")|**Acciones paralelas**|Permite que la orquestación lleve a cabo dos o más operaciones independientemente del resto.|  
|![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")|**Puerto**|Define dónde y cómo se transmiten los mensajes.|  
|![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")|**Recepción**|Permite que su orquestación reciba un mensaje.|  
|![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")|**Vínculo de función**|Permite crear una colección de puertos que se comunican con el mismo socio comercial lógico, quizá mediante diferentes transportes o extremos.|  
|![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")|**Ámbito**|Proporciona un marco de trabajo para transacciones y control de excepciones.|  
|![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")|**Enviar**|Permite enviar un mensaje desde la orquestación.|  
|![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")|**Iniciar orquestación**|Permite que su orquestación llame a otra orquestación de forma asincrónica.|  
|![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")|**Suspender**|Suspende la operación de la orquestación para permitir la intervención en caso de que se produzca alguna condición de error.|  
|![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")|**Finalizar**|Permite finalizar inmediatamente la operación de la orquestación por si se produjera alguna condición de error.|  
|![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")|**Iniciar excepción**|Permite iniciar una excepción de forma explícita en caso de error.|  
|![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")|**Transformar**|Permite asignar los campos de mensajes ya existentes a nuevos mensajes.|