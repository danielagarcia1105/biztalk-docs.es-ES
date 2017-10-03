---
title: "Solución de problemas de administración de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dfb56b0-352f-4012-b030-087bbcfe09d4
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d89f81bbaf15dfb0c87de91659888d70a2345a6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-administration"></a>Solución de problemas de administración de BizTalk Server
En esta sección se proporciona una ubicación centralizada de información sobre problemas comunes que se pueden producir al usar la consola de administración de BizTalk Server.  
  
 Además de los siguientes problemas conocidos, [problemas comunes y soluciones con la consola de administración](http://social.technet.microsoft.com/wiki/contents/articles/common-issues-and-resolutions-with-the-biztalk-server-administration-console.aspx) proporciona información adicional.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="delay-in-entsso-service-prevents-biztalk-server-service-from-starting"></a>El retardo en el servicio ENTSSO impide que se inicie el servicio BizTalk Server  
  
##### <a name="problem"></a>Problema  
 Reiniciar el equipo con DTC no configurado para el arranque automático puede impedir que se inicie el servicio BizTalk Server.  
  
##### <a name="cause"></a>Causa  
 Esto se debe a que el servicio ENTSSO puede necesitar más tiempo para iniciarse que el que permite la duración del tiempo de espera del servicio BizTalk Server.  
  
##### <a name="solution"></a>Solución  
 Para solucionar este problema, establezca DTC en automático.  
  
#### <a name="sql-resources-may-become-locked"></a>Es posible que se bloqueen los recursos de SQL  
  
##### <a name="problem"></a>Problema  
 Puede producirse el error siguiente:  
  
 **La transacción (Id. de proceso 95) se ha interbloqueado en recursos de bloqueo con otro proceso y se ha elegido como víctima del interbloqueo. Vuelva a ejecutar la transacción.**  
  
##### <a name="cause"></a>Causa  
 Se trata de una situación muy poco frecuente en la cual las operaciones administrativas que realiza un usuario hacen que otro usuario se bloquee fuera de la administración de la base de datos.  
  
##### <a name="solution"></a>Solución  
 El problema debe corregirse por sí mismo en poco tiempo. Intente de nuevo la operación al cabo de unos minutos.  
  
#### <a name="sql-database-may-become-locked"></a>Es posible que se haya bloqueado la base de datos SQL  
  
##### <a name="problem"></a>Problema  
 Los usuarios pueden quedar bloqueados fuera de la base de datos SQL. Pueden devolverse numerosos mensajes de error diferentes.  
  
##### <a name="cause"></a>Causa  
 En algunos casos, un usuario que escribe en la base de datos bloqueará eficazmente a otro usuario fuera de la base de datos.  
  
##### <a name="solution"></a>Solución  
 El problema debe corregirse por sí mismo en poco tiempo. Intente de nuevo la operación al cabo de unos minutos.  
  
#### <a name="termination-of-multiple-service-instances-in-a-multiple-messagebox-environment-fails-with-an-error"></a>Se produce un error en la terminación de varias instancias de servicio en un entorno de varios cuadros de mensaje  
  
##### <a name="problem"></a>Problema  
 Se produce un error en los intentos de terminar varias instancias de servicio desde la consola de administración de BizTalk Server y se muestra un error similar al siguiente:  
  
 SQL Server bloqueó el acceso al procedimiento 'sys.xp_sqlagent_enum_jobs' del componente 'Agent XPs' debido a que este componente se ha desactivado como parte de la configuración de seguridad para este servidor.  
  
> [!NOTE]
>  Este problema se produce en un entorno de varios cuadros de mensaje.  
  
##### <a name="cause"></a>Causa  
 Este problema puede producirse en un entorno de cuadro de mensajes múltiples, si el trabajo del Agente SQL ' Operations_OperateOnInstances_OnMaster_\<*dbName*>' no se está ejecutando en las bases de datos de cuadro de mensaje secundaria. Para propagar información desde las bases de datos de cuadro de mensaje secundarias a la base de datos de cuadro de mensajes primaria, este trabajo debe estar en ejecución. Este trabajo no se podrá ejecutar si no está habilitado o si se produce un error de inicio de sesión.  
  
##### <a name="solution"></a>Solución  
 Si está utilizando la consola de administración de BizTalk para realizar operaciones en varias instancias del servicio al mismo tiempo y el entorno de BizTalk Server está configurado con varias bases de datos de cuadro de mensajes, compruebe que el trabajo del Agente SQL Server con el nombre ' Operations_ OperateOnInstances_OnMaster_\<*dbName*>' está habilitada en todas las bases de datos de cuadro de mensaje secundarias (no principales). Además, el servicio Agente SQL Server en el equipo SQL Server que hospeda las bases de datos de cuadro de mensaje secundarias debe ejecutarse como cuenta incluida en el rol de base de datos BTS_SQLAGENT_USER de la base de datos de cuadro de mensaje secundaria.  
  
> [!NOTE]
>  \<*dbname*> es un marcador de posición para el nombre real de la base de datos de cuadro de mensajes de BizTalk.  
  
 Siga estos pasos para agregar la cuenta del servicio Agente SQL Server al rol de base de datos BTS_SQLAGENT_USER de la base de datos de cuadro de mensaje secundaria.  
  
 **En SQL Server 2008**  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  Cuando se le solicite elegir la **tipo de servidor** de **motor de base de datos** y escriba o seleccione el **nombre del servidor** que hospeda la base de datos de cuadro de mensaje secundaria.  
  
3.  Haga clic para expandir **bases de datos**, haga clic para expandir la base de datos de cuadro de mensaje secundaria, haga clic para expandir **seguridad**, haga clic para expandir **Roles**, haga clic para expandir  **Roles de base de datos**y, a continuación, haga doble clic en el rol de base de datos BTS_SQLAGENT_USER.  
  
4.  Haga clic en el botón **Agregar** .  
  
5.  Haga clic en **examinar**, seleccione un grupo de la cuenta de servicio del Agente SQL Server es un miembro de y, a continuación, haga clic en **Aceptar**.  
  
> [!NOTE]
>  Si la cuenta de servicio del Agente SQL Server no es miembro del grupo especificado, deberá agregarla al grupo.  
  
#### <a name="changes-applied-in-one-instance-of-the-biztalk-administration-console-are-not-automatically-updated-in-other-instances-of-the-biztalk-administration-console"></a>Los cambios aplicados en una instancia de la consola de administración de BizTalk no se actualizan automáticamente en otras instancias de la consola de administración de BizTalk  
  
##### <a name="problem"></a>Problema  
 Si hay múltiples instancias de la consola de administración de BizTalk conectadas simultáneamente al mismo grupo de BizTalk Server, los cambios realizados en una instancia de la consola de administración de BizTalk no se ven reflejados automáticamente en la otra (u otras) instancias de la consola de administración de BizTalk. Esto puede causar errores de infracción de simultaneidad al intentar modificar un artefacto que se muestra en una instancia de la consola de administración de BizTalk si el estado del artefacto no coincide con su estado real tal como se encuentra almacenado en la base de datos de administración de BizTalk.  
  
##### <a name="cause"></a>Causa  
 Cada instancia de la consola de administración de BizTalk mantiene su propia caché de la configuración del grupo de BizTalk y sólo refleja los cambios de la caché. La caché sólo se actualiza cuando lo hace la consola de administración de BizTalk.  
  
##### <a name="resolution"></a>Solución  
 Si recibe errores de infracción de simultaneidad en la consola de administración de BizTalk, actualice la caché de la instancia de la consola de administración de BizTalk, haga clic en el **actualizar** botón en la consola de administración de BizTalk barra de herramientas o presionando el **F5** clave.  
  
#### <a name="failed-to-execute-action-stop-error-occurs-when-you-attempt-to-stop-an-orchestration-with-the-biztalk-administration-console"></a>Se produce el error No se pudo ejecutar la acción 'Stop' cuando se intenta detener una orquestación con la consola de administración de BizTalk  
  
##### <a name="problem"></a>Problema  
 Cuando se intenta detener una orquestación en la consola de administración de BizTalk, aparece un mensaje de error similar al siguiente:  
  
```  
Failed to execute action 'Stop'.  
------------------------------  
ADDITIONAL INFORMATION:  
A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.) (Microsoft SQL Server, Error: 10054)  
```  
  
 Este problema se puede producir si se cumplen las condiciones siguientes:  
  
-   La consola de administración de BizTalk está abierta.  
  
-   La base de datos de administración de BizTalk está instalada en una instancia agrupada de SQL Server.  
  
-   La instancia agrupada de SQL Server se ha conmutado por error.  
  
-   Después de la conmutación por error, se ha intentado detener una instancia de una orquestación que se está ejecutando, mediante la consola de administración de BizTalk.  
  
##### <a name="cause"></a>Causa  
 La consola de administración de BizTalk mantiene una conexión con la base de datos de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Cuando se ha interrumpido la conexión con la base de datos de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] durante la conmutación por error, algunas tareas de administración pueden producir errores que indican que no se ha podido conectar o que no se ha podido llevar a cabo la ejecución hasta que se cierre y se vuelva a abrir la consola de administración de BizTalk.  
  
##### <a name="resolution"></a>Solución  
 Cierre y vuelva a abrir la consola de administración de BizTalk. Cuando se vuelve a abrir la consola de administración de BizTalk, ésta crea una nueva conexión con la base de datos de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] especificada.  
  
#### <a name="windows-group-names-that-were-previously-deleted-do-not-have-access-to-the-biztalk-server-databases"></a>Los nombres de grupo de Windows que se eliminaron previamente no tienen acceso a las bases de datos de BizTalk Server  
  
##### <a name="problem"></a>Problema  
 Si al reinstalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa un nombre de grupo de Windows que se eliminó previamente, el grupo de Windows no tendrá acceso a las bases de datos de BizTalk Server.  
  
##### <a name="cause"></a>Causa  
 Al eliminar un grupo de Windows y crear a continuación otro con el mismo nombre, se produce un nuevo identificador de seguridad (SID) para el grupo de Windows. Sin embargo, el antiguo SID sigue almacenado en la caché de SQL Server; por lo tanto, el nuevo grupo de Windows no puede iniciar sesión en SQL Server.  
  
##### <a name="resolution"></a>Solución  
 Al eliminar el grupo de Windows, también habrá que eliminar el inicio de sesión de SQL Server del grupo de Windows.  
  
#### <a name="biztalk-administrator-cannot-start-the-biztalk-server-administration-console"></a>El administrador de BizTalk no puede iniciar la consola de administración de BizTalk Server  
  
##### <a name="problem"></a>Problema  
 Es posible que un administrador de BizTalk (miembro del grupo de Windows Administradores de BizTalk) no pueda abrir la consola de administración de BizTalk Server si ese usuario no es un miembro del grupo de administradores de Windows en el equipo local.  
  
##### <a name="cause"></a>Causa  
 Este problema se puede producir si ha vuelto a instalar o a configurar BizTalk Server. Esto ocurre porque SQL Server usaba identificadores de seguridad almacenados en caché.  
  
##### <a name="resolution"></a>Solución  
 Agregue temporalmente el administrador de BizTalk al grupo de administradores de Windows local en el equipo local. Después de haber abierto satisfactoriamente la consola de administración de BizTalk Server, elimine el administrador de BizTalk del grupo de administradores de Windows local del equipo local.  
  
#### <a name="cannot-start-a-host-instance-on-a-remote-computer"></a>No se puede iniciar una instancia de host en un equipo remoto  
  
##### <a name="problem"></a>Problema  
 Cuando se crea una instancia de BizTalk Host en un equipo remoto, puede ver el siguiente error al iniciar la instancia de BizTalk Host: "No se pudo iniciar debido a un error de inicio de sesión."  
  
##### <a name="cause"></a>Causa  
 Este error puede producirse si se han escrito credenciales no válidas para la cuenta de servicio en la que está ejecutándose la instancia de host de BizTalk, o bien porque la cuenta de servicio no tiene derechos de inicio de sesión como servicio.  
  
##### <a name="resolution"></a>Solución  
 Asigne derecho de inicio de sesión como servicio a la cuenta de servicio que está en el equipo remoto antes de iniciar la instancia de host de BizTalk. Esto se hace automáticamente en un equipo local, pero debe hacerse manualmente en un equipo remoto.  
  
#### <a name="creating-or-configuring-a-host-instance-on-an-x64-computer-with-the-32-bit-only-option-selected-fails"></a>Crear o configurar una instancia de host en un equipo con X64 en el que se producen errores con la opción Sólo de 32 bits seleccionada  
  
##### <a name="problem"></a>Problema  
 En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la creación de una instancia de host de BizTalk en un equipo con X64 con la opción Solo de 32 bits seleccionada (opción predeterminada) puede producir errores.  
  
 En el administrador de configuración de BizTalk Server, al configurar Tiempo de ejecución de BizTalk Server en un equipo con X64, es posible que el servicio no pueda iniciarse si se crea una instancia de host aislado o de tipo En curso con la opción Sólo de 32 bits seleccionada.  
  
##### <a name="cause"></a>Causa  
 Desconocido  
  
##### <a name="resolution"></a>Solución  
 Éste problema tiene un carácter intermitente. Intente crear o configurar nuevamente el host o, como alternativa, anule la selección de la opción Sólo de 32 bits.  
  
#### <a name="host-instance-deletion-does-not-clear-registry-information"></a>La eliminación de la instancia de host no borra la información del Registro  
  
##### <a name="problem"></a>Problema  
 Si no es un administrador del equipo local, al eliminar un host de tipo En curso o aislado, aparece un mensaje de error de acceso denegado. Puede eliminar forzosamente el host. No obstante, eliminar el host de este modo no borra toda la información relacionada que hay en el Registro.  
  
##### <a name="cause"></a>Causa  
 La eliminación de la información relativa a una instancia de host que hay en el Registro requiere privilegios de administrador.  
  
##### <a name="resolution"></a>Solución  
 Inicie sesión con una cuenta de administrador local antes de eliminar el host, de modo que también se elimine la información del Registro relacionada.  
  
#### <a name="cannot-delete-a-messagebox-database"></a>No se puede eliminar una base de datos de cuadro de mensajes  
  
##### <a name="problem"></a>Problema  
 Es posible que no pueda eliminar una base de datos de cuadro de mensajes. Si no se produce la eliminación, alguno de los siguientes problemas pueden ser los causantes:  
  
-   El intervalo de actualización de la caché no ha caducado.  
  
-   La base de datos de cuadro de mensajes contiene instancias incompletas.  
  
 Si el intervalo de actualización de caché no ha expirado todavía, aparece el siguiente mensaje de error cuando se produce un error en la eliminación: "cuadro de mensajes no se puede eliminar porque se podría ser trabajo restante en el cuadro de mensajes. Asegúrese de que no hay instancias incompletas no hay más en el cuadro de mensajes y vuelva a intentarlo."  
  
##### <a name="cause"></a>Causa  
 El intervalo de actualización de la caché debe caducar entre el momento en que se deshabilita la publicación del nuevo mensaje en la base de datos de cuadro de mensajes y el momento en que se elimina la base de datos. El valor predeterminado del intervalo de actualización de la caché es de 60 segundos.  
  
##### <a name="resolution"></a>Solución  
 Para eliminar una base de datos de cuadro de mensajes será necesario en primer lugar deshabilitar la publicación de nuevos mensajes en esa base de datos de cuadro de mensajes y, a continuación, esperar hasta que caduque el intervalo de actualización de la caché antes de eliminar la base de datos de cuadro de mensajes.  
  
 Si la base de datos de cuadro de mensajes contiene instancias de servicio incompletas, aparece el siguiente mensaje de error: "el cuadro de mensajes no se puede eliminar porque todavía puede contener instancias incompletas. Asegúrese de que no quedan instancias incompletas en el cuadro de mensajes y vuelva a intentarlo."  
  
 Puede ver instancias de servicio incompletas en la base de datos de cuadro de mensaje mediante la página Concentrador de grupo de la consola de administración de BizTalk Server. Para obtener información acerca de cómo ver el estado de las instancias de servicio en la página concentrador de grupo, consulte [cómo buscar instancias de servicio controladas](../core/how-to-search-for-tracked-service-instances.md).  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas](../core/troubleshooting.md)