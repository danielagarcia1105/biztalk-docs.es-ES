---
title: Seguimiento de transacciones de extremo a extremo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebacd2e4-6b5c-4dc4-8361-b5b77042debc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffa49372c54dc526f45e04317e002604ac0914d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294116"
---
# <a name="end-to-end-transaction-tracking"></a>Seguimiento de transacciones de extremo a extremo
Visibilidad de negocio se relaciona con la capacidad de operadores y los usuarios para supervisar el flujo de tráfico a través del entorno de tiempo de ejecución. Las empresas deben ser capaz de realizar un seguimiento de los procesos y las transacciones que fluyen a través de sus sistemas en cada paso para asegurarse de que pueden jugar su parte en que contribuyen a la generación de ingresos. AmberPoint SMS simplifica la medida y el seguimiento de estos mensajes en Microsoft BizTalk Server. El sistema permite a los usuarios definir nuevas unidades de administración que se alinean con los flujos de procesos empresariales de extremo a extremo, en lugar de que se requiere para que se ajuste a la forma en que los desarrolladores elegido para empaquetar e implementar componentes de servicio individuales. La figura 1 muestra la pantalla para definir las unidades de administración.  
  
 ![Transacción de definición de BizTalk](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9-BizTalkDefiningTransaction")  
  
 **Figura 1**  
  
 **Definir una transacción como una nueva unidad de administración**  
  
 Después de definir las transacciones, los usuarios pueden instrumentar y mensajes de seguimiento asociados a cada transacción con las mismas herramientas que proporcionan una visibilidad en un único servicio. Estas herramientas pueden exponer las métricas de rendimiento, supervisar el rendimiento en los contratos de nivel de servicio y generar registros de mensajes, como se muestra en la figura 2.  
  
 ![Supervisión de BizTalk](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9-BizTalkMonitoring")  
  
 **Figura 2**  
  
 **Supervisión del rendimiento de extremo a extremo de una canalización**  
  
 Un requisito principal para la regulación de tiempo de ejecución correcta y la supervisión del sistema es la detección de eventos empresariales importantes, como las excepciones y errores de aplicación que se pueden interrumpir el procesamiento lógico empresarial de flujos de transacción. AmberPoint SMS permite a los operadores y los usuarios para obtener una visión general operativa y eventos empresariales y para supervisar el impacto de estos eventos en todos los componentes que dependen del servicio que generó el problema. Además, los operadores y los usuarios pueden resolver rápidamente todo el sistema para identificar la causa de un problema.