---
title: Indicadores de rendimiento clave | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 298d639a-7adf-4f04-b097-a17f4c77ee50
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a03bf76c725f22567d5e884ca22e3a862b15ce3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="key-performance-indicators"></a>Indicadores clave de rendimiento
Este tema proporciona los resultados de pruebas que el grupo de productos de servidor BizTalk Server tenerse en cuenta al usar los siguientes métodos de escalado horizontal:  
  
-   Indicadores de rendimiento (KPI) de clave al aumentar el número de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Para estas pruebas, solo uno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos se configuró para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Estas pruebas se centraron exclusivamente en el impacto de agregar más [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
-   KPI al aumentar el número de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensaje usan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Estas pruebas se centraron exclusivamente en el impacto de agregar más [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensajes a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
-   KPI al aumentar el número de ambos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensaje usan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Estas pruebas mide el efecto de agregarlas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensajes a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
## <a name="analysis-of-key-performance-indicators"></a>Análisis de los indicadores clave de rendimiento  
  
### <a name="messaging-scenario-biztalk-server-scale-out--biztalk-and-sql-kpi"></a>Escenario de mensajería, BizTalk Server-escalabilidad: BizTalk y KPI de SQL  
 Agregar un segundo equipo que ejecuta BizTalk Server no muestra un impacto significativo en el rendimiento global.  Disminuye la carga en la CPU del servidor de BizTalk en un 25%. La CPU para SQL Server ligeramente aumenta de 59% 59.8% cuando el segundo equipo que ejecuta BizTalk Server se agrega al grupo de BizTalk Server. Más allá de este punto, se obtiene ninguna ventaja de rendimiento adicional si aumenta el número de servidores de procesamiento de BizTalk.  
  
 Cada instancia de host de BizTalk sondea periódicamente la cola apropiada en el cuadro de mensajes. Cualquier mensaje que se hace referencia en la cola de host se almacena realmente en el conjunto compartido de tablas en el cuadro de mensajes. Si el rendimiento disminuye al agregar más equipos que ejecutan BizTalk Server, una causa frecuente es demasiada actividad en las tablas compartidas dentro de la base de datos de cuadro de mensajes. Una ruta de E/S dedicada para SQL Server a estas tablas se puede crear mediante la asignación de estas tablas a un grupo de archivos específico.  
  
 [Optimizar los grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md) proporciona instrucciones sobre cómo asignar tablas a grupos de archivos específicos. El script incluido en [Script SQL de grupos de archivos de base de datos de cuadro de mensajes de BizTalk Server](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md) de la guía indica cómo puede hacerlo. Sólo se debe considerar la ampliación horizontal a una configuración de cuadro de mensajes múltiples después de distribuir objetos de cuadro de mensajes a través de varios grupos de archivos, y después de que se han aplicado todas las otras optimizaciones relacionadas con SQL.  
  
 **Porcentaje de utilización de CPU de SQL Server y BizTalk Server**  
  
 ![M &#45; SingleMsgBox](../technical-guides/media/m-singlemsgbox.gif "SingleMsgBox M")  
  
### <a name="messaging-scenario-biztalk-server-and-sql-server-scale-out--biztalk-and-sql-kpi"></a>Escenario de mensajería, BizTalk Server y SQL Server-escalabilidad: BizTalk y KPI de SQL  
 Esta prueba se realiza para determinar la eficacia de escalar horizontalmente el nivel de SQL Server mediante la adición de cuatro bases de datos de cuadro de mensajes. En este escenario, agregar hasta dos equipos que ejecuten BizTalk Server habilita un rendimiento máximo sostenible de 2,790 mensajes por segundo. Esto resultaba 118% mayor que el máximo rendimiento puede obtenerse cuando se usa un único cuadro de mensajes. Más allá de este punto, agregar más capacidad de procesamiento en el nivel de servidor BizTalk Server disminución del rendimiento en un modo similar al escenario de cuadro de mensaje único.  
  
 Las conclusiones claves de las pruebas de un escenario de mensajería son que el escalado de BizTalk Server es una técnica eficaz para aumentar el rendimiento global si contención en SQL Server no es un cuello de botella. Si la base de datos de cuadro de mensajes se convierte en un punto de contención, aplique primero las optimizaciones que se detallan en [optimizar el rendimiento de base de datos](../technical-guides/optimizing-database-performance.md), especialmente la secuencia de comandos de optimización de grupo de archivos que se describe en [BizTalk Server Script de SQL de grupos de archivos de base de datos de cuadro de mensajes](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md) para distribuir la carga de E/S. Si todavía no puede lograr el rendimiento deseado, considere la posibilidad de escalado horizontal agregando más bases de datos de cuadro de mensajes.  
  
 **Porcentaje de utilización de CPU de SQL Server y BizTalk Server**  
  
 ![M &#45; MultipleMsgBox](../technical-guides/media/m-multiplemsgbox.gif "MultipleMsgBox M")  
  
### <a name="orchestration-scenario-biztalk-server-scale-out--sql-server-and-biztalk-server-kpi"></a>Escenario de orquestación, BizTalk Server-escalabilidad: SQL Server y KPI de BizTalk Server  
 Agregar un segundo equipo que ejecuta BizTalk Server no muestra un impacto significativo en el rendimiento global. Disminuye la carga en la CPU del servidor de BizTalk 23 por ciento. La CPU para SQL Server aumenta de porcentaje de 66.5 a 68.5 porcentaje cuando se agrega un equipo adicional que se ejecuta BizTalk Server.  
  
 **Porcentaje de utilización de CPU de SQL Server y BizTalk Server**  
  
 ![Co &#45; SingleMsgBox](../technical-guides/media/o-singlemsgbox.gif "O SingleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-and-sql-server-scale-out--sql-server-and-biztalk-server-kpi"></a>Escenario de orquestación, BizTalk Server y SQL Server-escalabilidad: SQL Server y KPI de BizTalk Server  
 Esta prueba se realiza para determinar la eficacia de escalar horizontalmente el servidor BizTalk Server y el SQL Server mediante la adición de más equipos que ejecutan BizTalk Server y varias bases de datos de cuadro de mensajes para el escenario de orquestación. En este escenario, el agregar hasta dos equipos que ejecuten BizTalk Server habilitado un rendimiento máximo sostenible de 1,487 orquestaciones por segundo. Esto resultaba 116% mayor que el número máximo de resultados puede obtenerse con un único cuadro de mensajes. Escalado horizontal con cuatro bases de datos de cuadro de mensajes en equipos independientes de SQL Server admite el aumento del rendimiento debido a la potencia de procesamiento adicional y la capacidad de distribuir la carga de la base de datos entre varias bases de datos de cuadro de mensajes. Esta táctica también evita la contención en tablas compartidas, que era un cuello de botella en el entorno de cuadros de mensaje único. Al igual que con el escenario de mensajería, aumentar el número de bases de datos de cuadro de mensajes y la distribución de estos en todas las instancias SQL dedicadas permite la adición de varios equipos de servidor BizTalk Server al grupo de BizTalk Server.  
  
 **Porcentaje de utilización de CPU de SQL Server y BizTalk Server**  
  
 ![Co &#45; MultipleMsgBox](../technical-guides/media/o-multiplemsgbox.gif "O MultipleMsgBox")  
  
## <a name="see-also"></a>Vea también  
 [Ajuste de escala en un entorno de BizTalk Server de producción](../technical-guides/scaling-a-production-biztalk-server-environment.md)