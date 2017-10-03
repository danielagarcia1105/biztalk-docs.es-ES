---
title: "Información de salida de seguimiento de prueba de directivas para reglas de negocios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, business rules
- testing, policies
- business rules, testing
- policies, testing
ms.assetid: 26ff584e-97a1-4d76-a8a9-a55b4c99231f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c223e8bddae1ff68e77cdf881ea22e6be4cdab9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="policy-test-trace-output-information-for-business-rules"></a>Información del resultado del seguimiento de pruebas de directivas para reglas de negocios
En esta sección se proporciona información acerca de la información de seguimiento que se muestra al probar una directiva en el Compositor de reglas de negocio. Se ve información muy similar al visualizar los resultados de seguimiento de la ejecución de directivas mediante las consultas de seguimiento de instancias de servicio y eventos de mensaje en la página Concentrador de grupo.  
  
 Existen cuatro tipos de instrucciones que se muestran en el resultado del seguimiento:  
  
-   Actividad de hechos  
  
-   Evaluación de condición  
  
-   Actualización de agenda  
  
-   Regla activada  
  
 A continuación se describe cada tipo de instrucción.  
  
## <a name="fact-activity"></a>Actividad de hechos  
 Esta instrucción indica los cambios en los hechos que están en la memoria de trabajo del motor. A continuación se muestra un ejemplo de entrada de actividad de datos:  
  
```  
FACT ACTIVITY 3/16/2004 9:50:28 AM  
Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
Ruleset Name: LoanProcessing  
Operation: Assert  
Object Type: MyTest.test  
Object Instance Identifier: 872  
```  
  
### <a name="rule-engine-instance-identifier"></a>Identificador de instancias de motor de reglas  
 Identificador único para la **RuleEngine** instancia que proporciona el entorno de ejecución para la activación de reglas.  
  
### <a name="ruleset-name"></a>Nombre de conjunto de reglas  
 Nombre del conjunto de reglas (directiva).  
  
### <a name="operation"></a>Operación  
 Existen tres tipos de operaciones que pueden darse en una actividad de datos:  
  
 Assert  
  
 El hecho se agrega a la memoria de trabajo.  
  
 Update  
  
 El hecho se actualiza mediante una regla y, a continuación, tiene que volver a imponerse en el motor para volver a evaluarse según los nuevos datos y el nuevo estado.  
  
 Retirar  
  
 El hecho se elimina de la memoria de trabajo.  
  
> [!NOTE]
>  Si se ha impuesto un hecho cuyo tipo no coincide con ninguno de los utilizados en la directiva, la operación Imponer mostrará "Imponer - Hecho no reconocido".  
  
### <a name="object-type"></a>Tipo de objeto  
 Tipo de hecho de una actividad particular:  
  
-   DataConnection  
  
-   TypedDataTable  
  
-   TypedDataRow  
  
     Cuando se impone TypedDataTable, todas la filas que contiene se imponen como TypedDataRows.  Las TypedDataRows asociadas con una DataConnection no se imponen hasta que se evalúa una condición y se ejecuta la consulta resultante.  
  
-   TypedXmlDocument  
  
     Las aserciones se verán en las instancias de TypedXmlDocument tanto principal como secundaria.  
  
### <a name="object-instance-identifier"></a>Identificador de instancia de objeto  
 Identificador único de instancia de la referencia de hecho.  
  
## <a name="condition-evaluation"></a>Evaluación de condición  
 Esta actividad indica el resultado de la evaluación de predicados individuales. A continuación se muestra un ejemplo de entrada de evaluación de condición:  
  
```  
CONDITION EVALUATION TEST (MATCH) 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:Root.EmploymentType/TimeInMonths >= 18  
Left Operand Value: 31  
Right Operand Value: 18  
Test Result: True  
```  
  
 A continuación se muestran las descripciones de algunos de los términos del ejemplo anterior:  
  
-   **Expresión de prueba.** Expresión simple (unaria o binaria) de una regla.  
  
-   **Valor del operando izquierdo.** Valor del término situado a la izquierda de una expresión.  
  
-   **Valor del operando derecho.** Valor del término situado a la derecha de una expresión.  
  
-   **Resultado de pruebas.** Resultado de la evaluación, que puede ser True o False.  
  
## <a name="agenda-update"></a>Actualización de agenda  
 Esta actividad indica reglas que se agregan a la agenda del motor de reglas para su posterior ejecución. A continuación se muestra un ejemplo de entrada de actualización de agenda:  
  
```  
AGENDA UPDATE 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Operation: Add  
Rule Name: Employment Status Rule  
Conflict Resolution Criteria: 0  
```  
  
 A continuación se muestran las descripciones de algunos de los términos del ejemplo anterior:  
  
-   **Operación.** Se pueden agregar o quitar reglas de la agenda.  
  
-   **Nombre de la regla.** Nombre de la regla que se agrega a la agenda.  
  
-   **Criterios de resolución de conflictos.** Prioridad de una regla, que determina el orden relativo en que se ejecutan las acciones (las acciones de mayor prioridad se ejecutan primero).  
  
## <a name="rule-fired"></a>Regla activada  
 Esta actividad indica la ejecución de acciones de una regla. A continuación se muestra un ejemplo de entrada de regla activada:  
  
```  
RULE FIRED 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Rule Name: Residency Status Rule  
Conflict Resolution Criteria: 10  
```