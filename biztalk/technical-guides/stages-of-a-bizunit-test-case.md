---
title: Fases de un caso de prueba de BizUnit | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed0e725f-2c52-43f7-ae30-343413a703c2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff435fd1c69118112b0121bf68b38ae3151885f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302380"
---
# <a name="stages-of-a-bizunit-test-case"></a>Fases de un caso de prueba de BizUnit
Cada caso de prueba de BizUnit consta de tres fases: **TestSetup**, **TestExecution**, y **TestCleanup**. Cada fase contiene uno o varios pasos de prueba que son responsables de realizar una sola unidad discreta de trabajo; Por ejemplo, el **FileCreateStep** es responsable de crear un archivo en una ubicación especificada con un nombre de archivo determinado.  BizUnit incluye más de 70 pasos de prueba y también proporciona capacidades de extensión que permiten nuevos pasos de prueba agregar fácilmente para el marco de trabajo. La capacidad para agregar nuevos pasos para el marco de trabajo permite BizUnit para utilizarse en una amplia gama de escenarios. Este tema describe las fases de prueba de BizUnit con más detalle.  
  
## <a name="setup-stage"></a>Fase de configuración  
 Esta fase de instalación prepara la plataforma para la prueba. Por ejemplo, antes de poder ejecutar una prueba determinada, tendrá un archivo se copien en una caída de archivo como preparación para la ejecución de la prueba real. También podría utilizar esta fase para realizar la limpieza de las ubicaciones de archivos o tablas de base de datos que se utilizarán en la prueba. Como con cada etapa de BizUnit, no existe ningún límite para el número de pasos de prueba que se pueden agregar, que proporciona la flexibilidad necesaria para tratar escenarios complejos.  
  
## <a name="execution-stage"></a>Fase de ejecución  
 La fase de ejecución es donde realmente se ejecuta la prueba. Esto es donde realmente se prueba la función del sistema que se va a validar.  
  
## <a name="cleanup-stage"></a>Fase de limpieza  
 La fase de limpieza es el contenedor de pasos de prueba que devuelva la plataforma en el estado coherente que estaba antes de que ejecutó la prueba. Esta fase se ejecuta siempre, incluso si se produce un error en la fase de ejecución. Es el motivo de que la plataforma debe devolverse al punto de partida impedir que un caso de prueba interfiera con otra para que cada caso de prueba se ejecuta de forma autónoma como parte del conjunto de pruebas. Asegurar una limpieza completa del sistema en esta fase es uno de los principios rectores para pruebas eficientes con BizUnit.  
  
 El siguiente diagrama ilustra el formato de un caso de prueba de ejemplo, que incluye los pasos de prueba en las tres fases: el programa de instalación, la ejecución y la limpieza. Es importante seguir siempre esta estructura al definir los casos de prueba con BizUnit.  
  
 ![Etapas de una prueba de BizUnit](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")  
Etapas de una prueba de BizUnit  
  
## <a name="see-also"></a>Vea también  
 [Usando BizUnit para facilitar la prueba automatizada](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)