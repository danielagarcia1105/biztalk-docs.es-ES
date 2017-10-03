---
title: "¿Qué son medidas y dimensiones? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6b12a4c-9be5-4cac-b5b9-ece376d28cb1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdbbd270b5241d25e7ba227c2db886c112f3f4c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-are-measures-and-dimensions"></a>¿Qué son medidas y dimensiones?
Las dimensiones y las medidas son los aspectos físicos de la agregación de datos. En este tema se definen los conceptos de medidas y dimensiones en el contexto de un escenario de BAM.  
  
## <a name="measures"></a>medidas  
 Suponga que define una actividad de BAM para un proceso de administración de pedidos en términos sumamente simples, con tres elementos:  
  
1.  Hora de inicio del proceso (un evento del mundo real)  
  
2.  Hora de fin del proceso (otro evento real)  
  
3.  Duración del proceso (calculada sustrayendo 1 a 2)  
  
 En este caso agregar datos consiste simplemente en aplicar una función de agregación (por ejemplo promedio, mínimo, máximo, etc.) a una serie de valores de duración individuales (es decir la duración de procesamiento de cada pedido).  
  
 El concepto de "duración promedio" es una medida y un valor individual. Por sí misma, esta medida produce información relevante para la administración de procesos en el sentido de que indica si el proceso global funciona (en cuanto a precisión/rendimiento) de la forma prevista. No obstante, en ausencia de otros datos (ya que la "duración promedio" es un solo valor) es más difícil comprender el significado del valor real de la medida. Por ejemplo, ¿por qué hubo un aumento anormal de la duración esta semana? ¿Fue debido a un socio, un programa o un producto concretos?  
  
## <a name="dimensions"></a>Dimensions  
 Las dimensiones son el contexto que ayuda al consumidor de medidas a entender el significado de éstas.  
  
 Siguiendo con el ejemplo anterior, suponga que agrega tres elementos más a la actividad de BAM para el proceso de administración del pedido:  
  
1.  Nombre del socio comercial (el que hizo el pedido)  
  
2.  Nombre del responsable comercial (el contacto de ventas)  
  
3.  Región de venta  
  
 Como la actividad ahora incluye tres posibles tablas dinámicas de datos (socio, responsable comercial y región), la agregación de estos datos resulta literalmente en la creación de un cubo tridimensional en tiempo de ejecución.  
  
 Sigue comenzando con el primer elemento de trabajo, lo que crea una medida "duración promedio" individual. Al finalizar el siguiente elemento de trabajo (iniciado por la llegada de otro pedido), si el socio comercial, el responsable comercial y la región son los mismos que para el primer elemento, todo lo que ocurre es que se vuelve a calcular la medida de "duración promedio", ahora a partir de los dos elementos (por ejemplo, el promedio de las dos duraciones) para obtener un solo valor de medida de "duración promedio".  
  
 En cuanto se recibe un elemento cuyo socio comercial, responsable comercial o región son diferentes de los anteriores, se crea un nuevo valor de medida de "duración promedio" que se mantiene aparte del primero.  
  
 Por ejemplo, si el socio comercial del tercer elemento de trabajo es diferente de los dos anteriores, el resultado es la creación de un segundo valor de medida de "duración promedio" a lo largo de la dimensión de socio comercial. Ahora puede revisar los valores de "duración promedio" a lo largo de la dimensión de socio comercial, y ver aspectos tales como: "de promedio, se tarda casi el doble en procesar los pedidos de SocioComercialX respecto de los de SocioComercialY". Asimismo, las dimensiones pueden contraerse para su visualización para poder seguir viendo la "duración promedio" global del proceso, independientemente de cualquier socio comercial o de otra dimensión.  
  
 Finalmente, si el socio comercial, el responsable comercial y la región tienen cada uno tres y sólo tres valores diferentes, una vez realizadas todas las permutaciones el resultado es un Cubo de Rubik® de datos, en el que los usuarios pueden ver cada uno de los 27 valores de "duración promedio" mantenidos de forma independiente y las dimensiones son tres aristas del cubo.  
  
 Para obtener más información acerca de dimensiones y medidas, vea el tema sobre los datos de origen de OLAP en informes de tablas dinámicas y de gráficos dinámicos de la Ayuda de Excel.