---
title: "Diseñar con patrones: la solución de administración de procesos empresariales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- patterns [process management solutions], examples
- patterns [process management solutions], designing
- examples, programming patterns
- designing, programming patterns
ms.assetid: 0583f4a4-01db-4d5b-a1f5-1694c1ddbd30
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91da8c63fc46ee90696e257bfd6142b5088af305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="designing-with-patterns-the-business-process-management-solution"></a>Diseñar con patrones: la solución de administración de procesos empresariales
La solución Administración de procesos empresariales muestra una forma de construir un administrador de procesos en una aplicación de BizTalk. La solución utiliza un componente para seleccionar y controlar la secuencia de fases en el procesamiento de pedidos. La solución toma un pedido, que puede ser de un nuevo servicio, un cambio o cancelación del servicio, lo registra y lo confirma antes de pasarlo para su procesamiento. El procesamiento consta de uno o más fases de control del pedido. Por último, la solución devuelve una respuesta final a la solicitud de pedido original.  
  
 Una solución de administración de proceso bien diseñada le permite agregar o quitar fases del proceso sin tener que reconstruir el resto de la aplicación. El enfoque adoptado en esta solución permite exactamente eso. El proceso de pedido se divide en etapas específicas, independientes. Todas las fases leen del mismo puerto y utilizan un filtro para determinar qué mensajes les corresponde procesar. Esto se explica con más detalle en la sección siguiente: "Patrones".  
  
 Esta solución también acepta entradas a través de un servicio Web, aunque también puede utilizar una interfaz que no sea de servicio con esta solución mediante una conexión FTP. Esta instalación simula cómo se puede utilizar la aplicación en un sistema por lotes.  
  
## <a name="patterns"></a>Patrones  
 En el diagrama siguiente se muestra una versión simplificada de los patrones de la solución Administración de procesos empresariales, como se describen en la sección anterior.  
  
 ![Patrones de solución de administración de procesos de negocio](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
 La solución consta de las siguientes partes: la interfaz de servicio, el canal FTP, varios traductores, el Administrador de procesos y las dos fases de procesamiento. Los cuatro traductores de la sección de preprocesamiento crean un mensaje de confirmación que regresa a la interfaz de servicio, generan una entrada en una base de datos de seguimiento o de historial y crean una entrada en el sistema de servicio. El cuarto traductor crea el mensaje que requiere el administrador de procesos. El administrador de procesos, a su vez, controla las fases de procesamiento.  
  
 En muchas implementaciones del administrador de procesos, el administrador realiza un seguimiento del estado de procesamiento. Esta implementación modifica esto, tal como muestra el diagrama. En esta solución, el administrador de procesos establece un indicador en el mensaje para indicar la fase de procesamiento que debería controlar el mensaje a continuación. Cada fase utiliza un filtro para determinar si debe controlar un mensaje concreto.  
  
 Al utilizar este enfoque, el administrador de procesos no tiene que mantener ninguna información de enrutamiento. Todos los mensajes entre el administrador y las diversas fases utilizan los mismos puertos. Para agregar una fase, sólo tiene que agregar un componente que envíe y reciba en los puertos y filtros adecuados para el número de fase correcto. No necesita cambiar nada en el administrador de procesos.  
  
 Observe que quedan excluidas del diagrama bastantes cosas. Las fases de procesamiento mayo: y, de hecho, realice: comunicarse con procesos de back-end. La solución también puede recopilar información histórica en más de un punto del proceso. Quizá lo más significativo es que no se especifique la lógica del administrador de procesos. Además, no se especifica el uso de conexiones síncronas o asíncronas. Éstas se tratarán en las secciones siguientes.  
  
## <a name="see-also"></a>Vea también  
 [Patrones de la solución de administración de procesos empresariales](../core/patterns-in-the-business-process-management-solution.md)   
 [Traducir los patrones de la solución de administración de procesos empresariales](../core/translating-the-patterns-of-the-business-process-management-solution.md)