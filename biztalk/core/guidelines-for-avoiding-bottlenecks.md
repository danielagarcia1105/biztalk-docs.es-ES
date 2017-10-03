---
title: Directrices para evitar cuellos de botella | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 640ab399-b22d-4f71-b41d-ea8d778e064a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e78f637c2fd6919b4182f2a58b5f16fbd23f0170
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="guidelines-for-avoiding-bottlenecks"></a>Directrices para evitar cuellos de botella
Aunque la configuración predeterminada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona un rendimiento óptimo para muchas configuraciones de hardware y software, en algunas situaciones conviene modificar los valores de configuración o la configuración de implementación. Al configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tenga en cuenta las siguientes directrices sobre rendimiento:  
  
-   Para evitar la contención de recursos, aísle la recepción, la orquestación y el envío en host distintos. Para reducir aún más la contención, aísle el servicio de seguimiento de otros hosts.  
  
-   Si el cuello de botella se produce en el procesamiento de la CPU en BizTalk Server, escale verticalmente BizTalk Server mediante la inclusión de CPU adicionales o la actualización a CPU más rápidas.  
  
## <a name="sql-server-guidelines"></a>Directrices de SQL Server  
 Al configurar Microsoft SQL Server con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tenga en cuenta las siguientes directrices sobre rendimiento:  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]las bases de datos deben configurarse para ejecutarse en una instancia dedicada de SQL Server siempre que sea posible. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]es una aplicación de uso intensivo de bases de datos, por lo que separación de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y los equipos de SQL Server que alojan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mejorará el rendimiento de bases de datos y debe considerarse como un procedimiento recomendado en uno de producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
-   Siempre que sea posible, utilice un subsistema rápido de discos con SQL Server. Utilice una matriz redundante de discos independientes de tipo 5 (RAID5/10) o una red de área de almacenamiento (SAN) con un sistema de alimentación auxiliar.  
  
-   Para realizar copias de seguridad de las bases de datos con regularidad, utilice el proceso de recuperación ante desastres de SQL Server. El servicio de BizTalk Server se recupera automáticamente de problemas de funcionamiento en la conexión con SQL Server.  
  
-   Aísle cada cuadro de mensajes en un servidor independiente de la base de datos de seguimiento de BizTalk (BizTalkDTADb). En el caso de implementaciones más pequeñas, si hay recursos de CPU disponibles, el aislamiento del cuadro de mensajes en un disco físico independiente de la base de datos BizTalkDTADb bastaría.  
  
-   El cuadro de mensajes principal podría ser el cuello de botella debido a una saturación del procesador de la CPU o a la latencia de operaciones de disco (longitud media de la cola del disco). Si el cuello de botella se encuentra en el procesamiento de la CPU, agregue procesadores de CPU al cuadro de mensajes principal. Si no es así, pruebe a deshabilitar la publicación en el cuadro de mensaje principal. De este modo, el cuadro puede controlar con mayor eficacia el enrutamiento de mensajes a las demás bases de datos de cuadro de mensaje.  
  
-   Si el cuello de botella se encuentra en las operaciones de disco, mueva la base de datos BizTalkDTADb a un equipo dedicado con SQL Server o a un disco dedicado. Si el cuello de botella no se encuentra en el procesamiento de la CPU ni en las operaciones de disco en el cuadro de mensajes principal, puede crear nuevas bases de datos de cuadro de mensajes en el mismo equipo de SQL Server para aprovechar el hardware existente.  
  
-   Siga las prácticas recomendadas de SQL Server para aislar los archivos de registro de transacciones y datos de las bases de datos de cuadro de mensajes y BizTalkDTADb en discos físicos diferentes.  
  
-   Asigne suficiente espacio de almacenamiento para los archivos de registro y de datos; en caso contrario, SQL Server consumirá automáticamente todo el espacio disponible en los discos donde se guardan los archivos de registro. El tamaño inicial de los archivos de registro dependerá de los requisitos específicos de cada escenario concreto. Realice una estimación del tamaño medio de los archivos de la implementación según los resultados de la prueba y amplíe el espacio de almacenamiento antes de implementar la solución.  
  
-   Asigne suficiente espacio de almacenamiento para bases de datos que hacen un uso intensivo del disco, como las bases de datos de cuadro de mensaje, de seguimiento y de supervisión de la actividad económica (BAM). Si la solución utiliza el protocolo de mensajería BizTalk Framework, asigne suficiente espacio de almacenamiento para la base de datos de configuración de BizTalk (BizTalkMgmtDb).  
  
-   En función de las necesidades empresariales [períodos de retención de datos] y de la cantidad de datos procesada en el escenario concreto, configure trabajos de archivado y purga en la base de datos de seguimiento, de modo que la base de datos BizTalkDTADb no aumente demasiado. El crecimiento de esta base de datos puede reducir el rendimiento (en especial cuando una base de datos BizTalkDTADb admite varios cuadros de mensajes) ya que, al alcanzar el límite de su capacidad, se establece un límite en la velocidad de inserción de los datos.  
  
-   Escale verticalmente los servidores que alojan las bases de datos de cuadro de mensajes y BizTalkDTADb si éstas generan el cuello de botella. Para escalar verticalmente el hardware, agregue diversas CPU, agregue memoria, actualice a CPU más rápidas y utilice discos dedicados de alta velocidad.