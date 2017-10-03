---
title: "Planeación de alta disponibilidad2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65271fd5-5294-406f-87f8-3aa394c235a2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 310414b094b7175c6b07fc92697b460e6dd2a830
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-high-availability"></a>Planear la alta disponibilidad
La alta disponibilidad de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se centra en la recuperación de componentes funcionales que podrían interrumpir la disponibilidad en una implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Para demostrar la alta disponibilidad en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], tiene que producir un error y medir la eficacia del producto de recuperación. Alta disponibilidad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación, los errores son transparentes para las aplicaciones externas y los sistemas y garantiza que todos los servicios seguirán funcionando correctamente con interrupciones mínimas.  
  
 Diseñar un [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] implementación que proporciona alta disponibilidad es preciso implementar redundancia para cada componentes funcionales que participan en un escenario aplicación integración de proceso de integración o business. [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]simplifica la implementación de estos escenarios separando conceptualmente los datos de la *hosts* que procesar los datos. A *host* es un contenedor lógico de BizTalk elementos, como orquestaciones, controladores de envío y controladores de recepción. Crear *instancias de host* y asignarlas al host. Una instancia de host es la representación física de un host en un servidor específico. Es el [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] proceso de servicio denominado BTSNTSvc.exe u otro proceso, por ejemplo, el proceso IIS. Por lo que proporciona alta disponibilidad para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] implica la ejecución de varios *instancias de host* y agrupación en clústeres los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, como se indica a continuación:  
  
-   **Arquitectura de Hosts de BizTalk**. [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]le permite separar hosts y ejecutar varias instancias de host para proporcionar alta disponibilidad para funciones clave como recibir mensajes, procesar orquestaciones y enviar mensajes. Estos hosts no requieren ningún adicionales de agrupación en clústeres o el mecanismo de equilibrio de carga porque [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] distribuye automáticamente la carga de trabajo entre varios equipos a través de instancias de host. Sin embargo, hospeda está ejecutando los controladores de recepción para los adaptadores de HTTP y SOAP requieren un mecanismo de equilibrio de carga como red equilibrio de carga (NLB) para proporcionar alta disponibilidad y hosts que ejecutan los controladores de recepción de FTP, MSMQ, POP3, SQL y SAP requieren una mecanismo de agrupación en clústeres para proporcionar alta disponibilidad.  
  
    > [!NOTE]  
    >  Siempre debe agrupar el SAP adaptador para dar cabida a un escenario de confirmación en dos fases de recepción.  
  
-   **Arquitectura de bases de datos de BizTalk Server**. Configuración de alta disponibilidad para el [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] bases de datos normalmente consta de dos o más [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos con una configuración de clúster activo/pasivo del servidor de la base de datos. Estos equipos comparten un recurso de disco común (por ejemplo, una RAID 1 + 0 matriz de discos SCSI o una red de área de almacenamiento) y usar la agrupación en clústeres de conmutación por error de Windows para proporcionar copias de seguridad redundancia y tolerancia a errores.  
  
 Otro componente funcional de BizTalk que es crítico para la alta disponibilidad es el servidor secreto principal. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]se basa en este servicio para obtener la clave de cifrado.  
  
 Esta sección proporciona información acerca de cómo obtener alta disponibilidad en cada una de estas categorías. Dado que un [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] solución de alta disponibilidad se basa en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], asegúrese de implementar estos productos con alta disponibilidad antes de configurar los hosts para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]. Los siguientes vínculos incluyen información sobre cómo proporcionar alta disponibilidad a estos productos subyacentes:  
  
-   **Notas del producto: Alta disponibilidad: Always On Technologies** disponible en [http://go.microsoft.com/fwlink/?LinkId=156812](http://go.microsoft.com/fwlink/?LinkId=156812).  
  
-   Obtener más información acerca de cómo solucionar problemas relacionados con Windows Server 2008 en el [Windows Server 2008 implementación, administración y solución de problemas de página](http://go.microsoft.com/fwlink/?LinkId=156813) (http://go.microsoft.com/fwlink/?LinkId=156813).  
  
-   Obtener más información sobre la disponibilidad y escalabilidad en Windows Server 2008 en [disponibilidad y escalabilidad](http://go.microsoft.com/fwlink/?LinkId=156814) (http://go.microsoft.com/fwlink/?LinkId=156814).  
  
-   Consulte la **alta disponibilidad** sección de la [página Windows Server 2008 R2 artículos y notas del producto](http://go.microsoft.com/fwlink/?LinkId=157760) (http://go.microsoft.com/fwlink/?LinkId=157760).  
  
## <a name="understanding-the-impact-of-a-component-failure"></a>Entender el impacto de un error de componente  
 En la tabla siguiente se enumera los componentes y las dependencias de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno y el impacto en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno si se produce un error en la dependencia o un componente. Debe considerar el ámbito de un posible error al decidir si desea una dependencia o un componente del clúster.  
  
|Dependencia o un componente|Ámbito del error|  
|-----------------------------|----------------------|  
|[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]|Todo el sistema. Si [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] , a continuación, se produce un error [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no podrá procesar los documentos.|  
|Servidor secreto principal|Todo el sistema. Si el servidor secreto principal no es correcta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no podrá procesar los documentos. **Nota:** si se produce un error en el servidor secreto principal, cada servidor BizTalk server en el grupo de BizTalk continuarán utilizando una copia en memoria en caché del secreto principal hasta que se reinicie el servicio SSO empresarial en que BizTalk server. Si se reinicia el servicio SSO empresarial en los servidores BizTalk Server, la copia en caché del secreto principal se libera de la memoria y los servidores BizTalk Server deben ser capaz de ponerse en contacto con el servidor secreto principal para obtener otra copia del secreto principal. No se reinicie el servicio de SSO empresarial en los servidores de BizTalk en un grupo si se produce un error en el servidor secreto principal y desea que el servidor BizTalk server para continuar el procesamiento de documentos.|  
|MSDTC|Servidor. Si se produce un error de MSDTC se producirá un error en cualquier componente en el servidor que requiere compatibilidad con transacciones. **Nota:** porque [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y el servidor secreto principal son dependientes de MSDTC para compatibilidad con transacciones, el ámbito del error se convertirá en todo el sistema si se produce un error en el MSDTC en el servidor SQL o el servidor secreto principal. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]requiere compatibilidad con transacciones al comunicarse con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y el servidor secreto principal durante las operaciones de tiempo de ejecución.|  
|Instancia de host de BizTalk|Servidor. Todos los componentes alojados en una instancia de BizTalk Host podrá participar en el procesamiento de documentos si se produce un error en la instancia de host.|  
|Message Queue Server (MSMQ)|Servidor. Si MSMQ se produce un error, a continuación, cualquier procesamiento de documentos que depende el servicio MSMQ, como el adaptador de MSMQ, se detendrá en el servidor.|  
|Sistema de archivos|Servidor. Si se produce un error en el sistema de archivos, a continuación, cualquier procesamiento de documentos que depende el sistema de archivos, por ejemplo, el adaptador de archivo, se detendrá en el servidor.|  
  
 Para poder administrar mejor una alta disponibilidad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema, debe tener un buen conocimiento de la pila de BizTalk: [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], controlador de dominio (DNS, DHCP), [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], IIS server, servidor de archivos, servidor MSMQ, las aplicaciones externas. En esta sección se centra en la alta disponibilidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y dependent [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  
  
## <a name="biztalk-server-high-availability-examples"></a>Ejemplos de alta disponibilidad de servidor BizTalk Server  
 Para los escenarios de ejemplo en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que proporcionar una alta disponibilidad mediante niveles de escala horizontal de hosts, consulte [escenarios de alta disponibilidad de ejemplo de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=156815) (http://go.microsoft.com/fwlink/?LinkId=156815).  
  
## <a name="see-also"></a>Vea también  
 [Alta disponibilidad para los Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [Alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md)   
 [Alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [Lista de comprobación: Aumentar la disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)