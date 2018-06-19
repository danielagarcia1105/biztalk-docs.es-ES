---
title: Errores de orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception block [Orchestration Designer], suspended orchestrations
- HAT, Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], HAT
- orchestrations, troubleshooting [HAT]
- orchestrations, errors
- HAT, Orchestration Debugger
- Orchestration Debugger
- errors, orchestrations
- HAT, troubleshooting orchestrations
- orchestrations, HAT
- HAT, orchestrations
ms.assetid: d0a799fb-7859-4774-b444-979f22f04215
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d95cab903ae9bf5faacdf385f667c33f9a2d5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263812"
---
# <a name="orchestration-failures"></a>Errores de orquestaciones
Las orquestaciones varían en complejidad; por ejemplo, una orquestación puede llamar a un objeto .NET o construir mensajes mediante la forma de transformación o de asignación. En consecuencia, resulta imposible mostrar una lista de todos los errores debido a la variedad de su contenido y al nivel de personalización. Sin embargo, los errores que se producen en las orquestaciones aparecen como excepciones.  
  
 Si una orquestación no incluye ningún **CatchException** forma para una excepción, la excepción hace que la orquestación suspendida, pero no reanudable. Esto significa que el seguimiento de instancias de mensajes y servicios, o un script WMI, no puede recuperar la instancia. Sin embargo, se pueden guardar todos los mensajes asociados a la instancia Suspendido (no reanudable) mediante el seguimiento (o script WMI) para realizar un diagnóstico y reintentarlo manualmente.  
  
 Para diagnosticar el problema, use el depurador de orquestaciones para ver la última forma que se ejecutó antes de que se suspendiera la instancia. Asimismo, se pueden visualizar los detalles de la excepción con el depurador de orquestaciones.  
  
## <a name="see-also"></a>Vea también  
 [Investigación de orquestación, puerto y errores de mensaje](../core/investigating-orchestration-port-and-message-failures.md)   
 [Depuración de una orquestación](../core/debugging-an-orchestration.md)