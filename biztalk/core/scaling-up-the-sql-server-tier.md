---
title: "Cómo ampliar el nivel de SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- SQL Server, scaling
- scaling, scaling up
- scaling, strategies
ms.assetid: 4352c4af-6861-43d9-b433-9ca25668b439
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c654c4a3b1bba166ae8a49918f6ef31827cf041
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-up-the-sql-server-tier"></a>Escalar el nivel del servidor SQL Server verticalmente
En este modelo, la base de datos de cuadro de mensajes SQL existente se actualiza para escalarse según los requisitos de rendimiento o latencia.  
  
 La siguiente ilustración muestra un caso donde la base de datos de cuadro de mensajes principal se actualiza del servidor del procesador quad al servidor del procesador 8.  
  
 ![Escala &#45; una copia de seguridad MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")  
  
## <a name="when-to-scale-up-the-sql-tier"></a>Cuándo se debe escalar el nivel SQL verticalmente  
  
-   Cuando pueda realizar el escalamiento vertical de la base de datos de cuadro de mensajes principal.  
  
-   Cuando la base de datos de cuadro de mensajes principal forme un cuello de botella. Estos cuellos de botella pueden ser:  
  
    -   **CPU** en el caso de escenarios de orquestación muy caros y complejos, cuadro de mensajes consume muchos recursos de CPU. Escalar el servidor SQL verticalmente, aumentando el número de CPU, debería ampliar el escenario.  
  
    -   **Memoria o E/S** memoria o E/S puede ser el cuello de botella y se pueden actualizar.  
  
-   Cuando el escalamiento vertical resulta más económico que el escalamiento horizontal, y el escalamiento vertical puede solucionar el cuello de botella. Por ejemplo, si la base de datos de cuadro de mensajes principal tiene un problema con la contención de bloqueos de SQL, el escalamiento vertical no puede resolver este problema.  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a>¿Cuándo se decide que no se puede realizar el escalamiento vertical en SQL?  
 El escalamiento vertical no puede solucionar los cuellos de botella de la contención de bloqueos en el nivel SQL. Si se alcanzan estos tipos de cuellos de botella, el escalamiento horizontal resulta una mejor opción que el vertical.  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a>Estrategias y consideraciones para realizar el escalamiento vertical del nivel SQL  
  
-   Realice primero un escalamiento vertical de la base de datos de cuadro de mensajes principal, y luego lleve a cabo el escalamiento horizontal.  
  
-   La base de datos de cuadro de mensajes principal será finalmente el cuello de botella. Por lo tanto, la base de datos de cuadro de mensajes principal debería ser más rápida y más grande (por ejemplo, un equipo de 64 bits basado en Itanium o x64 con doble núcleo).  
  
## <a name="see-also"></a>Vea también  
 [Escalar horizontalmente el nivel de servidor BizTalk Server](../core/scaling-out-the-biztalk-server-tier.md)   
 [Cómo ampliar el nivel de servidor BizTalk Server](../core/scaling-up-the-biztalk-server-tier.md)   
 [Escalar horizontalmente el nivel de servidor SQL](../core/scaling-out-the-sql-server-tier.md)   
 [Hosts de recepción escalados](../core/scaled-out-receiving-hosts.md)   
 [Hosts de procesamiento de escala horizontal](../core/scaled-out-processing-hosts.md)   
 [Hosts de envío de escala horizontal](../core/scaled-out-sending-hosts.md)   
 [Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [Bases de datos de escala horizontal](../core/scaled-out-databases.md)   
 [Agrupación en clústeres las bases de datos de servidor BizTalk Server](../core/clustering-the-biztalk-server-databases1.md)