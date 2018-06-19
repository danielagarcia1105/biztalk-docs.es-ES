---
title: Motor de reglas de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Engine
- Business Rules Engine
- Business Rules Engine, rules
- Business Rules Engine, about Business Rules Engine
ms.assetid: 87b38507-9f6d-4863-88a6-9c20f15a4e55
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d99cff10324f1cf1ba97d99431524474ed5f039b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232620"
---
# <a name="business-rules-engine"></a>motor de reglas de negocios
El marco de trabajo de reglas de trabajo es una biblioteca de clases compatible con Microsoft .NET. Proporciona un motor de inferencia eficiente que puede vincular reglas de gran riqueza semántica, declarativas y muy legibles con cualquier objeto de negocios (componentes .NET), documento XML o tabla de base de datos. Los programadores de aplicaciones pueden crear reglas de negocio mediante la generación de reglas a partir de bloques pequeños de lógica de negocios (conjuntos de reglas pequeños) que funciones en información (hechos) incluida en objetos .NET, tablas de base de datos y documentos XML. Este patrón de diseño fomenta la reutilización de código, la sencillez del diseño y la modularidad de la lógica de negocios. Además, el motor de reglas no se impone en la arquitectura o el diseño de las aplicaciones de negocios. De hecho, se puede agregar tecnología de reglas a una aplicación de negocios mediante la invocación directa del motor de reglas o bien mediante la lógica externa que invoque los objetos de negocios sin modificarlos. En resumen, la tecnología permite a los programadores crear y mantener aplicaciones con el mínimo de esfuerzo.  
  
 Al planear el desarrollo de una aplicación basada en reglas, debe determinar primero cómo se ajustarán las reglas a sus procesos empresariales. La aplicación creará una instancia de una directiva y le suministrará datos, o hechos, en los que funcionar. El objeto de directiva encapsula el motor de reglas y suministra un único punto de entrada a través del que ejecutarse.  
  
 También debe planear el desarrollo y la realización de pruebas de su diseño de reglas. Debe considerar cómo va a implementar y actualizar sus directivas. Debería realizar un seguimiento del progreso de la ejecución de su motor de reglas y la supervisión de su estado actual.  
  
 Tenga en cuenta los siguientes pasos a la hora de planear el desarrollo de sus reglas:  
  
1.  Planee cómo incorporar sus reglas en la aplicación.  
  
2.  Identifique la lógica de negocios que desea representar con reglas en su aplicación. El término "lógica de negocios" puede hacer referencia a varios conceptos. Un ejemplo de lógica de negocios sería "Los pedidos de compra por valor de más de quinientos dólares deben ser aprobados por un supervisor".  
  
3.  Identifique los orígenes de datos para los elementos de su regla. También puede definir y publicar vocabularios (nomenclatura específica de dominio que representa los enlaces subyacentes)..  
  
4.  Defina reglas a partir de definiciones de vocabulario o directamente desde enlaces de datos y, a partir de estos, componga una directiva que represente su lógica de negocios.  
  
    > [!NOTE]
    >  Para poder aplicarse en las reglas, los vocabularios deben publicarse.  
  
5.  Pruebe y depure la directiva con hechos de prueba. Puede usar la funcionalidad de directiva de prueba en el Compositor de reglas de negocios o usar **directiva** o **PolicyTester** clases para ejecutar desde una aplicación, el programa de línea de comandos o la orquestación.  
  
6.  Publique la versión de la directiva en el almacén de reglas.  
  
7.  Implemente la versión de la directiva.  
  
8.  Cree una instancia y genere la lista de hechos a corto plazo en la aplicación host. Use la **reglas de llamada** forma de una orquestación para ejecutar la directiva empresarial o crear una instancia de una versión de directiva en la aplicación host mediante programación.  
  
9. Supervise y realice un seguimiento de la ejecución de reglas si es necesario.  
  
    > [!NOTE]
    >  El interceptor de seguimiento predeterminado funciona con orquestaciones. Si su aplicación host no es una orquestación, deberá escribir su propio interceptor de seguimiento para hacerlo.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Reglas](../core/rules.md)  
  
-   [Directivas](../core/policies.md)  
  
-   [Vocabularios](../core/vocabularies.md)  
  
-   [Arquitectura del marco de trabajo de reglas de negocios](../core/business-rules-framework-architecture.md)  
  
-   [Hechos](../core/facts.md)  
  
-   [Motor de reglas](../core/rule-engine.md)