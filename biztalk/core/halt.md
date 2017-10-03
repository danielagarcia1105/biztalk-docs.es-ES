---
title: Detener | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Halt function [Business Rules Engine]
ms.assetid: 468ba6dd-2bb2-4787-a824-1f5455508efd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ca8091d4ff4405704314d72939758c7600a71a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="halt"></a>Detener
Puede usar el **detener** función para detener la ejecución del motor de reglas actual. El **detener** función toma un parámetro de tipo `Boolean`. Si se especifica el valor del parámetro como `true`, el motor de reglas también borrará la agenda que contiene las reglas candidatas pendientes.  
  
 El **Policy.Execute** método es básicamente un contenedor alrededor de la **RuleEngine.Execute** método. Tiene código parecido al siguiente:  
  
```  
RuleEngine.Assert(facts);   
RuleEngine.Execute();   
RuleEngine.Retract(facts);  
```  
  
 Si usa el **Policy.Execute** método para ejecutar una directiva, el motor de reglas devuelve el control a la **Policy.Execute** método cuando el **detener** se ejecuta la función. El **Policy.Execute** método retira los hechos y devuelve el control al llamador. Por tanto, la ejecución de directiva detenida no se puede reanudar en este caso. Lo mismo sucede cuando se usa el **reglas de llamada** forma para invocar la directiva.  
  
 Sin embargo, si usa el **RuleEngine.Execute** método directamente para ejecutar la directiva, puede reanudar la ejecución de directiva detenida con la siguiente activación de reglas pendiente mediante la llamada a **RuleEngine.Execute** nuevo (siempre y cuando no retirara los objetos necesarios entre las dos llamadas). El código de ejemplo para reanudar la ejecución de la directiva detenida es el siguiente:  
  
```  
//assert facts into working memory of the rule engine instance  
RuleEngine.Assert(facts);   
//execute the policy  
RuleEngine.Execute();   
//policy invokes the Halt method when executing actions.   
//control is returned to here when the Halt method is invoked  
  
//when engine is halted do the following  
//Add your code here  
  
//To resume the halted rule engine execution  
RuleEngine.Execute();  
//retract or remove facts frm the working memory of the rule engine  
RuleEngine.Retract(facts);  
```  
  
 Tenga en cuenta que la **Policy.Execute** método almacena en caché las instancias del motor de reglas para mejorar el rendimiento. Cuando se usa el **RuleEngine.Execute** directo del método, el motor de reglas de instancias no se almacenan en caché.  
  
## <a name="see-also"></a>Vea también  
 [Funciones de Control del motor](../core/engine-control-functions.md)