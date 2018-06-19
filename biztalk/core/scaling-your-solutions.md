---
title: Escalar soluciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, scaling
- scaling, scaling out
- scaling, performance
- scaling, about scaling
- scaling, scaling up
- scaling
ms.assetid: e2acbaa4-29d3-4c89-ac1f-c0641cfa0442
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5417e303ea8486ef5bdee8e57c66d4783fb197ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269980"
---
# <a name="scaling-your-solutions"></a>Escalar soluciones
BizTalk Server proporciona una arquitectura que resulta muy adecuada para la escalabilidad. Los patrones de escalamiento que se seleccionen dependerán de la complejidad de su escenario, así como de los requisitos de hardware y de latencia o rendimiento. Es aconsejable comenzar con una topología más pequeña en un principio e intentar escalarla verticalmente o abreviarla en función de las directrices de esta sección.  
  
## <a name="scaling-out-and-scaling-up"></a>Escalar de forma horizontal y vertical  
 El sistema de BizTalk Server puede escalarse de dos formas:  
  
-   El escalamiento horizontal es el proceso que consiste en agregar más equipos. Por ejemplo, si se produce un cuello de botella en BizTalk Server debido a los recursos de CPU, la agregación de otro servidor proporcionaría el doble de recursos de CPU y, con ello, el doble de rendimiento.  
  
-   El escalamiento vertical es el proceso que consiste en actualizar el equipo existente. Por ejemplo, puede actualizar el equipo que tiene instalado BizTalk Server de 4 a 8 procesadores.  
  
 Un sistema de BizTalk Server dispone de dos niveles: el nivel de servidor BizTalk Server y el nivel de SQL Server, que contiene las bases de datos de cuadro de mensajes. Los dos niveles pueden escalarse de forma horizontal o vertical, independientemente del escenario que posea. Por tanto, puede escalar BizTalk Server y la base de datos de cuadro de mensajes de forma horizontal o vertical.  
  
 En la mayoría de los casos, el nivel de BizTalk Server es el primer lugar en que se produce un cuello de botella, por lo que se mejora el rendimiento escalando este nivel de forma horizontal. No obstante, en un momento determinado, en función de la complejidad del sistema y del hardware, es posible que no pueda seguir escalando el nivel de BizTalk de forma horizontal y que se produzca el cuello de botella en el nivel de SQL Server. Por tanto, escalará de forma vertical el nivel de SQL Server y, más adelante, lo escalará de forma horizontal agregando más bases de datos de cuadro de mensajes.  
  
> [!NOTE]
>  Una base de datos de cuadro de mensajes nueva no implica la instalación de otro servidor. Un único servidor SQL Server puede disponer de varias bases de datos de cuadro de mensajes. Además, disponer de varias bases de datos de cuadro de mensajes puede provocar un aumento del costo de DTC y saltos de red cuando las bases de datos se encuentran en distintos equipos.  
  
 En teoría, puede escalar el nivel de SQL Server de forma horizontal cuantas veces desee, siempre que no se sature la base de datos de cuadro de mensajes.  
  
 En los temas de esta sección se describen con mayor detalle los patrones de escalamiento. Además, se explica cómo debe escalarse cada patrón y cómo determinar cuándo no se puede seguir utilizando un patrón determinado de escalamiento en el sistema.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Qué es la escalabilidad?](../core/what-is-scalability.md)  
  
-   [Escalar horizontalmente el nivel de servidor BizTalk Server](../core/scaling-out-the-biztalk-server-tier.md)  
  
-   [Cómo ampliar el nivel de servidor BizTalk Server](../core/scaling-up-the-biztalk-server-tier.md)  
  
-   [Escalar horizontalmente el nivel de servidor SQL](../core/scaling-out-the-sql-server-tier.md)  
  
-   [Cómo ampliar el nivel de SQL Server](../core/scaling-up-the-sql-server-tier.md)  
  
## <a name="see-also"></a>Vea también  
 [Hosts de recepción escalados](../core/scaled-out-receiving-hosts.md)   
 [Hosts de procesamiento de escala horizontal](../core/scaled-out-processing-hosts.md)   
 [Hosts de envío de escala horizontal](../core/scaled-out-sending-hosts.md)   
 [Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [Bases de datos de escala horizontal](../core/scaled-out-databases.md)   
 [Agrupación en clústeres las bases de datos de servidor BizTalk Server](../core/clustering-the-biztalk-server-databases1.md)