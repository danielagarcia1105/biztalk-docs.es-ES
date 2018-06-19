---
title: Alta disponibilidad para bases de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63813d87-1ce4-4645-bb2a-d55e413fcace
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e17afbf9e33f3e12553d7ded5068370d8ca085
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009365"
---
# <a name="high-availability-for-databases"></a>Alta disponibilidad para bases de datos
BizTalk Server se basa principalmente en SQL Server para almacén de datos y persistencia de los datos. Los demás componentes y hosts de BizTalk Server tienen funciones específicas en el proceso de integrar aplicaciones empresariales diferentes (por ejemplo, recibir, procesar o enrutar mensajes), pero el equipo de la base de datos captura este trabajo y lo almacena en disco. Por ejemplo, cuando el servidor BizTalk Server recibe un mensaje entrante, el host de recepción lo conserva en la base de datos de cuadro de mensajes antes de otros hosts lo recuperen el mensaje de orquestación de procesamiento y el envío. Si la solución de BizTalk implica orquestación, BizTalk Server enruta el mensaje en el host que ejecuta el proceso empresarial (host de procesamiento) y guarda el mensaje en la base de datos de cuadro de mensajes cuando finaliza la orquestación. El host de envío recupera entonces el mensaje de la base de datos antes de enviarlo a la aplicación externa a través del adaptador de envío correspondiente.  
  
 Para proporcionar alta disponibilidad para las bases de datos de BizTalk Server, utilice la agrupación en clústeres de Windows para configurar dos o más equipos que ejecutan SQL Server para crear un clúster de servidores. Esta agrupación de servidores proporciona redundancia y tolerancia a errores para las bases de datos de BizTalk Server. A diferencia de la agrupación con equilibrio de carga, en la que un grupo de equipos funciona conjuntamente para aumentar la disponibilidad y la escalabilidad, la agrupación de servidores suele consistir en un par de equipos de base de datos en una configuración activo/pasivo, de modo que un equipo proporciona recursos de copia de seguridad para el otro.  
  
 La siguientes ilustración muestra un nivel de base de datos de BizTalk Server que obtiene alta disponibilidad mediante una agrupación de servidores de tipo activo/pasivo.  
  
 ![Nivel de base de datos de BizTalk Server](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 Si el equipo de base de datos activo detecta errores o deja de funcionar, el equipo pasivo se vuelve activo y asume el control de los recursos de base de datos hasta que se soluciona el problema. El servicio de base de datos conmuta por error y restaura las conexiones de datos en el nuevo equipo activo y permite que la aplicación de BizTalk siga funcionando.  
  
## <a name="biztalk-server-databases"></a>Bases de datos de BizTalk Server  
 Microsoft BizTalk Server instala varias bases de datos en el servidor SQL Server. La siguiente tabla muestra las características de uso típico de las bases de datos de BizTalk Server.  
  
|Base de datos|Nombre predeterminado de la base de datos|Características de uso|  
|--------------|---------------------------|---------------------------|  
|base de datos de administración|BizTalkMgmtDb|Este uso de baja de los identificadores de base de datos de lectura y las operaciones de escritura.|  
|Base de datos de cuadro de mensajes|BizTalkMsgBoxDb|Esta base de datos identificadores hacen un uso intensivo de lectura y las operaciones de escritura.|  
|Base de datos de seguimiento|BizTalkDTADb|Esta base de datos controla las operaciones de escritura de uso elevado potencialmente según la cantidad de datos que configuran para realizar su seguimiento y las operaciones de lectura de escaso uso.|  
|base de datos de SSO|SSODB|Este uso de baja de los identificadores de base de datos de lectura y las operaciones de escritura.|  
|Base de datos de análisis de BAM|BAMAnalysis|Esta base de datos de SQL Server Analysis Services controla potencialmente hacen uso intensivo operaciones de lectura y escritura, según el nivel de supervisión realizadas.|  
|Base de datos de esquema de estrella de SAE|BAMStarSchema|Esta base de datos de SQL Server Analysis Services controla potencialmente hacen uso intensivo operaciones de lectura y escritura, según el nivel de supervisión realizadas.|  
|Base de datos de importación principal de BAM|BAMPrimaryImport|Esta base de datos de SQL Server Analysis Services controla potencialmente hacen uso intensivo operaciones de lectura y escritura, según el nivel de supervisión realizadas.|  
|Base de datos de archivo SAE|BAMArchive|Esta base de datos de SQL Server Analysis Services controla potencialmente hacen uso intensivo operaciones de lectura y escritura, según el nivel de supervisión realizadas.|  
|Base de datos del motor de reglas|BizTalkRuleEngineDb|Esta base de datos controla potencialmente escaso uso operaciones de lectura y escritura, a menos que actualice las reglas.|  
|Base de datos de seguimiento de Analysis Services|BizTalkAnalysisDb|Identificadores hacen un uso intensivo de lectura y escritura de las operaciones de base de datos de este SQL Server Analysis Services.|  
  
 Las operaciones de tiempo de ejecución de BizTalk Server suelen usan las primeras cuatro bases de datos (base de datos de administración, las bases de datos de cuadro de mensajes, base de datos de seguimiento y base de datos SSO). Según el tráfico en estas bases de datos, que puede colocar en equipos independientes que ejecutan SQL Server. Según la funcionalidad de BizTalk Server que use, podrá utilizar todas o algunas de las demás bases de datos de la tabla. Puede escalar horizontalmente y estas bases de datos del clúster según sea necesario.  
  
 Asegúrese de que sigue buenas prácticas de implementación de SQL Server, como el uso de discos independientes para cada base de datos.  
  
 Para las bases de datos de BizTalk Server, se recomienda que haga lo siguiente:  
  
-   **Configurar la agrupación en clústeres de conmutación por error**. Agrupación en clústeres de conmutación por error permite a SQL Server cambiar automáticamente el procesamiento de una instancia de SQL Server desde un servidor con errores a un servidor en funcionamiento.  
  
     La base de datos de importación principal de BAM recopila datos de eventos. Si se produce un desastre, se perderán los datos que se hayan escrito en la base de datos de importación principal de BAM desde la última copia de seguridad. Porque no hay ninguna manera de volver a generar eventos perdidos, es especialmente importante habilitar la conmutación por error en la base de datos de importación principal de BAM.  
  
-   **Usar SQL Server RAID 1 + 0 (matriz redundante de discos independientes)**, especialmente para la base de datos de cuadro de mensajes y la base de datos de importación principal de BAM.  
  
 Para obtener información acerca de la copia de seguridad de las bases de datos de BizTalk Server, vea [prácticas recomendadas para la recuperación ante desastres](../technical-guides/best-practices-for-disaster-recovery.md).  
  
> [!NOTE]  
>  Microsoft SQL Server proporciona una solución de software que se conoce como creación de reflejo de base de datos para aumentar la probabilidad de que una base de datos esté disponible. El uso de la creación de reflejo de base de datos de SQL Server no es una solución admitida para garantizar la alta disponibilidad de las bases de datos de Microsoft BizTalk Server debido a posibles problemas que se mantiene la coherencia transaccional en las bases de datos de BizTalk Server.  
>   
>  Para obtener más información acerca de la creación de reflejo de base de datos y transacciones entre bases de datos en SQL Server, vea [transacciones - grupos de disponibilidad y creación de reflejo de base de datos](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring). Las bases de datos de BizTalk Server deben instalarse en un clúster de SQL Server para garantizar la alta disponibilidad y el trasvase de registros debe utilizarse para fines de recuperación ante desastres.  
>   
>  Para obtener más información acerca del trasvase de registros, vea [¿qué es BizTalk Server del trasvase de registros?](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Agrupación en clústeres de las bases de datos de BizTalk Server](../technical-guides/clustering-the-biztalk-server-databases2.md)  
  
-   [Escala horizontal de las bases de datos de BizTalk Server](../technical-guides/scaling-out-the-biztalk-server-databases.md)  
  
## <a name="see-also"></a>Vea también  
 [Planeamiento para alta disponibilidad](../technical-guides/planning-for-high-availability2.md)   
 [Alta disponibilidad para los Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [Alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [Recuperación ante desastres](../technical-guides/disaster-recovery.md)