---
title: Alta disponibilidad mediante SQL Server grupos de disponibilidad AlwaysOn | Documentos de Microsoft
description: Agrupe la base de datos de BizTalk Server en varios nodos para obtener una solución de alta disponibilidad (HA) mediante SQL Server siempre en disponibles grupos (AG), incluidos los requisitos de sistema y limitaciones. Siempre AG requiere clústeres de conmutación por error de servidor de Windows (WSFC).
ms.custom: ''
ms.date: 04/10/2018
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
ms.openlocfilehash: 4bc7a1d1864b4e31bc20d170e2f2dd2602646188
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="high-availability-using-sql-server-always-on-availability-groups"></a>Alta disponibilidad mediante SQL Server grupos de disponibilidad AlwaysOn
Configurar alta disponibilidad mediante el uso de grupos de disponibilidad AlwaysOn de SQL Server.

> [!TIP] 
[Configurar BizTalk Server 2016 mediante la disponibilidad de grupos de laboratorio](https://skastberg.wordpress.com/2017/02/22/setting-up-my-biztalk-server-2016-using-availability-groups-lab/) proporciona una guía paso a paso escrita por un ingeniero de campo de Microsoft. Esta se basa en un entorno de laboratorio e incluye algunas observaciones. Mira esto.  

> [!IMPORTANT]
> * Grupos de disponibilidad AlwaysOn está disponible a partir de SQL Server 2016. Si está utilizando una versión anterior de SQL Server, este tema no se aplica a usted. 
> * BizTalk Server 2016 admite el modo de confirmación sincrónica; no se admite el modo de confirmación asincrónica. Recuperación ante desastres, se recomienda configurar el trabajo de copia de seguridad de BizTalk Server y usar el trasvase de registros. Vea [copia de seguridad y restaurar bases de datos de servidor de BizTalk](../core/backing-up-and-restoring-biztalk-server-databases.md) para obtener detalles específicos.
> 
>    [Modos de disponibilidad](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/availability-modes-always-on-availability-groups) se detallan las opciones de confirmación con grupos de disponibilidad AlwaysOn. 


## <a name="background-and-history"></a>Segundo plano y el historial

BizTalk Server se basa principalmente en SQL Server para la persistencia de datos. Otros componentes y hosts de BizTalk Server tienen funciones específicas al integrar aplicaciones empresariales diferentes, por ejemplo, recibir, procesar o enrutar mensajes. El equipo de base de datos captura este trabajo y lo almacena en el disco. 

BizTalk utiliza clústeres de conmutación por error de SQL Server y el trasvase de registros para proporcionar alta disponibilidad, copia de seguridad y restauración y recuperación ante desastres para sus bases de datos local. En IaaS de Azure (máquinas virtuales de Azure), las versiones anteriores de SQL Server no son compatibles con instancias de clúster de conmutación por error (no hay compatibilidad MSDTC). Como resultado, BizTalk no tenía una solución de alta disponibilidad al utilizar máquinas virtuales de Azure.

A partir de SQL Server 2016, grupos de disponibilidad AlwaysOn de SQL Server es compatible con MSDTC para local y usar máquinas virtuales de Azure. Como resultado, la característica de SQL Server 2016 AlwaysOn se admite para las bases de datos de BizTalk en local o en escenarios de IaaS de Azure. 

## <a name="sql-server-2016-alwayson-availability-groups"></a>Grupos de disponibilidad AlwaysOn de SQL Server 2016 
La implementación de grupos de disponibilidad AlwaysOn requiere un clúster de clústeres de conmutación por error de servidor de Windows (WSFC). Cada réplica de disponibilidad de un determinado grupo de disponibilidad debe residir en otro nodo del mismo clúster de WSFC. Por cada grupo de disponibilidad que cree, se creará un grupo de recursos de WSFC. El clúster de WSFC supervisa este grupo de recursos para evaluar el estado de la réplica principal.  

En la ilustración siguiente se muestra un grupo de disponibilidad que contiene solo una réplica principal y cuatro réplicas secundarias.  
 
 ![SQLAG_PrimaryReplica](../core/media/sqlag-primaryreplica.png)

Los clientes pueden conectarse a la réplica principal de un grupo de disponibilidad determinado mediante un agente de escucha del grupo de disponibilidad. Un agente de escucha del grupo de disponibilidad proporciona un conjunto de recursos que están conectados a un grupo de disponibilidad determinado para dirigir las conexiones de cliente a la réplica de disponibilidad adecuada. 

>[!IMPORTANT]
> SQL Server 2016 admite MSDTC con grupos de disponibilidad AlwaysOn (AG) en Windows Server 2016 y Windows Server 2012 R2. **Windows Server 2012 R2** requiere el [3090973](https://support.microsoft.com/kb/3090973) revisión de Windows esté instalado. 
> **Windows Server 2016** requiere que el [clave del registro de RemoteAccessEnabled](https://support.microsoft.com/kb/3182294) habilitarse.

SQL Server no es compatible con MSDTC con AlwaysOn AG para cualquier versión anterior a 2016.  

MSDTC entre bases de datos en la misma instancia de SQL Server no es compatible con grupos de disponibilidad AlwaysOn de SQL Server. Esto significa que no hay dos bases de datos de BizTalk en una transacción distribuida se pueden hospedar en la misma instancia SQL server. Para mantener la coherencia transaccional, deben hospedar bases de datos de BizTalk participan en transacciones distribuidas en varias instancias SQL server. Tenga en cuenta que no importa si las instancias de SQL se encuentran en el mismo equipo o en equipos diferentes.  


## <a name="providing-high-availability-for-biztalk-databases-using-alwayson-availability-groups"></a>Proporcionar alta disponibilidad de bases de datos de BizTalk mediante grupos de disponibilidad AlwaysOn 
En la configuración básica de BizTalk Server, un mínimo de 9 bases de datos se crean incluidas reglas y BAM bases de datos. Debido a MSDTC limitación con grupos de disponibilidad se ha mencionado anteriormente, una configuración como siguiente no garantiza la coherencia transaccional. 

![SQLAG_NoTrans](../core/media/sqlag-notrans.gif)
 
Se recomienda que las bases de datos de BizTalk Server se agrupan en las siguientes cuatro instancias de SQL Server:
 
| Instancia |Rol |Bases de datos de BizTalk en ese grupo  |
|--- | --- | ---|
|1 |Autenticación |SSODB|
|2 |Administración |BizTalkMgmtDb| 
|3 |Tiempo de ejecución |BizTalkMsgBoxDb<br/> BizTalkRulesEngineDb<br/> BAMPrimaryImport<br/>BAMStarSchema <br/>BAMAlertsApplication |
|4 |Seguimiento |BizTalkDTADb<br/>EsbItineraryDb<br/>EsbExceptionDb | 
 
En un escenario de cuadro de mensajes de escala horizontal (una configuración con más de un cuadro de mensajes), hay más de una base de datos de cuadro de mensajes, y cada base de datos de cuadro de mensajes debe estar en su propia instancia de SQL Server. 

BizTalk Server también depende de SQL Server Analysis Services y SQL Server Integration Services para el análisis de BAM y archivado. SQL Server no proporciona una solución de alta disponibilidad para los servicios de integración o de Analysis Services en IaaS de Azure. Por lo tanto, se recomienda usar otra instancia de SQL Server independiente para las bases de datos BAMArchive y BAMAnalysis Analysis Services. Para las instalaciones locales, instancia de clústeres de conmutación por error de SQL puede utilizarse para establecer una configuración de alta disponibilidad. 

Esta configuración se ilustra a continuación y se recomienda para las bases de datos de BizTalk en grupos de disponibilidad:  

![SQLAG_Recommended](../core/media/sqlag-recommended.png)
 
Junto con las bases de datos de SQL Server, configuración de BizTalk Server crea también los inicios de sesión de seguridad de SQL Server y trabajos del Agente SQL. Grupos de disponibilidad AlwaysOn solo proporcionan la capacidad para administrar bases de datos dentro de un grupo de disponibilidad. Los inicios de sesión y trabajos del Agente SQL de BizTalk que se crean y se actualizan/administran manualmente en todas las réplicas de disponibilidad.  

La siguiente lista de inicios de sesión de seguridad de SQL Server están asociados con BizTalk Server. Puede que tenga más inicios de sesión creados para las aplicaciones de BizTalk Server. Si es así, debe replicarlos en cada instancia de SQL Server que hospeda una réplica de bases de datos de BizTalk. 

1. Usuarios de aplicación de BizTalk (uno o más correspondiente a cada Host en proceso) 
2. Usuarios de hosts aislados de BizTalk (uno o más correspondiente a cada Host aislado) 
3. Administradores de servidor BizTalk Server 
4. Operadores B2B de BizTalk Server 
5. Operadores de servidor BizTalk Server 
6. Administradores de SSO 
7. Usuario de alertas BAM 
8. Usuario de servicio web de administración de BAM 
9. Cuenta de servicio de actualización de motor de reglas 

Si ha creado hosts adicionales o creará hosts adicionales más tarde, habrá nuevos inicios de sesión SQL creados como parte de este proceso. Debe asegurarse de que crear manualmente estos inicios de sesión SQL en las réplicas correspondientes.

Los siguientes trabajos del Agente SQL Server están asociados a BizTalk Server. Los trabajos instalados en cada servidor son diferentes según las características instaladas y configuradas. La mayoría de estos trabajos se crea durante la configuración de BizTalk Server. Algunos se crean al configurar el envío de registro. Estos trabajos deben replicarse en cada instancia de réplica de hospedaje de SQL Server de su base de datos de BizTalk correspondiente. Esto debe realizarse manualmente. 

- Trabajos de BizTalkMgmtDb: 
    - Copia de seguridad de BizTalk Server (BizTalkMgmtDb) 
    - CleanupBTFExpiredEntriesJob_BizTalkMgmtDb 
    - Supervisar el servidor BizTalk Server (BizTalkMgmtDb) 
- Trabajos de BizTalkMsgBoxDb: 
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
- Trabajo de BizTalkRulesEngineDb: 
    - Rules_Database_Cleanup_BizTalkRuleEngineDb 
- Trabajo de BAMAlertsApplication: 
    - 0 o más DelAlertHistJob 

A diferencia de instancias de clústeres de conmutación por error de SQL Server, en grupos de disponibilidad todas las réplicas están activas, ejecución y disponibles. Cuando los trabajos del Agente SQL se duplican en cada réplica para conmutación por error, se ejecutan en la réplica correspondiente, independientemente de si está actualmente en el rol principal o secundaria. Para asegurarse de que estos trabajos se ejecutan solo en la réplica principal actual, cada paso en cada trabajo debe incluirse dentro de un bloque IF, tal como se muestra: 

    IF (sys.fn_hadr_is_primary_replica(‘dbname’) = 1)  
    BEGIN  
    …  
    END
  
Reemplace `‘dbname’` con el nombre de base de datos correspondiente en la que el trabajo está configurado para ejecutarse. En el ejemplo siguiente se muestra este cambio para TrackedMessages_Copy_BizTalkMsgBoxDb en BizTalkMsgBoxDb: 
 
 ![SQLAG_AgentJob](../core/media/sqlag-agentjob.gif)

### <a name="configure-biztalk-server-when-availability-groups-are-already-set-up"></a>Configurar BizTalk Server cuando ya se configuran los grupos de disponibilidad

1. Compruebe los requisitos de sistema operativo: 
* En todos los **Windows Server 2012 R2** los equipos, instalar el [3090973 revisión MSDTC](https://support.microsoft.com/kb/3090973) (abre un artículo de KB)
* En todos los **Windows Server 2016** equipos, habilite la [clave del registro de RemoteAccessEnabled](https://support.microsoft.com/kb/3182294) (abre un artículo de KB)
2. Asegúrese de que tiene al menos cuatro instancias diferentes de SQL que hospedará las bases de datos de BizTalk distintos. Las réplicas secundarias también se deben configurar en distintas instancias SQL. Esto da como resultado un mínimo de 8 instancias SQL (1 principal y 1 réplica secundaria para cada uno de las 4 instancias) y un mínimo de 4 grupos de disponibilidad. Vea la ilustración anterior para esta configuración de grupo de disponibilidad. Asegúrese de que los grupos de disponibilidad se crean con el **por el soporte de DTC de base de datos** opción como no se pueden cambiar más adelante. 
3. Al configurar BizTalk Server y especificar el nombre del servidor SQL, utilice el nombre de agente de escucha del grupo de disponibilidad en lugar del nombre real del equipo. Esto crea las bases de datos de BizTalk, los inicios de sesión y trabajos del Agente SQL en la réplica principal actual. 
4. Detener el procesamiento de BizTalk (instancias de Host, servicio de SSO, IIS, servicio de actualización de motor de reglas, BAMAlerts Service etc.) y detener los trabajos del Agente SQL. 
5. Ahora agregue las bases de datos de BIzTalk a los respectivos grupos de disponibilidad. 
6. Incluir cuerpo de pasos de trabajo del Agente SQL en `IF` bloque (mencionado anteriormente) para asegurarse de que ejecute solo si el destino es la réplica principal. 
7. Script para los inicios de sesión y trabajos del Agente SQL para replicarlas en réplica correspondiente. 
8. Replicar SQL DBMail perfil y cuenta para las alertas de BAM en instancias correspondientes de SQL que hospeda la réplica secundaria. 
9. Si va a agregar una base de datos de cuadro de mensaje adicional o implementar una nueva actividad/vista de BAM posterior, a continuación, nueva trabajos SQL se crean para nuevas bases de datos de cuadro de mensaje o la base de datos de alertas de BAM en la réplica principal actual. Asegúrese de editar en la réplica principal y crearlos manualmente en las réplicas secundarias correspondientes. 

Esta configuración también se puede realizar con las instancias de SQL que hospeda la réplica principal. En este caso, después de la configuración de BizTalk, ejecute el `UpdateDatabase.vbs` y `UpdateRegistry.vbs` las secuencias de comandos en los equipos de BizTalk después de los pasos anteriores. Esto se explica con más detalle en la sección siguiente.  
 
### <a name="move-biztalk-server-databases-of-an-existing-biztalk-system-to-availability-groups"></a>Mover bases de datos de BizTalk Server de un sistema de BizTalk existente a grupos de disponibilidad

1. Compruebe los requisitos de sistema operativo: 
* En todos los **Windows Server 2012 R2** los equipos, instalar el [3090973 revisión MSDTC](https://support.microsoft.com/kb/3090973) (abre un artículo de KB)
* En todos los **Windows Server 2016** equipos, habilite la [clave del registro de RemoteAccessEnabled](https://support.microsoft.com/kb/3182294) (abre un artículo de KB)
2. Asegúrese de que tiene al menos cuatro instancias diferentes de SQL que hospedará las bases de datos de BizTalk distintos. Las réplicas secundarias también se deben configurar en distintas instancias SQL. Esto da como resultado un mínimo de 8 instancias SQL (1 principal y 1 réplica secundaria para cada uno de las 4 instancias) y un mínimo de 4 grupos de disponibilidad. Vea la ilustración anterior para esta configuración de grupo de disponibilidad. Asegúrese de que los grupos de disponibilidad se crean con **por el soporte de DTC de base de datos** opción como no se pueden cambiar más adelante.  
3. Detener el procesamiento de BizTalk y trabajos del Agente SQL. 
4. Realizar copia de seguridad completa de todas las bases de datos de BizTalk. 
5. Restaurar bases de datos de BizTalk en las instancias SQL actualmente en el rol principal del grupo de disponibilidad. 
6. Secuencia de comandos de los inicios de sesión y el Agente SQL trabajos en instancias de SQL correspondientes actualmente en el rol principal del grupo de disponibilidad.  
7. Ejecute el `UpdateDatabase.vbs` y `UpdateRegistry.vbs` las secuencias de comandos en los equipos de BizTalk siguiendo estos pasos. Escriba el agente de escucha del grupo de disponibilidad como el nuevo nombre del servidor en el xml de información de actualización de la entrada.  
    1. Detenga todos los servicios de SSO empresarial y servicios de BizTalk en BizTalk Server. Detener servicio Agente SQL en SQL Server. 
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
 
        Ejecutar UpdateDatabase.vbs en un solo servidor en el grupo de BizTalk. 

    4. Copie el archivo SampleUpdateInfo.xml editado en la carpeta siguiente en cada equipo de servidor BizTalk Server de este grupo de BizTalk: 
 
        equipo de 32 bits: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore` 
 
        equipo de 64 bits: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
    5. En cada equipo en el grupo de BizTalk Server, abra un símbolo del sistema y vaya a: 
 
        equipo de 32 bits: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        equipo de 64 bits: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        En el símbolo del sistema, ejecute:  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml` 
 
        Ejecute UpdateRegistry.vbs en todos los servidores del grupo de BizTalk. 
 
8. Ahora puede mover las bases de datos a sus respectivos grupos de disponibilidad. 
9. Replicar el perfil de DBMail de SQL y la cuenta para las alertas de BAM en la instrucción SQL instancias hospeda la réplica de la base de datos de BAMAlerts. 
10. Ponga el cuerpo de pasos de trabajo del Agente SQL dentro de un bloque IF para asegurarse de que ejecute solo si el destino es el principal. 
11. Script para los inicios de sesión y trabajos del Agente SQL para replicarlas en la réplica correspondiente. La secuencia de comandos UpdateDatabase también actualiza el nombre del servidor en los trabajos de Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb y TrackedMessages_Copy_BizTalkMsgBoxDb. Secuencia de comandos por lo que los trabajos del Agente SQL sólo después de ejecutar el script UpdateDatabase. 

## <a name="requirements"></a>Requisitos 
* BizTalk Server 2016 Enterprise
* Corporativo de SQL Server 2016
* Windows Server 2012 R2
* Windows Server 2016 

### <a name="availability-group-listener-configured-with-non-default-port-1433"></a>Agente de escucha de grupo de disponibilidad configurado tiene un valor no predeterminado (1433) de puerto 
Usar SQL alias en máquinas de BizTalk Server. 

### <a name="supporting-availability-group-multi-subnet-failovers"></a>Compatibilidad con clústeres de conmutación por error de varias subredes de grupo de disponibilidad 
BizTalk Server utiliza OLE DB de Microsoft para las conexiones de base de datos, que no admite la **MultiSubnetFailover** opción de conexión. BizTalk Server no admite el `MultiSubnetFailover (=TRUE)` opción de conexión y esto pueden provocar el mayor tiempo de recuperación durante la conmutación por error de múltiples subredes. 

### <a name="read-only-routing"></a>Enrutamiento de solo lectura 
Enrutamiento de solo lectura se refiere a la capacidad de SQL Server para enrutar las conexiones entrantes de un agente de escucha del grupo de disponibilidad a una réplica secundaria que está configurada para permitir las cargas de trabajo de solo lectura. 

BizTalk no usa enrutamiento de solo lectura para cualquiera de las conexiones a sus bases de datos. Esto significa que la opción "Secundaria legible" en las réplicas de disponibilidad del grupo de disponibilidad no tiene ningún efecto en las conexiones de base de datos de BizTalk. 

### <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de host de BizTalk Server durante la conmutación por error de SQL Server 
Si el grupo de disponibilidad de SQL Server produce una conmutación por error, las bases de datos de BizTalk Server en el grupo de disponibilidad están disponibles temporalmente. 

#### <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de host de tipo En curso durante la conmutación por error de SQL Server 
Si no están disponibles las bases de datos de BizTalk Server, una instancia en curso de un host de BizTalk Server se recicla hasta que se restaure la conexión a SQL Server. Una vez que se restaure la conexión a las bases de datos de SQL Server, el procesamiento de documentos se reanuda normalmente.
 
#### <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>Comportamiento de las instancias de host aisladas durante la conmutación por error de SQL Server 
Si las bases de datos de BizTalk Server no están disponibles, a continuación, detiene la instancia aislada de un host de BizTalk Server y se genera un error similar al siguiente en el registro de aplicación de BizTalk Server: 

    All receive locations are being temporarily disabled because either the MessageBox or Configuration database is not available. When these databases become available, the receive locations will be automatically enabled.
 
Una vez que se restaure la conexión a las bases de datos de SQL Server, se escribe un mensaje informativo similar al siguiente en el registro de aplicación de BizTalk Server y, a continuación, reanuda el procesamiento de documentos con normalidad: 

    All receive locations are being enabled because both the MessageBox and Configuration databases are back online.

#### <a name="biztalk-server-log-shipping-for-disaster-recovery"></a>El servidor BizTalk Server trasvase de registros para recuperación ante desastres 
BizTalk Server incorpora capacidades en espera de base de datos mediante el uso de la base de datos de trasvase de registros. Se produce un error en BizTalk Server trasvase de registros automatiza la copia de seguridad y restauración de bases de datos y sus archivos de registro de transacciones, lo que permite un servidor en espera reanudar el procesamiento de base de datos en caso de que el servidor de base de datos de producción. 

**Bases de datos secundarias en el grupo de disponibilidad no son copias de seguridad.** Continuar con copias de seguridad de bases de datos de BizTalk y sus registros de transacciones con los trabajos de trasvase de registros de BizTalk Server. La manera en que se implementa el trasvase de registros de BizTalk garantiza que siempre se realizan copias de seguridad en la réplica principal actual de cada base de datos. El valor de preferencia de copia de seguridad en el grupo de disponibilidad no se respeta los trabajos de trasvase de registros de BizTalk Server. 

Si va a agregar otras bases de datos de BizTalk para el trabajo de copia de seguridad de bases de datos de BizTalk, asegúrese de utilizar el nombre de agente de escucha de grupo de disponibilidad como el servidor de base de datos para ellos al configurar la copia de seguridad.  
 
## <a name="references"></a>Referencias 
 
* [Proporcionar una alta disponibilidad para bases de datos de servidor BizTalk Server](../core/providing-high-availability-for-biztalk-server-databases.md)  
* [Soporte de software de servidor de Microsoft para máquinas virtuales de Microsoft Azure](https://support.microsoft.com/kb/2721672)  
* [Creación de reflejo de base de datos de SQL Server, Servicio de instantáneas de volumen y AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
* [Información general de los grupos de disponibilidad AlwaysOn (SQL Server)](https://msdn.microsoft.com/library/ff877884.aspx)  
* [Compatibilidad para las transacciones entre bases de datos para la creación de reflejo de base de datos o grupos de disponibilidad AlwaysOn (SQL Server)](https://msdn.microsoft.com/library/ms366279.aspx)  
* [No se puede llamar Reenlist cuando SQL Server recibe el resultado de la transacción de MSDTC en Windows Server 2012 R2](https://support.microsoft.com/kb/3090973)  
* [Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)  
* [Cómo mover las bases de datos de servidor BizTalk Server](../core/how-to-move-the-biztalk-server-databases.md)  
* [Cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md)   
* [Tiempos de espera de conexión en el grupo de disponibilidad de varias subredes](https://blogs.msdn.microsoft.com/alwaysonpro/2014/06/03/connection-timeouts-in-multi-subnet-availability-group/)  
 
## <a name="known-limitations"></a>Limitaciones conocidas 

Estas limitaciones son para BizTalk Server, SQL Server AlwaysOn disponibilidad el grupo y máquinas virtuales de Azure. Estas limitaciones pueden o no se pueden obtener solucionadas en el futuro. 

* No se administran los inicios de sesión, trabajos del Agente SQL, el perfil de correo electrónico de base de datos de SQL y las cuentas dentro de grupos de disponibilidad. Esto requiere una modificación manual de trabajos para asegurarse de que se ejecutan en la réplica principal. 
* SQL Server Analysis Services y SQL Server Integration Services no participar en grupos de disponibilidad. Sin esta compatibilidad de SQL Server, no hay ninguna solución de alta disponibilidad para estas máquinas virtuales de Azure. Capacidades BAM de BizTalk Server dependen de estos servicios. 
* Grupos de disponibilidad no es compatible con MSDTC entre bases de datos en la misma instancia SQL. Por lo tanto, un mínimo 8 instancias SQL necesarios para configurar BizTalk. 
* Para solucionar MSDTC limitaciones con grupos de disponibilidad, las bases de datos de BizTalk pueden configurarse con un mínimo de dos servidores que hospedan cuatro instancias SQL. También puede usar [varias direcciones IP con el equilibrador de carga de Azure](https://docs.microsoft.com/azure/load-balancer/load-balancer-multivip-overview). Por ello, si desea usar cuatro instancias SQL de forma predeterminada en el puerto 1433 en un solo servidor, debe cuatro direcciones IP. Si están restringidos a una dirección IP, y desea hospedar varias instancias SQL en el mismo servidor, asegúrese de utilizar un puerto personalizado para cada instancia de SQL. 
* BizTalk Server no puede usar enrutamiento de solo lectura. 
* BizTalk Server no establece la `MultiSubnetFailover` propiedad de conexión. 
* Trabajos de copia de seguridad de BizTalk mediante el trasvase de registros siempre tendrán como destino la réplica principal, independientemente de la preferencia de copia de seguridad definida en el grupo de disponibilidad. 
 
