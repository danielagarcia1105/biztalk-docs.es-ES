---
title: Indicadores de rendimiento clave | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 298d639a-7adf-4f04-b097-a17f4c77ee50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f808299dd0df0c47b169a831a7f09b33e59dc799
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966141"
---
# <a name="key-performance-indicators"></a>Indicadores clave de rendimiento
Este tema proporciona los resultados de pruebas que el grupo de BizTalk Server asociado al uso de los siguientes métodos de escalado horizontal:  
  
- Indicadores de rendimiento (KPI) de clave al aumentar el número de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Para estas pruebas, solo uno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensajes se configuró para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Estas pruebas se centraron exclusivamente en el impacto de agregar más [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
- KPI al aumentar el número de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos utilizados por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Estas pruebas se centraron exclusivamente en el impacto de agregar más [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensajes a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
- KPI al aumentar el número de ambos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos utilizados por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Estas pruebas mide el impacto de agregar ambos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensajes a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
## <a name="analysis-of-key-performance-indicators"></a>Análisis de los indicadores clave de rendimiento  
  
### <a name="messaging-scenario-biztalk-server-scale-out--biztalk-and-sql-kpi"></a>Escenario de mensajería, BizTalk Server escalada – BizTalk y KPI de SQL  
 Agregar un segundo equipo que ejecuta BizTalk Server no muestra un impacto significativo en el rendimiento general.  Reduce la carga en la CPU del servidor de BizTalk en un 25%. La CPU para SQL Server marginalmente aumenta de 59% a % 59.8 cuando el segundo equipo que ejecuta BizTalk Server se agrega al grupo de BizTalk Server. Más allá de este punto, no se obtuvo ninguna ventaja adicional del rendimiento si aumenta el número de servidores de procesamiento de BizTalk.  
  
 Cada instancia de host de BizTalk sondea periódicamente la cola adecuada en el cuadro de mensajes. Cualquier mensaje que se hace referencia en la cola de host se almacena dentro del conjunto de tablas en el cuadro de mensajes compartido. Si el rendimiento desciende al agregar más equipos que ejecutan BizTalk Server, una causa común es demasiada actividad en las tablas dentro de la base de datos compartidas. Una ruta de E/S dedicada para SQL Server a estas tablas se puede crear mediante la asignación de estas tablas a un grupo de archivos específico.  
  
 [Optimización de los grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md) se proporcionan instrucciones sobre cómo asignar tablas a grupos de archivos específicos. El script incluido en [Script de SQL de grupos de archivos de base de datos de BizTalk Server MessageBox](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md) de la guía le indica cómo puede lograr esto. Sólo se debe considerar el escalado horizontal a una configuración de cuadro de mensajes de varias después de la distribución de los objetos de cuadro de mensajes a través de varios grupos de archivos, y después de que se hayan aplicado todas las demás optimizaciones relacionadas con SQL.  
  
 **Porcentaje de utilización de CPU de SQL Server y BizTalk Server**  
  
 ![M&#45;SingleMsgBox](../technical-guides/media/m-singlemsgbox.gif "M SingleMsgBox")  
  
### <a name="messaging-scenario-biztalk-server-and-sql-server-scale-out--biztalk-and-sql-kpi"></a>Escenario de mensajería, BizTalk Server y SQL Server horizontal: BizTalk y KPI de SQL  
 Esta prueba se realiza para determinar la eficacia de escalar horizontalmente el nivel de SQL Server mediante la adición de cuatro bases de datos de cuadro de mensajes. En este escenario, la adición de hasta dos equipos que ejecutan BizTalk Server habilitado un rendimiento máximo sostenible de 2,790 mensajes por segundo. Esto fue 118% mayor que el rendimiento máximo que puede obtenerse al usar un único cuadro de mensaje. Más allá de este punto, agregar más capacidad de procesamiento para el nivel de BizTalk Server disminución del rendimiento de manera similar al escenario de cuadro de mensaje único.  
  
 Las conclusiones clave de las pruebas del escenario de mensajería son que el escalado horizontal de BizTalk Server es una técnica eficaz para aumentar el rendimiento general si la contención en SQL Server no es un cuello de botella. Si la base de datos se convierte en un punto de contención, aplique primero las optimizaciones que se detallan en [optimización del rendimiento de base de datos](../technical-guides/optimizing-database-performance.md), especialmente la secuencia de comandos de optimización de grupo de archivos que se describe en [BizTalk Server Script de SQL de grupos de archivos de base de datos de cuadro de mensajes](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md) para distribuir la carga de E/S. Si todavía no puede lograr el rendimiento deseado, considere la posibilidad de escalar horizontalmente agregando más bases de datos de cuadro de mensajes.  
  
 **Porcentaje de utilización de CPU de SQL Server y BizTalk Server**  
  
 ![M&#45;MultipleMsgBox](../technical-guides/media/m-multiplemsgbox.gif "M MultipleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-scale-out--sql-server-and-biztalk-server-kpi"></a>Escenario de orquestación, BizTalk Server escalada – SQL Server y KPI de BizTalk Server  
 Agregar un segundo equipo que ejecuta BizTalk Server no muestra un impacto significativo en el rendimiento general. Reduce la carga en la CPU del servidor de BizTalk en un 23%. La CPU para SQL Server aumenta por ciento 66.5 por ciento 68.5 cuando se agrega un equipo adicional que ejecuta BizTalk Server.  
  
 **Porcentaje de utilización de CPU de SQL Server y BizTalk Server**  
  
 ![O&#45;SingleMsgBox](../technical-guides/media/o-singlemsgbox.gif "O SingleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-and-sql-server-scale-out--sql-server-and-biztalk-server-kpi"></a>Escenario de orquestación, BizTalk Server y SQL Server horizontal: SQL Server y KPI de BizTalk Server  
 Esta prueba se realiza para determinar la eficacia de escalar horizontalmente el servidor BizTalk Server y el servidor de SQL mediante la adición de más equipos que ejecutan BizTalk Server y más bases de datos de cuadro de mensajes para el escenario de orquestación. En este escenario, la adición de hasta dos equipos que ejecutan BizTalk Server habilitado un rendimiento máximo sostenible de 1,487 orquestaciones por segundo. Esto fue 116% mayor que el número máximo de resultados puede obtenerse con un único cuadro de mensajes. Escalado horizontal a cuatro bases de datos en equipos independientes de SQL Server admite el aumento del rendimiento debido a la potencia de procesamiento adicional y la capacidad de distribuir la carga de la base de datos entre varias bases de datos de cuadro de mensajes. Esta táctica también alivia la contención en las tablas compartidas, lo que era un cuello de botella en el entorno de cuadros de mensaje único. Al igual que con el escenario de mensajería, aumentar el número de bases de datos y distribuir estas entre instancias SQL dedicadas permiten la adición de varios equipos de BizTalk Server al grupo de BizTalk Server.  
  
 **Porcentaje de utilización de CPU de SQL Server y BizTalk Server**  
  
 ![O&#45;MultipleMsgBox](../technical-guides/media/o-multiplemsgbox.gif "O MultipleMsgBox")  
  
## <a name="see-also"></a>Vea también  
 [Escalado de un entorno de producción de BizTalk Server](../technical-guides/scaling-a-production-biztalk-server-environment.md)