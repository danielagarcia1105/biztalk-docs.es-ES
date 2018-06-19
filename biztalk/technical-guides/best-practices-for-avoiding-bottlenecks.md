---
title: Procedimientos recomendados para evitar cuellos de botella | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81da2e31-dce0-43fb-841f-e65ff99e80a7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08f2291d6aa4d16c251a110bc6f94c6288dc5064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299668"
---
# <a name="best-practices-for-avoiding-bottlenecks"></a>Procedimientos recomendados para evitar cuellos de botella
Aunque la configuración predeterminada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona un rendimiento óptimo para muchas configuraciones de hardware y software, en algunas situaciones conviene modificar los valores de configuración o la configuración de implementación. Al configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tenga en cuenta las siguientes directrices sobre rendimiento:  
  
-   Para evitar la contención de recursos, aísle recepción, la orquestación y envío en hosts independientes. Para reducir aún más la contención, aísle el servicio de seguimiento de otros hosts.  
  
-   Si el procesamiento en el equipo que ejecuta BizTalk Server de la CPU es el cuello de botella, escalar verticalmente el equipo que ejecuta BizTalk Server mediante la inclusión de CPU adicionales o realizar la actualización a CPU más rápidas.  
  
## <a name="sql-server-guidelines"></a>Directrices de SQL Server  
 Al configurar Microsoft SQL Server con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tenga en cuenta las siguientes directrices sobre rendimiento:  
  
-   Siempre que sea posible, utilice un subsistema rápido de discos con SQL Server. Utilice una matriz redundante de discos independientes tipo 10 (RAID10 / 0 + 1) o una red de área de almacenamiento (SAN) con fuente de alimentación de copia de seguridad.  
  
-   Aísle cada base de datos de cuadro de mensajes en un servidor independiente de la base de datos de seguimiento de BizTalk (BizTalkDTADb). Para implementaciones más pequeñas si hay recursos de CPU disponibles, puede ser suficiente aislar la base de datos de cuadro de mensajes en un disco físico independiente de la base de datos de seguimiento de BizTalk.  
  
-   La base de datos de cuadro de mensajes principal podría ser el cuello de botella debido a una saturación del procesador de CPU o de latencia de operaciones de disco (longitud de cola de disco Media). Si el procesamiento de CPU es el cuello de botella, agregue procesadores de CPU en el cuadro de mensajes principal. Si no es así, pruebe a deshabilitar la publicación en la base de datos maestra. De esta forma la base de datos maestra pueden más controlar con eficacia el enrutamiento de mensajes a las otras bases de datos de cuadro de mensajes. La opción para deshabilitar la publicación es válida cuando se utiliza varias bases de datos de cuadro de mensajes.  
  
-   Si las operaciones de disco son el cuello de botella, mueva la base de datos de seguimiento de BizTalk a un equipo dedicado de SQL Server o un disco dedicado. Si las operaciones de disco y procesamiento de CPU en la base de datos de cuadro de mensajes principal no son el cuello de botella, puede crear nuevas bases de datos de cuadro de mensajes en el mismo equipo de SQL Server para aprovechar el hardware existente.  
  
-   Siga las recomendaciones de [optimizar los grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md)para aislar el registro de transacciones y datos de archivos para las bases de datos de cuadro de mensaje y seguimiento de BizTalk en discos físicos diferentes.  
  
-   Asigne suficiente espacio de almacenamiento para los archivos de datos y de registro. En caso contrario, SQL Server consumirá automáticamente todo el espacio disponible en los discos donde se guardan los archivos de registro. El tamaño inicial de los archivos de registro depende de los requisitos específicos en el escenario. Realice una estimación del tamaño medio de los archivos de la implementación según los resultados de la prueba y amplíe el espacio de almacenamiento antes de implementar la solución.  
  
-   Asigne suficiente espacio de almacenamiento para bases de datos de uso de disco de alta, como el cuadro de mensajes, el estado y el seguimiento de actividad (HAT) y la supervisión de la actividad económica (BAM). Si la solución utiliza el protocolo de mensajería BizTalk Framework, asigne suficiente espacio de almacenamiento para la base de datos de configuración de BizTalk (BizTalkMgmtDb).  
  
-   Dependiendo de negocio necesita, como períodos de retención de datos y el volumen de datos procesadas en el escenario, configure el trabajo de agente de SQL Server "Archivo y purga de DTA" en la base de datos de seguimiento de HAT, que la base de datos de seguimiento de BizTalk no aumente demasiado grande. El crecimiento de esta base de datos puede degradar el rendimiento porque alcanzar la capacidad total de la base de datos impone un límite en la velocidad de inserción de datos. Esto es especialmente cierto cuando una base de datos de seguimiento de BizTalk es compatible con varias bases de datos de cuadro de mensajes.  
  
-   Escalar verticalmente los servidores que hospedan las bases de datos de cuadro de mensaje y seguimiento de BizTalk si son el cuello de botella. Puede escalar verticalmente el hardware al agregar CPU, agregar memoria, realizar la actualización a CPU más rápidas y utilizando discos dedicados a alta velocidad.  
  
-   Dividir los archivos de TempDB en varios archivos, puede solucionar problemas de rendimiento relacionados con operaciones de E/S. Como norma general, crea un archivo de datos de archivo por procesador y utilizar el mismo tamaño para todos los archivos creados.  
  
-   Cambio de la base de datos tenga un crecimiento automático configuración en un valor fijo, como 100 a 150 MB. De forma predeterminada que el crecimiento de la base de datos está configurado en un 10%, lo que puede provocar retrasos al crecimiento de las bases de datos más grandes.  
  
-   Memoria de SQL Server debe establecerse en un valor fijo estableciendo Min Server Memory y Max Server Memory en el mismo valor. En general, asignar el 75% de memoria física para SQL Server y dejar el 25% para el resto del sistema operativo y todas las aplicaciones. Si se trata de un servidor dedicado de SQL, puede reducir la cantidad reservada para el sistema operativo en un mínimo de 1GB.  
  
## <a name="see-also"></a>Vea también  
 [Buscar y eliminar los cuellos de botella](../technical-guides/finding-and-eliminating-bottlenecks.md)