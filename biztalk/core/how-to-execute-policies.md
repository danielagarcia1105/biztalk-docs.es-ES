---
title: "Cómo ejecutar directivas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b0aa834150f0d5c84ebb4c757769a2be38f3942
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-execute-policies"></a>Cómo ejecutar directivas
El código de ejemplo siguiente muestra cómo invocar el motor de reglas para ejecutar una directiva mediante programación utilizando la **directiva** clase en el **Microsoft.RuleEngine** ensamblado.  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a>Métodos importantes de la clase de directiva  
 A continuación se presentan los métodos importantes de la clase Directiva y las descripciones correspondientes.  
  
|Método de la clase Directiva|Description|  
|--------------------------------|-----------------|  
|Execute|Agrega los hechos a corto plazo especificados en la memoria de trabajo del motor de reglas y ejecuta la directiva mediante el algoritmo de acción o resolución de conflictos o coincidencias. Para obtener más información sobre el algoritmo de acción o resolución de conflictos o coincidencias, vea [evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md) .|  
|Dispose|Publica los recursos que usa el motor de reglas para la ejecución de la directiva.|  
|Desactivar|Borra o restablece la memoria de trabajo y la agenda de la instancia del motor de reglas para la ejecución de la directiva.|  
  
## <a name="see-also"></a>Vea también  
 [Método Policy.Dispose](../core/policy-dispose-method.md)