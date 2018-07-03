---
title: Arquitectura del escenario de servidor de prueba | Microsoft Docs
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e3afb57-c3ff-4314-9605-cf9fe936e63f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 369286ea2c5c42a53a8e22a7e0b03ac5701db0d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981269"
---
# <a name="test-scenario-server-architecture"></a>Arquitectura de servidor del escenario de prueba
En este tema se proporciona información general del flujo de mensajes entre los servidores durante las pruebas de carga y las arquitecturas diferentes de servidor en el que se realizó la prueba de carga.  
  
## <a name="overview-of-message-flow-during-load-testing"></a>Información general de flujo de mensajes durante las pruebas de carga  
 El diagrama siguiente proporciona una introducción genérica de la arquitectura de servidor que se usa para todos los escenarios de prueba y el flujo de mensajes entre los servidores durante una prueba de carga.  
  
> [!NOTE]  
>  Se describe cada arquitectura de servidor distintas que se ha probado en la sección **arquitectura del servidor de línea base**.  
  
 La ilustración siguiente proporciona información general sobre el flujo de mensajes. Los números en la ilustración corresponden a los pasos indicados en la ilustración siguiente.  
  
 ![Información general del flujo de mensajes](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")  
Información general del flujo de mensajes  
  
1. Las pruebas de carga se inicia el equipo de controlador de carga del agente **VSTS_TestController**:  
  
   - Un proyecto de Visual Studio 2008 en **VSTS_TestController** se ejecuta. El proyecto carga una instancia de la clase BizUnit, carga el archivo de configuración de BizUnit XML especificado y comienza a ejecutar los pasos definidos en el archivo de configuración de BizUnit.  
  
     > [!NOTE]  
     >  Para obtener más información sobre el archivo de configuración XML usando BizUnit, vea el tema "Definir pruebas utilizando un archivo de configuración XML" en [ http://go.microsoft.com/fwlink/?LinkId=143432 ](http://go.microsoft.com/fwlink/?LinkId=143432).  
  
   - Después de completar los pasos de instalación de prueba, uno de los pasos descritos en el proyecto BizUnit ejecuta un comando que muestra un cuadro de diálogo que le pedirá que inicie un "desbloquear" serie de pruebas para enviar mensajes de desbloqueo a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
   - Desbloquear los mensajes se envían desde un proyecto de prueba de Visual Studio 2008 independiente en **VSTS_TestController**. Se envían mensajes de desbloqueo de "preparación" el entorno de prueba mediante la inicialización de las memorias caché del sistema.  
  
   - Después de que se han procesado todos los mensajes de desbloqueo; la instancia de BizUnit contadores del Monitor de rendimiento para todos los equipos que se está probados en la serie de pruebas principal carga y ejecuta un comando para mostrar un cuadro de diálogo que pregunta si desea enviar mensajes para la ejecución de prueba principal.  
  
   - El proyecto de prueba de Visual Studio 2008 de carga en **VSTS_TestController** dirige los equipos de agente de prueba de carga para enviar los mensajes para la ejecución de pruebas principal.  
  
2. La prueba de carga de Test Agent equipos enviar mensajes a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos especificados en el archivo app.config del proyecto de prueba de Visual Studio 2008 de carga en el equipo de controlador de pruebas de carga (**VSTS_TestController**).  
  
3. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos reciben los mensajes enviados por los equipos de agente de prueba de carga, la prueba de carga los mensajes recibidos por una forma de dos de ubicación de recepción de solicitud-respuesta.  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] publica el mensaje en la base de datos de cuadro de mensajes.  
  
   - Los mensajes son consumidos por la orquestación.  
  
   - La orquestación se enlaza a una forma de dos petición-respuesta puerto de envío que invoca el servicio de calculadora de nivel inferior.  
  
   > [!NOTE]  
   >  El servicio de calculadora de nivel inferior se basa en los ejemplos de Windows Communication Foundation se describe en [ http://go.microsoft.com/fwlink/?LinkId=141762 ](http://go.microsoft.com/fwlink/?LinkId=141762). Los ejemplos de Windows Communication Foundation están disponibles para su descarga en [ http://go.microsoft.com/fwlink/?LinkId=87352 ](http://go.microsoft.com/fwlink/?LinkId=87352).  
  
4. El servicio de calculadora consume la solicitud de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y devuelve una respuesta a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puerto de envío de petición-respuesta.  
  
5. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa la respuesta y envía el mensaje de respuesta a la base de datos de cuadro de mensajes. A continuación, se recupera el mensaje de respuesta del servicio web de calculadora de la base de datos de cuadro de mensajes por el puerto de solicitud y respuesta de BizTalk y se entrega un mensaje de respuesta a los equipos de agente de prueba de carga.  
  
## <a name="baseline-server-architecture"></a>Arquitectura del servidor de línea base  
 Para la arquitectura de servidor de línea de base, no se instaló el rol Hyper-V y ambos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SQL Server instaladas en el sistema operativo host. Esto se hacía para establecer las métricas de rendimiento de "línea base" de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución en un entorno de hardware físico.  
  
 La ilustración siguiente representa la física [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y planes de SQL Server de la arquitectura de servidor de línea base.  
  
 ![BizTalk físico &#47; SQL física](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")  
Servidor de BizTalk físico / físico SQL Server (línea de base)  
  
- **BizTalk Server** : 2 equipos con BizTalk Server configurados como sigue:  
  
  - Una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo con **6** GB de RAM y **8** núcleos de procesador disponibles.  
  
  - Una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo con **3** GB de RAM y **4** núcleos de procesador disponibles.  
  
  - Total de 6 + 3 = **9** disponibles GB de RAM y 8 + 4 = **12** núcleos de procesador disponibles para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- **SQL Server** -1 equipo con SQL Server configurado como sigue:  
  
  -   **8** GB de RAM disponible.  
  
  -   **4** núcleos de procesador disponibles.  
  
## <a name="virtual-biztalk-server--physical-sql-server"></a>Servidor de BizTalk virtual / físico SQL Server  
 La ilustración siguiente representa el virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y físicos [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] niveles.  
  
 ![BizTalk virtual &#47; SQL física](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")  
Servidor de BizTalk virtual / físico SQL Server  
  
 En este escenario, se ejecutó la prueba de carga con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecutan en máquinas virtuales de Hyper-V y SQL Server que se ejecuta en hardware físico.  
  
> [!NOTE]  
>  La asignación de núcleos de procesador y RAM que se describe a continuación es idéntica para cada escenarios no previsto, la única diferencia es si determinados equipos están ejecutando en una máquina virtual de Hyper-V o en hardware físico.  
  
- **BizTalk Server** - 3 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]equipos s configurados del modo siguiente:  
  
  - 3 GB de RAM asignado a cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo con un total de 3 x 3 = **9** GB de RAM disponible para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
  - 4 núcleos de procesador asignan a cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo con un total de 3 x 4 = **12** núcleos de procesador disponibles para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- **SQL Server** -1 equipo con SQL Server configurado como sigue:  
  
  -   **8** GB de RAM disponible.  
  
  -   **4** núcleos de procesador disponibles.  
  
## <a name="virtual-biztalk-server--virtual-sql-server"></a>Servidor de BizTalk virtual / Virtual SQL Server  
 La ilustración siguiente representa un virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos host de equipo y un equipo de SQL Server virtual en Hyper-V independiente.  
  
 ![BizTalk virtual &#47; SQL Virtual](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")  
Servidor de BizTalk virtual / Virtual SQL Server  
  
 En este escenario, se ejecutó la prueba de carga con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecutan en máquinas virtuales de Hyper-V y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que se ejecuta en una máquina virtual de Hyper-V. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] máquinas virtuales de Hyper-V y la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquina virtual de Hyper-V se ejecutaron en equipos host de Hyper-V independientes.  
  
> [!NOTE]
>  La asignación de núcleos de procesador y RAM para este escenario es idéntica a la asignación de núcleos de procesador y RAM para el **Virtual BizTalk Server / físico SQL Server** escenario, la única diferencia es que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] era configurado para ejecutarse en una máquina virtual de Hyper-V en lugar de hardware físico.  
  
## <a name="consolidated-environment"></a>Entorno consolidado  
 La ilustración siguiente representa virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consolidaron de equipos y un equipo virtual de SQL Server en un equipo de host de Hyper-V.  
  
 ![BizTalk virtual &#47; SQL Virtual &#47; consolidado](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")  
Entorno consolidado  
  
 En este escenario, se ejecutó la prueba de carga con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecutan en máquinas virtuales de Hyper-V y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que se ejecuta en una máquina virtual de Hyper-V. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] máquinas virtuales de Hyper-V y la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquina virtual de Hyper-V se ejecutaron en el mismo equipo host de Hyper-V.  
  
> [!NOTE]
>  La asignación de núcleos de procesador y RAM para este escenario es idéntica a la asignación de núcleos de procesador y RAM para el **Virtual BizTalk Server / Virtual SQL Server** escenario, la única diferencia es que tanto el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Las máquinas virtuales de Hyper-V y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquinas virtuales de Hyper-V se han configurado para ejecutarse en el mismo equipo host de Hyper-V.  
  
## <a name="see-also"></a>Vea también  
 [Información general del escenario de prueba](../technical-guides/test-scenario-overview.md)