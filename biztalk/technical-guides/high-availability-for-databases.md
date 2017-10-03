---
title: Alta disponibilidad para bases de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63813d87-1ce4-4645-bb2a-d55e413fcace
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 415b1bbe86df1b7ee3feaeec13c889dfe2a4a902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="high-availability-for-databases"></a>Alta disponibilidad para bases de datos
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]depende en gran medida [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para el almacén de datos y persistencia de los datos. Los demás componentes y hosts de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tienen funciones específicas en el proceso de integrar aplicaciones empresariales diferentes (por ejemplo, recibir, procesar o enrutar mensajes), pero el equipo de la base de datos captura este trabajo y lo almacena en disco. Por ejemplo, cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje entrante, el host de recepción lo conserva en la base de datos de cuadro de mensajes antes de que otros hosts lo recuperen para el procesamiento y envío de orquestaciones. Si la solución de BizTalk implica orquestación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enruta el mensaje en el host que ejecuta el proceso empresarial (host de procesamiento) y guarda el mensaje en la base de datos de cuadro de mensajes cuando finaliza la orquestación. El host de envío recupera entonces el mensaje de la base de datos antes de enviarlo a la aplicación externa a través del adaptador de envío correspondiente.  
  
 Para proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, utilice la agrupación en clústeres de Windows para configurar dos o más equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para crear un clúster de servidores. Esta agrupación de servidores proporciona redundancia y tolerancia a errores para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. A diferencia de la agrupación con equilibrio de carga, en la que un grupo de equipos funciona conjuntamente para aumentar la disponibilidad y la escalabilidad, la agrupación de servidores suele consistir en un par de equipos de base de datos en una configuración activo/pasivo, de modo que un equipo proporciona recursos de copia de seguridad para el otro.  
  
 La siguientes ilustración muestra un nivel de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que obtiene alta disponibilidad mediante una agrupación de servidores de tipo activo/pasivo.  
  
 ![Nivel de base de datos de BizTalk Server](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 Si el equipo de base de datos activo detecta errores o deja de funcionar, el equipo pasivo se vuelve activo y asume el control de los recursos de base de datos hasta que se soluciona el problema. El servicio de base de datos conmuta por error y restaura las conexiones de datos en el nuevo equipo activo y permite que la aplicación de BizTalk siga funcionando.  
  
## <a name="biztalk-server-databases"></a>Bases de datos de BizTalk Server  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instala varias bases de datos en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. La siguiente tabla muestra las características de uso típico de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos.  
  
|Base de datos|Nombre predeterminado de la base de datos|Características de uso|  
|--------------|---------------------------|---------------------------|  
|base de datos de administración|BizTalkMgmtDb|Este uso de baja de los identificadores de base de datos de lectura y las operaciones de escritura.|  
|Base de datos de cuadro de mensajes|BizTalkMsgBoxDb|Esta base de datos identificadores hacen un uso intensivo de lectura y las operaciones de escritura.|  
|Base de datos de seguimiento|BizTalkDTADb|Esta base de datos controla las operaciones de escritura de uso elevado potencialmente según la cantidad de datos que configuran para realizar su seguimiento y las operaciones de lectura de escaso uso.|  
|base de datos de SSO|SSODB|Este uso de baja de los identificadores de base de datos de lectura y las operaciones de escritura.|  
|Base de datos de análisis de BAM|BAMAnalysis|Esto [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] lectura potencialmente hacen uso intensivo de identificadores de base de datos de Analysis Services y escribir operaciones, según el nivel de supervisión realizadas.|  
|Base de datos de esquema de estrella de SAE|BAMStarSchema|Esto [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] lectura potencialmente hacen uso intensivo de identificadores de base de datos de Analysis Services y escribir operaciones, según el nivel de supervisión realizadas.|  
|Base de datos de importación principal de BAM|BAMPrimaryImport|Esto [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] lectura potencialmente hacen uso intensivo de identificadores de base de datos de Analysis Services y escribir operaciones, según el nivel de supervisión realizadas.|  
|Base de datos de archivo SAE|BAMArchive|Esto [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] lectura potencialmente hacen uso intensivo de identificadores de base de datos de Analysis Services y escribir operaciones, según el nivel de supervisión realizadas.|  
|Base de datos del motor de reglas|BizTalkRuleEngineDb|Esta base de datos controla potencialmente escaso uso operaciones de lectura y escritura, a menos que actualice las reglas.|  
|Base de datos de seguimiento de Analysis Services|BizTalkAnalysisDb|Esto [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] lectura hacen un uso intensivo de identificadores de base de datos de Analysis Services y las operaciones de escritura.|  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]las operaciones de tiempo de ejecución utilizan normalmente las primeras cuatro bases de datos (base de datos de administración, las bases de datos de cuadro de mensajes, base de datos de seguimiento y base de datos SSO). Según el tráfico en estas bases de datos, puede colocar en equipos independientes que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. En función de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] funcionalidad que use, puede tener algunas o todas las demás bases de datos en la tabla. Puede escalar horizontalmente y estas bases de datos del clúster según sea necesario.  
  
 Asegúrese de que sigue bueno [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] prácticas recomendadas de implementación, como el uso de discos independientes para cada base de datos. Para obtener más información acerca de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] prácticas recomendadas de implementación, consulte [notas del producto: alta disponibilidad: Always On Technologies](http://go.microsoft.com/fwlink/?LinkId=156812) (http://go.microsoft.com/fwlink/?LinkId=156812).  
  
 Para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, se recomienda que haga lo siguiente:  
  
-   **Configurar la agrupación en clústeres de conmutación por error**. Conmutación por error permite [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para cambiar automáticamente el procesamiento de una instancia de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] desde un servidor que dio error en un servidor en funcionamiento.  
  
     La base de datos de importación principal de BAM recopila datos de eventos. Si se produce un desastre, se perderán los datos que se hayan escrito en la base de datos de importación principal de BAM desde la última copia de seguridad. Porque no hay ninguna manera de volver a generar eventos perdidos, es especialmente importante habilitar la conmutación por error en la base de datos de importación principal de BAM.  
  
-   **Usar SQL Server RAID 1 + 0 (matriz redundante de discos independientes)**, especialmente para la base de datos de cuadro de mensajes y la base de datos de importación principal de BAM.  
  
 Para obtener información acerca de la copia de seguridad de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [prácticas recomendadas para la recuperación ante desastres](../technical-guides/best-practices-for-disaster-recovery.md).  
  
> [!NOTE]  
>  Microsoft [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] y [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] proporcionan una solución de software que se conoce como creación de reflejo de base de datos para aumentar la probabilidad de que una base de datos esté disponible. El uso de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] creación de reflejo de base de datos no está una solución admitida para garantizar la alta disponibilidad de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos debido a posibles problemas que se mantiene la coherencia transaccional en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
>   
>  Para obtener más información acerca de la creación de reflejo de base de datos y las transacciones entre bases de datos en [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], consulte [http://go.microsoft.com/fwlink/?LinkId=87977](http://go.microsoft.com/fwlink/?LinkId=87977). [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]las bases de datos deben instalarse en un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] clúster para asegurar la alta disponibilidad y trasvase de registros debe utilizarse para fines de recuperación ante desastres.  
>   
>  Para obtener más información acerca del trasvase de registros, vea [¿qué es BizTalk Server del trasvase de registros?](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [El servidor BizTalk Server Databases2 de agrupación en clústeres](../technical-guides/clustering-the-biztalk-server-databases2.md)  
  
-   [Ajuste de escala en las bases de datos de servidor BizTalk Server](../technical-guides/scaling-out-the-biztalk-server-databases.md)  
  
## <a name="see-also"></a>Vea también  
 [Planeación de alta disponibilidad2](../technical-guides/planning-for-high-availability2.md)   
 [Alta disponibilidad para los Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [Alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [Recuperación ante desastres](../technical-guides/disaster-recovery.md)