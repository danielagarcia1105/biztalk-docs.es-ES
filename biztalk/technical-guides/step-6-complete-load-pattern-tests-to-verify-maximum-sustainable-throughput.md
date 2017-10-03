---
title: "Paso 6: Realizar pruebas de modelo de carga constante para comprobar el rendimiento máximo sostenible | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd790354-be9f-4278-bd15-493eac8970c9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6bfc0b9670366ab2f38046fcdc5497234b51ba5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-perform-constant-load-pattern-tests-to-verify-maximum-sustainable-throughput"></a>Paso 6: Realizar pruebas de modelo de carga constante para comprobar el rendimiento máximo sostenible
Cuando carga probando una solución de BizTalk Server mediante Visual Studio 2010, una prueba del modelo de carga constante debe realizarse una vez que el aproximado máxima sostenible rendimiento (MST) de la solución se determina como se describe en [paso 5: realizar la carga por pasos Pruebas para determinar el rendimiento máximo sostenible de patrón](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md). Esto debe hacerse para confirmar que el MST de hecho es sostenible con el tiempo y también con el fin de crear una prueba de carga de la línea de base avanzando evaluar los efectos de los ajustes de rendimiento aplicado a la aplicación de BizTalk Server o el entorno.  
  
## <a name="create-and-run-a-constant-load-pattern-test"></a>Crear y ejecutar una prueba del modelo de carga constante  
 La manera más fácil de crear una prueba de modelo de carga constante que use la misma combinación de pruebas, conjuntos de contadores y asignaciones de conjuntos de contador utilizado por la prueba de modelo de carga por pasos es simplemente guarde la prueba de modelo de carga por pasos "BTS_Messaging_Step.loadtest" como "BTS_Messaging_ Constant.LoadTest"y, a continuación, realice algunos cambios en"BTS_Messaging_Constant.loadtest". Siga estos pasos para crear un modelo de carga constante de prueba que es basado en la prueba de modelo de carga por pasos existente:  
  
1.  Abra BTS_Messaging_Step.loadtest si no está ya abierto.  
  
2.  Haga clic en **archivo** y seleccione **guardar LoadTests\BTS_Messaging_Step.loadtest como**.  
  
3.  En el **Guardar archivo como** cuadro de diálogo, junto a **nombre de archivo**, escriba C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest y, a continuación, haga clic en **guardar**.  
  
4.  En el Editor de prueba de carga, cambiar el nombre del escenario **BTS_Messaging_Step** a **BTS_Messaging_Constant**. El nombre del escenario se muestra directamente bajo la **escenarios** carpeta.  
  
5.  Deje los valores para **combinación de pruebas** y **combinación de redes** sin cambios pero haga clic para seleccionar **modelo de carga por pasos**.  
  
6.  Haga clic en **modelo de carga por pasos** y seleccione **propiedades**.  
  
7.  En el **propiedades** sección, en **modelo de carga** haga clic en la lista desplegable junto a **patrón** y cambie el patrón de **paso** a **Constante**.  
  
8.  En el **propiedades** sección, en **parámetros**, cambie el valor de **recuento de usuarios constante** a un valor ligeramente menor que el número de usuarios en el que el patrón de carga de pasos prueba llegaba a ser no sostenible (es decir, el valor de la **BizTalk:Messaging\Documents recibido por / seg** empezó a superar constantemente el valor de **BizTalk:Messaging\Documents procesadas por segundo** y el valor de la **BizTalk cuadro: General Counters\Spool tamaño** comenzó a aumentar sin enlazar).  
  
9. En el **parámetros de ejecución** carpeta, haga clic en **Setting1 ejecutar [Active]** y seleccione **propiedades**.  
  
10. Desplácese hacia abajo en la lista de propiedades para el **tiempo** sección y escriba un valor para **duración de la ejecución** de al menos 10 minutos (00:10:00) y compruebe que el valor de **velocidad de muestra** todavía se establece en 5 segundos (00: 00:05).  
  
11. Inicie la prueba de carga haciendo clic en el nombre de la prueba (por ejemplo, BTS_Messaging_Constant) y, a continuación, haga clic en el **Ejecutar prueba** opción de menú.