---
title: Alta disponibilidad mediante SQL Server grupos de disponibilidad AlwaysOn | Microsoft Docs
description: Grupo de la base de datos de BizTalk Server en nodos diferentes para obtener una solución de alta disponibilidad (HA) mediante SQL Server siempre en disponibles grupos (AG), incluidos los requisitos del sistema y las limitaciones. Siempre en AG requiere clústeres de conmutación por error de servidor de Windows (WSFC).
ms.custom: ''
ms.date: 06/27/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4511a578-77d2-49ee-99bd-f0406ad625d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24a72698a97aa79ccd1b748a390f8e919ff0717f
ms.sourcegitcommit: 6379723045cf05ed36f2bc500f6b41be1135f47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2018
ms.locfileid: "37069401"
---
# <a name="high-availability-using-sql-server-always-on-availability-groups---biztalk-server"></a>Alta disponibilidad mediante SQL Server en grupos de disponibilidad Always - servidor BizTalk Server
Configurar la alta disponibilidad mediante grupos de disponibilidad AlwaysOn de SQL Server.

> [!TIP]
> [Configuración de BizTalk Server 2016 con la disponibilidad de grupos de laboratorio](https://skastberg.wordpress.com/2017/02/22/setting-up-my-biztalk-server-2016-using-availability-groups-lab/) proporciona una guía paso a paso escrita por un ingeniero de campo de Microsoft. Esta se basa en un entorno de laboratorio e incluye algunas observaciones. Mira esto.  
> 
> [!IMPORTANT]
> * Grupos de disponibilidad AlwaysOn está disponible a partir de SQL Server 2016. Si usa una versión anterior de SQL Server, en este tema no se aplica a usted. 
> * BizTalk Server 2016 admite el modo de confirmación sincrónica; no se admite el modo de confirmación asincrónica. Recuperación ante desastres, se recomienda configurar el trabajo de copia de seguridad de BizTalk Server y usar el trasvase de registros. Consulte [copia de seguridad y restaurar bases de datos de servidor de BizTalk](../core/backing-up-and-restoring-biztalk-server-databases.md) para obtener detalles concretos.
> 
>    [Modos de disponibilidad](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/availability-modes-always-on-availability-groups) se detallan las opciones de confirmación con grupos de disponibilidad AlwaysOn. 


## <a name="background-and-history"></a>En segundo plano y el historial

BizTalk Server se basa principalmente en SQL Server para la persistencia de datos. Otros componentes y hosts de BizTalk Server tienen funciones específicas al integrar aplicaciones empresariales diferentes, por ejemplo, recibir, procesar o enrutar mensajes. El equipo de base de datos captura este trabajo y lo almacena en disco. 

BizTalk utiliza el trasvase de registros y clústeres de conmutación por error de SQL Server para proporcionar alta disponibilidad, copia de seguridad y restauración y recuperación ante desastres para sus bases de datos de forma local. En Azure IaaS (máquinas virtuales de Azure), las versiones anteriores de SQL Server no admiten las instancias de clúster de conmutación por error (no hay compatibilidad MSDTC). Como resultado, BizTalk no tenía una solución de alta disponibilidad al usar máquinas virtuales de Azure.

A partir de SQL Server 2016, los grupos de disponibilidad AlwaysOn de SQL Server es compatible con MSDTC para un entorno local y el uso de máquinas virtuales de Azure. Como resultado, la característica AlwaysOn de SQL Server 2016 se admite para las bases de datos BizTalk local o en escenarios de IaaS de Azure. 

## <a name="sql-server-2016-alwayson-availability-groups"></a>Grupos de disponibilidad AlwaysOn de SQL Server 2016 
Implementación de grupos de disponibilidad AlwaysOn requiere un clúster de clústeres de conmutación por error de servidor de Windows (WSFC). Cada réplica de disponibilidad de un determinado grupo de disponibilidad debe residir en otro nodo del mismo clúster de WSFC. Por cada grupo de disponibilidad que cree, se creará un grupo de recursos de WSFC. El clúster de WSFC supervisa este grupo de recursos para evaluar el estado de la réplica principal.  

En la ilustración siguiente se muestra un grupo de disponibilidad que contiene solo una réplica principal y cuatro réplicas secundarias.  
 
 ![SQLAG_PrimaryReplica](../core/media/sqlag-primaryreplica.png)

Los clientes pueden conectarse a la réplica principal de un grupo de disponibilidad determinado mediante un agente de escucha del grupo de disponibilidad. Un agente de escucha del grupo de disponibilidad proporciona un conjunto de recursos que están conectados a un grupo de disponibilidad determinado para dirigir las conexiones de cliente a la réplica de disponibilidad adecuada. 

>[!IMPORTANT]
> SQL Server 2016 admiten MSDTC con grupos de disponibilidad AlwaysOn (AG) en Windows Server 2016 y Windows Server 2012 R2. **Windows Server 2012 R2** requiere la [3090973](https://support.microsoft.com/kb/3090973) revisión de Windows para instalarse. 
> **Windows Server 2016** requiere que el [clave del registro de RemoteAccessEnabled](https://support.microsoft.com/kb/3182294) habilitarse.

SQL Server no es compatible con MSDTC con grupos de disponibilidad AlwaysOn para las versiones anteriores a 2016.  

MSDTC entre bases de datos en la misma instancia de SQL Server no es compatible con grupos de disponibilidad AlwaysOn de SQL Server. Esto significa que no hay dos bases de datos de BizTalk en una transacción distribuida se pueden hospedar en la misma instancia SQL server. Para mantener la coherencia transaccional, que participan en transacciones distribuidas de bases de datos de BizTalk deben hospedarse en instancias diferentes de SQL server. Tenga en cuenta que no importa si las instancias de SQL se encuentran en el mismo equipo o en equipos diferentes. 


## <a name="provide-high-availability-for-biztalk-databases-using-alwayson-availability-groups"></a>Proporcionar alta disponibilidad para bases de datos de BizTalk mediante grupos de disponibilidad AlwaysOn 
En la configuración básica de BizTalk Server, un mínimo de 9 bases de datos se crean como reglas y BAM bases de datos. Debido a la MSDTC limitación con grupos de disponibilidad se ha mencionado anteriormente, una configuración como siguiente no garantiza la coherencia transaccional. 

![SQLAG_NoTrans](../core/media/sqlag-notrans.gif)
 
Se recomienda que las bases de datos de BizTalk Server se agrupan en las siguientes cuatro instancias de SQL Server:
 
| Instancia |Rol |Bases de datos de ese grupo de BizTalk  |
|--- | --- | ---|
|1 |Autenticación |SSODB|
|2 |Administración |BizTalkMgmtDb| 
|3 |Tiempo de ejecución |BizTalkMsgBoxDb<br/> BizTalkRulesEngineDb<br/> BAMPrimaryImport<br/>BAMStarSchema <br/>BAMAlertsApplication |
|4 |Seguimiento |BizTalkDTADb<br/>EsbItineraryDb<br/>EsbExceptionDb | 
 
En un escenario de cuadro de mensajes de escala horizontal (una configuración con más de un cuadro de mensaje), hay más de una base de datos de cuadro de mensajes, y cada base de datos de cuadro de mensajes debe estar en su propia instancia de SQL Server. 

BizTalk Server también depende de SQL Server Analysis Services y SQL Server Integration Services para el análisis de BAM y de archivado. SQL Server no proporciona una solución de alta disponibilidad para Integration Services o Analysis Services en IaaS de Azure. Por lo tanto, se recomienda utilizar otra instancia de SQL Server independiente para las bases de datos BAMArchive y BAMAnalysis Analysis Services. Para las instalaciones locales, la instancia de agrupación en clústeres de conmutación por error de SQL puede utilizarse para establecer una configuración de alta disponibilidad. 

Esta configuración es se muestra a continuación y se recomienda para bases de datos de BizTalk en grupos de disponibilidad:  

![SQLAG_Recommended](../core/media/sqlag-recommended.png)
 
Junto con las bases de datos de SQL Server, configuración de BizTalk Server también crea los inicios de sesión de seguridad de SQL Server y trabajos del Agente SQL. Grupos de disponibilidad AlwaysOn solo proporcionan la capacidad para administrar las bases de datos dentro de un grupo de disponibilidad. Inicios de sesión y trabajos del Agente SQL de BizTalk deben crearse y actualizado o administrarse manualmente en todas las réplicas de disponibilidad.  

> [!NOTE]
> SQL Server 2016 Service Pack 2 es compatible con las transacciones de DTC entre varias bases de datos dentro del mismo grupo de disponibilidad. BizTalk Server es compatible con esta funcionalidad a partir de CU5.

La siguiente lista de inicios de sesión de seguridad de SQL Server están asociados con BizTalk Server. Puede tener inicios de sesión adicionales creados para las aplicaciones de BizTalk Server. Si es así, debe replicarlos en cada instancia de SQL Server que hospeda una réplica de bases de datos de BizTalk. 

1. Usuarios de aplicación de BizTalk (uno o más correspondiente a cada Host en proceso) 
2. Usuarios de hosts aislados de BizTalk (uno o más correspondiente a cada Host aislado) 
3. Administradores de servidor BizTalk Server 
4. Operadores B2B de BizTalk Server 
5. Operadores de servidor BizTalk Server 
6. Administradores de SSO 
7. Usuario de alertas de BAM 
8. Usuario de servicio web de administración de BAM 
9. Cuenta de servicio de actualización de motor de reglas 

Si ha creado hosts adicionales o creará hosts adicionales más adelante, habrá nuevos inicios de sesión SQL creados como parte de este proceso. Hay que asegurarse de crear estos inicios de sesión SQL manualmente en las réplicas correspondientes.

Los siguientes trabajos del Agente SQL Server están asociados a BizTalk Server. Los trabajos instalados en cada servidor son diferentes según las características instaladas y configuradas. La mayoría de estos trabajos se crea durante la configuración de BizTalk Server. Algunos se crean al configurar el envío de registro. Estos trabajos deben replicarse en cada instancia de réplica de hospedaje de SQL Server de su base de datos de BizTalk correspondiente. Esto debe realizarse manualmente. 

- BizTalkMgmtDb trabajos: 
    - Copia de seguridad de BizTalk Server (BizTalkMgmtDb) 
    - CleanupBTFExpiredEntriesJob_BizTalkMgmtDb 
    - Supervisar el servidor BizTalk Server (BizTalkMgmtDb) 
- BizTalkMsgBoxDb trabajos: 
    - MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb 
    - MessageBox_Message_Cleanup_BizTalkMsgBoxDb
    - MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb
    - MessageBox_Parts_Cleanup_BizTalkMsgBoxDb 
    - MessageBox_UpdateStats_BizTalkMsgBoxDb 
    - Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 
    - PurgeSubscriptionsJob_BizTalkMsgBoxDb 
    - TrackedMessages_Copy_BizTalkMsgBoxDb 
- Trabajos en msgboxes adicionales
- Trabajo de BizTalkDTADb: 
    - DTA Purge and Archive (BizTalkDTADb) 
- Trabajo BizTalkRulesEngineDb: 
    - Rules_Database_Cleanup_BizTalkRuleEngineDb 
- Trabajo BAMAlertsApplication: 
    - 0 o más DelAlertHistJob 

A diferencia de instancias de agrupación en clústeres de conmutación por error de SQL Server, en grupos de disponibilidad todas las réplicas son activa, en ejecución y disponible. Cuando los trabajos del Agente SQL se duplican en cada réplica para la conmutación por error, se ejecutan contra la réplica correspondiente, independientemente de si está actualmente en el rol principal o secundaria. Para asegurarse de que estos trabajos se ejecutan solo en la réplica principal actual, cada paso de cada trabajo debe incluirse dentro de un bloque IF, tal como se muestra: 

    ```
    IF (sys.fn_hadr_is_primary_replica(‘dbname’) = 1)  
    BEGIN  
    …  
    END
    ```
  
Reemplace `‘dbname’` con el nombre de base de datos correspondiente en la que el trabajo está configurado para ejecutarse. El ejemplo siguiente muestra este cambio para TrackedMessages_Copy_BizTalkMsgBoxDb en BizTalkMsgBoxDb: 
 
 ![SQLAG_AgentJob](../core/media/sqlag-agentjob.gif)

### <a name="configure-biztalk-when-availability-groups-are-already-set-up"></a>Configuración de BizTalk cuando ya haya configurado los grupos de disponibilidad

1. Compruebe los requisitos del sistema operativo: 
2. En todos los **Windows Server 2012 R2** los equipos, instalar el [revisión 3090973 de MSDTC](https://support.microsoft.com/kb/3090973) (abre un artículo de KB)
3. En todos los **Windows Server 2016** equipos, habilite la [clave del registro de RemoteAccessEnabled](https://support.microsoft.com/kb/3182294) (abre un artículo de KB)
4. Asegúrese de tener al menos cuatro instancias diferentes de SQL que hospedarán las bases de datos distintos de BizTalk. Las réplicas secundarias también se deben configurar en distintas instancias de SQL. Esto da como resultado un mínimo de 8 instancias SQL (1 principal y 1 réplica secundaria para cada una de las instancias de 4) y un mínimo de 4 grupos de disponibilidad. Vea la ilustración anterior para esta configuración de grupo de disponibilidad. Asegúrese de que los grupos de disponibilidad se crean con el **soporte de DTC por base de datos** opción ya no se puede cambiar más adelante. 
5. Al configurar BizTalk Server y especificando el nombre SQL server, usar nombre de agente de escucha del grupo de disponibilidad en lugar del nombre real del equipo. Esto crea las bases de datos de BizTalk, los inicios de sesión y trabajos del Agente SQL en la réplica principal actual. 
6. Detener el procesamiento de BizTalk (instancias de Host, el servicio de inicio de sesión único, IIS, servicio de actualización de motor de reglas, BAMAlerts Service etc.) y detener los trabajos del Agente SQL. 
7. Ahora, agregue las bases de datos de BIzTalk a los grupos de disponibilidad respectivo. 
8. Incluya el cuerpo de los pasos de trabajo del Agente SQL en `IF` bloque (mencionado anteriormente) para asegurarse de que ejecute sólo si el destino es la réplica principal. 
9. Secuencia de comandos los inicios de sesión y trabajos del Agente SQL para replicarlas en réplica correspondiente. 
10. Replicación SQL DBMail perfil y cuenta para las alertas de BAM en instancias SQL correspondientes que hospeda la réplica secundaria. 
11. Si va a agregar una base de datos de cuadro de mensaje adicionales o implementar una nueva actividad/vista de BAM posterior, nueva, a continuación, se crean trabajos SQL para nuevas bases de datos de cuadro de mensaje o la base de datos de alertas de BAM en la réplica principal actual. Asegúrese de que para poder editarlo en la réplica principal y, a continuación, crearlos manualmente en las réplicas secundarias correspondientes. 

Esta configuración también se puede realizar con las instancias de SQL que hospeda la réplica principal. En este caso, después de la configuración de BizTalk, ejecute el `UpdateDatabase.vbs` y `UpdateRegistry.vbs` scripts en los equipos de BizTalk después de los pasos anteriores. Esto se explica con más detalle en la sección siguiente.  
 
### <a name="move-existing-biztalk-databases-to-availability-groups"></a>Mover bases de datos de BizTalk existentes a grupos de disponibilidad

1. Compruebe los requisitos del sistema operativo: 
2. En todos los **Windows Server 2012 R2** los equipos, instalar el [revisión 3090973 de MSDTC](https://support.microsoft.com/kb/3090973) (abre un artículo de KB)
3. En todos los **Windows Server 2016** equipos, habilite la [clave del registro de RemoteAccessEnabled](https://support.microsoft.com/kb/3182294) (abre un artículo de KB)
4. Asegúrese de tener al menos cuatro instancias diferentes de SQL que hospedarán las bases de datos distintos de BizTalk. Las réplicas secundarias también se deben configurar en distintas instancias de SQL. Esto da como resultado un mínimo de 8 instancias SQL (1 principal y 1 réplica secundaria para cada una de las instancias de 4) y un mínimo de 4 grupos de disponibilidad. Vea la ilustración anterior para esta configuración de grupo de disponibilidad. Asegúrese de que los grupos de disponibilidad se crean con **soporte de DTC por base de datos** opción ya no se puede cambiar más adelante.  
5. Detener el procesamiento de BizTalk y los trabajos del Agente SQL. 
6. Realizar copia de seguridad completa de todas las bases de datos de BizTalk. 
7. Restaurar bases de datos de BizTalk en las instancias SQL actualmente en el rol principal en el grupo de disponibilidad. 
8. Los inicios de sesión y el Agente SQL de script los trabajos en instancias de SQL correspondientes actualmente en el rol principal en el grupo de disponibilidad.  
9. Ejecute el `UpdateDatabase.vbs` y `UpdateRegistry.vbs` scripts en los equipos de BizTalk siguiendo estos pasos. Escriba el agente de escucha del grupo de disponibilidad como el nuevo nombre del servidor en el xml de información de actualización de entrada.  
    1. Detenga todos los servicios de BizTalk y los servicios SSO empresariales en BizTalk Server. Detenga el servicio Agente SQL en SQL Server. 
    2. En BizTalk Server, edite SampleUpdateInfo.xml en la siguiente carpeta: 
 
        equipo de 32 bits: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        equipo de 64 bits: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore`
 
            1. Replace "SourceServer" with the source server name (old SQL Server hosting old databases).  
            2. Replace "DestinationServer" with the name of the destination server, which should be the availability group listener name.  
            3. If you have the BAMAnalysis, BAM databases or RuleEngineDB, uncomment the appropriate sections. 

    3. Abra un símbolo del sistema y vaya a: 
 
        equipo de 32 bits: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore` 
 
        equipo de 64 bits: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        En el símbolo del sistema, ejecute:  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
 
        Ejecute UpdateDatabase.vbs en un único servidor en el grupo de BizTalk. 

    4. Copie el archivo SampleUpdateInfo.xml editado en la carpeta siguiente en cada equipo de BizTalk Server de este grupo de BizTalk: 
 
        equipo de 32 bits: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore` 
 
        equipo de 64 bits: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
    5. En cada equipo en el grupo de BizTalk Server, abra un símbolo del sistema y vaya a: 
 
        equipo de 32 bits: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        equipo de 64 bits: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        En el símbolo del sistema, ejecute:  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml` 
 
        Ejecute UpdateRegistry.vbs en todos los servidores del grupo de BizTalk. 
 
10. Ahora puede mover las bases de datos a sus respectivos grupos de disponibilidad. 
11. Replicar el perfil de SQL DBMail y la cuenta para las alertas de BAM en SQL instancias que hospeda la réplica de la base de datos de BAMAlerts. 
12. Incluya el cuerpo de los pasos de trabajo del Agente SQL dentro de un bloque IF para asegurarse de que ejecute sólo si el destino es la principal. 
13. Secuencia de comandos los inicios de sesión y trabajos del Agente SQL para replicarlas en la réplica correspondiente. La secuencia de comandos UpdateDatabase también actualiza el nombre del servidor en los trabajos de Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb y TrackedMessages_Copy_BizTalkMsgBoxDb. Secuencia de comandos por lo que los trabajos del Agente SQL solo después de ejecutar el script UpdateDatabase. 

## <a name="requirements"></a>Requisitos 
* BizTalk Server 2016 Enterprise
* SQL Server 2016 Enterprise o SQL Server 2016 Standard (consulte **limitaciones conocidas** en este tema)
* Windows Server 2012 R2 o Windows Server 2016 

### <a name="availability-group-listener-configured-with-non-default-port-1433"></a>Agente de escucha de grupo de disponibilidad configurado con no predeterminado (1433) de puerto 
Usar el alias SQL en equipos con BizTalk Server. 

### <a name="support-availability-group-multi-subnet-failovers"></a>Conmutaciones por error de múltiples subredes de grupo de disponibilidad de soporte técnico 
BizTalk Server utiliza OLE DB de Microsoft para las conexiones de base de datos, que no admite la **MultiSubnetFailover** opción de conexión. BizTalk Server no admite el `MultiSubnetFailover (=TRUE)` opción de conexión y esto puede provocar mayor tiempo de recuperación durante la conmutación por error de múltiples subredes. 

### <a name="read-only-routing"></a>Enrutamiento de solo lectura 
Enrutamiento de solo lectura se refiere a la capacidad de SQL Server para enrutar las conexiones entrantes para un agente de escucha del grupo de disponibilidad a una réplica secundaria que está configurada para permitir las cargas de trabajo de solo lectura. 

BizTalk no use enrutamiento de solo lectura para cualquiera de las conexiones a sus bases de datos. Esto significa que la opción "Secundaria legible" en las réplicas de disponibilidad del grupo de disponibilidad no tiene ningún efecto en las conexiones de base de datos de BizTalk. 

### <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de Host de BizTalk durante la conmutación por error SQL Server 
Si el grupo de disponibilidad de SQL Server produce una conmutación por error, las bases de datos de BizTalk Server en el grupo de disponibilidad están disponibles temporalmente. 

#### <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de host de tipo En curso durante la conmutación por error de SQL Server 
Si no están disponibles las bases de datos de BizTalk Server, una instancia en curso de un host de BizTalk Server se recicla hasta que se restaure la conexión a SQL Server. Una vez que se restaure la conexión a las bases de datos de SQL Server, el procesamiento de documentos se reanuda normalmente.
 
#### <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de host aisladas durante la conmutación por error de SQL Server 
Si las bases de datos de BizTalk Server no están disponibles, a continuación, se detiene una instancia aislada de un host de BizTalk Server y se genera un error similar al siguiente en el registro de aplicación de BizTalk Server: 

    All receive locations are being temporarily disabled because either the MessageBox or Configuration database is not available. When these databases become available, the receive locations will be automatically enabled.
 
Una vez que se restaure la conexión a las bases de datos de SQL Server, se escribe un mensaje informativo similar al siguiente en el registro de aplicación de BizTalk Server y, a continuación, se reanuda el procesamiento de documentos con normalidad: 

    All receive locations are being enabled because both the MessageBox and Configuration databases are back online.

#### <a name="log-shipping-for-disaster-recovery"></a>Trasvase de registros para la recuperación ante desastres 
BizTalk Server implementa capacidades en espera de base de datos mediante el uso de la base de datos de trasvase de registros. Se produce un error en BizTalk Server del trasvase de registros automatiza la copia de seguridad y restauración de bases de datos y sus archivos de registro de transacciones, lo que permite a un servidor en espera reanudar el procesamiento de base de datos en caso de que el servidor de base de datos de la producción. 

**Bases de datos secundarias en el grupo de disponibilidad no son copias de seguridad.** Continuar copias de seguridad de bases de datos de BizTalk y sus registros de transacciones con los trabajos de trasvase de registros de BizTalk Server. La manera en que se implementa el trasvase de registros de BizTalk garantiza que las copias de seguridad se realizan siempre en la réplica principal actual de cada base de datos. Los trabajos de trasvase de registros de BizTalk Server no respeta la configuración de preferencia de copia de seguridad en el grupo de disponibilidad. 

Si va a agregar otras bases de datos de BizTalk para el trabajo de copia de seguridad de bases de datos de BizTalk, asegúrese de utilizar el nombre de agente de escucha de grupo de disponibilidad como el servidor de base de datos para ellos al configurar la copia de seguridad.  
 
## <a name="references"></a>References 
 
* [Proporcionar alta disponibilidad de las bases de datos de BizTalk Server](../core/providing-high-availability-for-biztalk-server-databases.md)  
* [Soporte de software de servidor de Microsoft para las máquinas virtuales de Microsoft Azure](https://support.microsoft.com/kb/2721672)  
* [Creación de reflejo de base de datos de SQL Server, Servicio de instantáneas de volumen y AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
* [Información general de los grupos de disponibilidad AlwaysOn (SQL Server)](https://msdn.microsoft.com/library/ff877884.aspx)  
* [Compatibilidad con transacciones entre bases de datos para la creación de reflejo de base de datos o grupos de disponibilidad AlwaysOn (SQL Server)](https://msdn.microsoft.com/library/ms366279.aspx)  
* [No se puede llamar Reenlist cuando SQL Server recibe el resultado de la transacción de MSDTC en Windows Server 2012 R2](https://support.microsoft.com/kb/3090973)  
* [Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)  
* [Cómo mover las bases de datos de BizTalk Server](../core/how-to-move-the-biztalk-server-databases.md)  
* [Cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md)   
* [Tiempos de espera de conexión en el grupo de disponibilidad de múltiples subredes](https://blogs.msdn.microsoft.com/alwaysonpro/2014/06/03/connection-timeouts-in-multi-subnet-availability-group/)  
 
## <a name="known-limitations"></a>Limitaciones conocidas 

Estas limitaciones son para BizTalk Server, SQL Server grupo de disponibilidad AlwaysOn y las máquinas virtuales de Azure. Estas limitaciones pueden o no se pueden obtener solucionar en el futuro. 

* No se administran los inicios de sesión, trabajos del Agente SQL, el perfil de correo electrónico de base de datos de SQL y las cuentas dentro de grupos de disponibilidad. Esto requiere la modificación manual de trabajos para asegurarse de que se ejecutan contra la réplica principal. 
* SQL Server Analysis Services y SQL Server Integration Services no participan en los grupos de disponibilidad. Sin esta compatibilidad de SQL Server, no hay ninguna solución de alta disponibilidad para estos en Azure Virtual Machines. Capacidades BAM de BizTalk Server dependen de estos servicios. 
* Antes de SQL Server 2016 SP2, los grupos de disponibilidad no admiten MSDTC entre bases de datos en la misma instancia SQL. Por lo tanto, un mínimo 8 instancias SQL necesarios para configurar BizTalk. 

  A partir de SQL Server 2016 SP2 *y* BizTalk Server 2016 [CU5](https://support.microsoft.com/help/2555976/service-pack-and-cumulative-update-list-for-biztalk-server), las bases de datos de BizTalk pueden usar la misma instancia de SQL Server. 

* Para abordar MSDTC limitaciones con grupos de disponibilidad, las bases de datos de BizTalk pueden configurarse con un mínimo de dos servidores de cuatro instancias SQL. También puede usar [varias direcciones IP con el equilibrador de carga Azure](https://docs.microsoft.com/azure/load-balancer/load-balancer-multivip-overview). Si desea usar cuatro instancias SQL de forma predeterminada en el puerto 1433 en un solo servidor, tiene cuatro direcciones IP. Si están restringidos a una dirección IP, y desea hospedar varias instancias SQL en el mismo servidor, asegúrese de utilizar un puerto personalizado para cada instancia SQL. 

  A partir de SQL Server 2016 SP2 *y* BizTalk Server 2016 [CU5](https://support.microsoft.com/help/2555976/service-pack-and-cumulative-update-list-for-biztalk-server), las bases de datos de BizTalk Server pueden usar la misma instancia de SQL Server. 

* BizTalk Server no puede usar el enrutamiento de solo lectura. 
* BizTalk Server no establece la `MultiSubnetFailover` propiedad de conexión. 
* Trabajos de copia de seguridad de BizTalk mediante el trasvase de registros siempre tendrán como destino la réplica principal, independientemente de la preferencia de copia de seguridad definida en el grupo de disponibilidad. 
* SQL Server 2016 Standard admite solo una única base de datos en cada grupo de disponibilidad de AlwaysOn de SQL. Puesto que BizTalk utiliza muchas bases de datos, normalmente se recomienda SQL Server Enterprise edition.
* Si usa máquinas virtuales de Azure, se recomienda para usar una dedicado se ha corregido el puerto TCP/IP para MSDTC. Cuando se usa un puerto TCP/IP fijo, no limitar el intervalo de puertos RPC suele utilizado con los sistemas operativos anteriores; y lo ayuda a simplificar el firewall y reglas de equilibrador de carga. Para evitar conflictos con puertos inferiores conocidos, considere la posibilidad de utilizar un puerto fijo superior (como > 20000). [Configuración de la compatibilidad de puerto único DTC](https://msdn.microsoft.com/library/windows/desktop/dd573191(v=vs.85).aspx) describe la `ServerTcpPort` clave del registro. Además del puerto fijo para MSDTC, también se usa el puerto RPC 135 principal. 
