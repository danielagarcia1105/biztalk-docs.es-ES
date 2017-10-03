---
title: "Fase 5: Ejecutar la evaluación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d40fc64-b6cb-448b-8ea1-a6ad7302ab8b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fba6d49d8d69276af4282ad0a941ee1fc4d8068
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="phase-5-executing-the-assessment"></a>Fase 5: Ejecutar la evaluación
La fase de ejecución es donde los datos de rendimiento se generan a través de pruebas de carga automatizada y donde los cuellos de botella de rendimiento son detectados y solucionarse. Esta fase tiene un proceso iterativo mediante el cual cuellos de botella de rendimiento se reduce o elimina probando, evaluar el rendimiento, optimizar y probar de nuevo.  
  
 En este tema se describe los pasos que se siguen normalmente durante la fase de ejecución de una evaluación del rendimiento de BizTalk Server:  
  
## <a name="step-1-run-automated-tests"></a>Paso 1: Ejecutar pruebas automatizadas  
 Comenzar la fase de ejecución mediante la ejecución de pruebas automatizadas. Una evaluación del rendimiento de BizTalk Server normalmente se centra en el rendimiento o pruebas de latencia, pero puede incluir la comprobación de la compilación y pruebas funcionales. Para obtener información completa acerca de cómo ejecutar pruebas automatizadas, vea [implementar las pruebas automatizadas](../technical-guides/implementing-automated-testing.md).  
  
## <a name="step-2-document-and-evaluate-test-results"></a>Paso 2: Documentos y evaluar los resultados de pruebas  
 Al final de cada prueba exhaustivamente documentar los resultados de pruebas y evaluar si se cumplen los objetivos de rendimiento indicados.  
  
## <a name="step-3-modify-the-configuration-of-biztalk-server-third-party-systems-or-solution-artifacts-to-tune-for-performance-based-on-the-test-results"></a>Paso 3: Modificar la configuración de BizTalk Server, sistemas de terceros o artefactos de la solución para la optimización del rendimiento en función de los resultados de pruebas  
 Utilizar los resultados de pruebas para tomar decisiones acerca de cómo optimizar el entorno para alcanzar los objetivos de rendimiento o latencia indicados.  
  
## <a name="step-4-record-all-changes-made-to-the-environment"></a>Paso 4: Registrar todos los cambios realizados en el entorno  
 Asegúrese de que han sido documentados en los cambios realizados en el entorno. Un registro de los cambios, podrá aplicar fácilmente los cambios en el entorno de producción y se alojará el Deshaciendo cambios si es necesario.  
  
## <a name="step-5-repeat-this-cycle-until-goals-are-achieved"></a>Paso 5: Repita este ciclo hasta que se logre establecer objetivos  
 Continuar el ciclo de pruebas, evaluar y documentar los resultados, optimización del entorno y documentar los cambios en el entorno hasta que se alcancen los objetivos de rendimiento deseados.  
  
## <a name="step-6-summarize-test-results-at-the-end-of-each-day"></a>Paso 6: Resumir los resultados de pruebas al final de cada día  
 Completar un "Resumen ejecutivo" de los resultados de pruebas y el progreso realizado al final de cada día. Compilar un correo electrónico que contiene el resumen y enviar a todas las partes interesadas en la evaluación del rendimiento para mantener a todos informados del progreso que se está realizando.  
  
## <a name="step-7-update-the-project-plan-as-timeline-goals-are-met"></a>Paso 7: Actualizar el plan del proyecto que se cumplen los objetivos de la escala de tiempo  
 La escala de tiempo desarrollado en la fase de planificación es una buena referencia para ver el progreso general de la evaluación del rendimiento. Actualizar esta escala de tiempo según sea necesario para comunicar el progreso a todas las partes interesadas.  
  
## <a name="see-also"></a>Vea también  
 [Fases de una evaluación del rendimiento](../technical-guides/phases-of-a-performance-assessment.md)