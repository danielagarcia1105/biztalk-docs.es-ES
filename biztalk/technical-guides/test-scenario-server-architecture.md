---
title: Arquitectura del escenario de servidor de prueba | Documentos de Microsoft
ms.custom: 
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e3afb57-c3ff-4314-9605-cf9fe936e63f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34a437cdc306a25d8f5e688880c55530ea9703f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="test-scenario-server-architecture"></a>Arquitectura de servidor del escenario de prueba
Este tema proporciona información general sobre el flujo de mensajes entre los servidores durante las pruebas de carga y las arquitecturas distintas de servidor en el que se realizó la prueba de carga.  
  
## <a name="overview-of-message-flow-during-load-testing"></a>Información general de flujo de mensajes durante las pruebas de carga  
 El siguiente diagrama proporciona una descripción genérica de la arquitectura de servidor que se usa para todos los escenarios de prueba y el flujo de mensajes entre los servidores durante una prueba de carga.  
  
> [!NOTE]  
>  Se describe cada arquitectura de servidor distintos que se probó en la sección **arquitectura de servidor de línea de base**.  
  
 La ilustración siguiente proporciona información general sobre el flujo de mensajes. Los números en la ilustración corresponden a los pasos que figuran en la ilustración.  
  
 ![Información general del flujo de mensajes](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")  
Información general del flujo de mensajes  
  
1.  Pruebas de carga se inicia el equipo de controlador de agente de carga **VSTS_TestController**:  
  
    -   Un proyecto de Visual Studio 2008 en **VSTS_TestController** se ejecuta. El proyecto carga una instancia de la clase BizUnit, carga el archivo de configuración de BizUnit XML especificado y empieza a ejecutar los pasos definidos en el archivo de configuración de BizUnit.  
  
        > [!NOTE]  
        >  Para obtener más información sobre el archivo de configuración XML usado por BizUnit, vea el tema "Definir pruebas utilizando un archivo de configuración XML" en [http://go.microsoft.com/fwlink/?LinkId=143432](http://go.microsoft.com/fwlink/?LinkId=143432).  
  
    -   Después de completar los pasos de configuración de pruebas, uno de los pasos en el proyecto BizUnit ejecuta un comando que muestra un cuadro de diálogo que le pregunta si desea iniciar una prueba de "desbloquear" ejecutar para enviar mensajes de preparar a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
    -   Preparar los mensajes se envían desde un proyecto de prueba de Visual Studio 2008 independiente en **VSTS_TestController**. Preparar los mensajes se envían de "preparación" el entorno de prueba mediante la inicialización de las memorias caché del sistema.  
  
    -   Una vez procesados todos los mensajes de preparar; la instancia de BizUnit contadores del Monitor de rendimiento de todos los equipos que se está probados en la serie de pruebas principales de carga y ejecuta un comando para mostrar un cuadro de diálogo que le pregunta si desea enviar mensajes para que la ejecución de prueba principal.  
  
    -   El proyecto de Visual Studio 2008 la prueba de carga en **VSTS_TestController** dirige los equipos de agente de prueba de carga para enviar mensajes para la ejecución de pruebas principal.  
  
2.  La prueba de carga Test Agent equipos enviar mensajes a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos especificados en el archivo app.config del proyecto de Visual Studio 2008 la prueba de carga en el equipo de controlador de pruebas de carga (**VSTS_TestController**).  
  
3.  El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos reciben los mensajes enviados por los equipos de agente de prueba de carga, la prueba de carga los mensajes recibidos por una forma de dos de ubicación de recepción de solicitud-respuesta.  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]publica el mensaje en la base de datos de cuadro de mensajes.  
  
    -   Los mensajes son consumidos por la orquestación.  
  
    -   La orquestación se enlaza a una forma de dos petición-respuesta puerto de envío que invoca el servicio de calculadora de nivel inferior.  
  
    > [!NOTE]  
    >  El servicio de calculadora de nivel inferior se basa en los ejemplos de Windows Communication Foundation que se describen en [http://go.microsoft.com/fwlink/?LinkId=141762](http://go.microsoft.com/fwlink/?LinkId=141762). Los ejemplos de Windows Communication Foundation están disponibles para su descarga en [http://go.microsoft.com/fwlink/?LinkId=87352](http://go.microsoft.com/fwlink/?LinkId=87352).  
  
4.  El servicio de calculadora consume la solicitud de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y devuelve una respuesta a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puerto de envío de petición-respuesta.  
  
5.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]procesa la respuesta y envía el mensaje de respuesta a la base de datos de cuadro de mensajes. A continuación, se recupera el mensaje de respuesta del servicio web de calculadora de la base de datos de cuadro de mensajes por el puerto de solicitud-respuesta de BizTalk y se entrega un mensaje de respuesta a los equipos de agente de prueba de carga.  
  
## <a name="baseline-server-architecture"></a>Arquitectura del servidor de línea de base  
 Para la arquitectura de servidor de línea de base, no se instaló el rol Hyper-V y ambos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] se instalaron en el sistema operativo host. Esto se hace para establecer las métricas de rendimiento de "línea base" de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución en un entorno de hardware físico.  
  
 La siguiente figura describe físico [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] niveles de la arquitectura de servidor de línea de base.  
  
 ![BizTalk físico &#47; SQL física](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")  
Servidor de BizTalk físico / físico SQL Server (línea de base)  
  
-   **BizTalk Server** : 2 equipos con BizTalk Server configurados del modo siguiente:  
  
    -   Una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo con **6** GB de RAM y **8** núcleos de procesador disponibles.  
  
    -   Una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo con **3** GB de RAM y **4** núcleos de procesador disponibles.  
  
    -   Total de 6 + 3 = **9** GB de RAM disponible y 8 + 4 = **12** núcleos de procesador disponibles para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   **SQL Server** - 1 [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] equipo configurado como se indica a continuación:  
  
    -   **8** GB de RAM disponible.  
  
    -   **4** núcleos de procesador disponibles.  
  
## <a name="virtual-biztalk-server--physical-sql-server"></a>Servidor de BizTalk virtual / físico SQL Server  
 La siguiente figura describe la virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y físicos [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] niveles.  
  
 ![BizTalk virtual &#47; SQL física](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")  
Servidor de BizTalk virtual / físico SQL Server  
  
 En este escenario, se realizó la prueba de carga en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutan en máquinas virtuales de Hyper-V y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] ejecutándose en hardware físico.  
  
> [!NOTE]  
>  La asignación de núcleos de procesador y RAM que se describe a continuación es idéntica para cada línea de base no los escenarios, la única diferencia que se va a si determinados equipos están ejecutando en una máquina virtual de Hyper-V o en el hardware físico.  
  
-   **BizTalk Server** - 3 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]equipos s configurados del modo siguiente:  
  
    -   3 GB de RAM asignada a cada uno de ellos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo con un total de 3 x 3 = **9** GB de RAM disponible para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    -   4 núcleos de procesador asignan a cada uno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo con un total de 4 x 3 = **12** núcleos de procesador disponibles para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   **SQL Server** - 1 [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] equipo configurado como se indica a continuación:  
  
    -   **8** GB de RAM disponible.  
  
    -   **4** núcleos de procesador disponibles.  
  
## <a name="virtual-biztalk-server--virtual-sql-server"></a>Servidor de BizTalk virtual / Virtual SQL Server  
 La figura siguiente muestra un virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo y un virtual [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] equipo en equipos host de Hyper-V independientes.  
  
 ![BizTalk virtual &#47; SQL virtual](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")  
Servidor de BizTalk virtual / Virtual SQL Server  
  
 En este escenario, se realizó la prueba de carga en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutan en máquinas virtuales de Hyper-V y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ejecuta en una máquina virtual de Hyper-V. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] máquinas virtuales Hyper-V y la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquina virtual de Hyper-V se ejecutaban en equipos host de Hyper-V independientes.  
  
> [!NOTE]  
>  La asignación de núcleos de procesador y RAM para este escenario es idéntica a la asignación de núcleos de procesador y RAM para el **Virtual BizTalk Server / físico SQL Server** escenario, la única diferencia es que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] era configurado para ejecutarse en una máquina virtual de Hyper-V en lugar de hardware físico.  
  
## <a name="consolidated-environment"></a>Entorno consolidado  
 La siguiente figura describe virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y un virtual [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] equipo consolidar en un equipo de host de Hyper-V.  
  
 ![BizTalk virtual &#47; Virtual SQL &#47; Consolidar](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")  
Entorno consolidado  
  
 En este escenario, se realizó la prueba de carga en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutan en máquinas virtuales de Hyper-V y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ejecuta en una máquina virtual de Hyper-V. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] máquinas virtuales Hyper-V y la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquina virtual de Hyper-V se ejecutaron en el mismo equipo host de Hyper-V.  
  
> [!NOTE]  
>  La asignación de núcleos de procesador y RAM para este escenario es idéntica a la asignación de núcleos de procesador y RAM para el **Virtual BizTalk Server / Virtual SQL Server** escenario, la única diferencia es que tanto el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Máquinas virtuales de Hyper-V y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquinas virtuales Hyper-V se han configurado para ejecutarse en el mismo equipo host de Hyper-V.  
  
## <a name="see-also"></a>Vea también  
 [Información general del escenario de prueba](../technical-guides/test-scenario-overview.md)