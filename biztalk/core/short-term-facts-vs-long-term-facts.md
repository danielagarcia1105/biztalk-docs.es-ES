---
title: Frente a hechos a corto plazo. Hechos a largo plazo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- facts, short-term
- facts, long-term
- short-term facts
- business rules, facts
- long-term facts
ms.assetid: de020b20-1012-498a-969e-4adc4549918c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d5c37926fb1da5499f34e22c35f8a8f32d238bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271044"
---
# <a name="short-term-facts-vs-long-term-facts"></a>Frente a hechos a corto plazo. Hechos a largo plazo
Dos tipos de hechos se imponen en la memoria de trabajo del motor de reglas, los hechos a corto plazo y los hechos a largo plazo.  
  
## <a name="short-term-facts"></a>Hechos a corto plazo  
 Un hecho a corto plazo se corresponde específicamente con un ciclo de ejecución sencillo del motor de reglas. Estos hechos se retiran automáticamente de la memoria de trabajo del motor de reglas tras ejecutarse la directiva. Si los hechos cambian entre dos ciclos de ejecución del motor de reglas para una directiva, debe enviarlos al motor de reglas como hechos a corto plazo.  
  
 Ejemplos de hechos a corto plazo:  
  
-   Los hechos que envía como parámetros a la **Policy.Execute** método.  
  
-   Los hechos que envía como parámetros a la **reglas de llamada** forma.  
  
-   Los hechos que envía desde una acción de una regla mediante el **Assert** función.  
  
## <a name="long-term-facts"></a>Hechos a largo plazo  
 Un hecho a largo plazo se carga en la memoria de trabajo del motor de reglas para su uso por un número arbitrario de ciclos de ejecución. Normalmente, estos hechos son bastante constantes y no cambian de una ejecución a otra de una directiva. Por ejemplo, quizá desee crear una conexión de base de datos una sola vez y, a continuación, ejecutar la directiva varias veces a través de esa misma conexión. La única diferencia real entre los hechos a corto plazo y los hechos a largo plazo se encuentra en la implementación.  
  
 Para enviar un hecho como de largo plazo, debe seguir los pasos siguientes:  
  
1.  Crear un componente de almacenes de datos de hechos que implementa el **IFactRetriever** interfaz. Cree e imponga el hecho en la memoria de trabajo de la regla motor cuando la **UpdateFacts** método se invoca para la primera vez y actualice el hecho cuando sea necesario en las siguientes llamadas a la **UpdateFacts**(método).  
  
2.  Configure la directiva para usar el componente recuperador datos a través del Compositor de reglas de negocio.  
  
 Para obtener más información sobre cómo crear un administrador de almacenes y su uso en una directiva, consulte [cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md).  
  
## <a name="see-also"></a>Vea también  
 [Hechos](../core/facts.md)