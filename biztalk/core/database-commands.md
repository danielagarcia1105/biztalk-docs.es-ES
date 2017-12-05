---
title: Comandos de la base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c54131-0793-45a9-822a-554cd4fc05a2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2232602ec5a91768f4b9dbde5f6c63a79de0c332
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="database-commands"></a>Comandos de base de datos
Los comandos de base de datos de la utilidad de administración de BAM le permiten trabajar con las bases de datos de BAM:  
  
-   las bases de datos de programa de instalación: crea las bases de datos específicas de BAM.  
  
-   migrar de sql: migra las bases de datos BAM desde:  
  
    -   Microsoft SQL Server 2000 a Microsoft SQL Server 2008  
  
    -   Microsoft SQL Server 2005 a Microsoft SQL Server 2008  
  
-   Enable-reference: permite una referencia a una base de datos de importación principal de BAM distribuida.  
  
-   Get-references: Obtiene una lista de referencias a bases de datos de importación principal de BAM distribuidas.  
  
-   Disable-reference: deshabilita una referencia a una base de datos de importación principal de BAM.  
  
> [!NOTE]
>  Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro. Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración. El conmutador puede utilizarse junto con cualquier comando normal de BM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="setup-databases-command"></a>setup-databases (comando)  
 **Uso**  
  
 **el programa de instalación de bm.exe-databases-ConfigFile:\<archivo de configuración\>[- NSUser:\<nombre de usuario del servicio de notificaciones\> ] [- NSUserPassword:\<decontraseñadeusuariodelserviciodenotificaciones\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|ConfigFile:\<archivo de configuración\>|El archivo de configuración de BAM desde el que se va a crear la base de datos.|  
|NSUser:\<nombre de usuario del servicio de notificaciones\>|Opcional: El identificador de usuario de un usuario de servicios de notificaciones con permisos para crear bases de datos.|  
|NSUserPassword|Opcional: La contraseña para el usuario de servicios de notificaciones especificadas.|  
  
 Crea las bases de datos descritas en el archivo de configuración (importación principal de BAM, esquema de estrella de BAM, análisis de BAM y alertas) si todavía no existen. Una vez que se cree las bases de datos, el comando crea las tablas de metadatos de BAM asociadas y los procedimientos almacenados.  
  
 Los parámetros NSUser y NSUserPassword son necesarios si está configurando alertas BAM. Si no se especifica el NSUserPassword en la línea de comandos, bm.exe le pide la contraseña.  
  
> [!NOTE]
>  Después de completar el comando, puede tener una excepción del AlertModule en el registro de seguimiento en cuenta:  
>   
>  "La cuenta especificada es el propietario de la base de datos. El propietario de la base de datos tiene siempre acceso a la vista y no se puede agregar ni quitar de la vista."  
>   
>  Asimismo, es posible que vea una advertencia en el evento de NotificationServices#19001.  
>   
>  Si no se informó de ningún error durante la ejecución del comando, puede pasar estos avisos por alto con seguridad.  
  
> [!IMPORTANT]
>  Si ejecuta un comando setup-database mediante un archivo de configuración de BAM que no contiene una sección de alertas y si ya ha configurado alertas BAM, bm.exe sobrescribirá la configuración de tal manera que ya no funcionarán las alertas.  
  
 Para configurar las bases de datos de BAM, deberá tener permisos de administrador en el servidor Microsoft SQL Server en que residen las bases de datos BAMPrimaryImport, BAMStarSchema y BAMArchive. Para configurar las bases de datos de servicios de notificación de SQL, deberá tener permisos de administrador y ser miembro del grupo local de administradores, así como ser miembro de otros grupos adicionales de administradores que se hayan configurado, como el grupo de administradores de BTS.  
  
 **Ejemplos**  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a>migrate-sql (comando)  
 **Uso**  
  
 **bm.exe migrar t-SQL-de: sql2000-a: sql2008 [- NSUser:\<nombre de usuario del servicio de notificaciones\> ] [- NSUserPassword:\<contraseña de usuario del servicio de notificaciones\> ] [-Server:\<server\> ] [-Base de datos:\<base de datos\> ]**  
  
 \- O bien  
  
 **bm.exe migrar t-SQL-de: sql2005-a: sql2008 [- NSUser:\<nombre de usuario del servicio de notificaciones\> ] [- NSUserPassword:\<contraseña de usuario del servicio de notificaciones\> ] [-Server:\<server\> ] [-Base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Desde: sql2000|Especifica que está convirtiendo desde una base de datos de Microsoft SQL Server 2000.|  
|To:sql2008|Especifica que va a convertir en una base de datos de Microsoft SQL Server 2008.|  
|Desde: sql2005|Especifica que está convirtiendo desde una base de datos de Microsoft SQL Server 2005.|  
|To:sql2008|Especifica que va a convertir en una base de datos de Microsoft SQL Server 2008.|  
|NSUser:\<nombre de usuario del servicio de notificaciones\>|Opcional: El identificador de usuario de un usuario de servicios de notificación con permisos para crear bases de datos.|  
|NSUserPassword|Opcional: La contraseña para el usuario de servicios de notificación especificado.|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que residirá la base de datos convertida. El servidor debe estar en el mismo dominio que el equipo que hospeda la base de datos de Microsoft SQL Server 2008. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos convertida. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Migra la infraestructura BAM desde Microsoft SQL Server 2000 o Microsoft SQL Server 2005 a Microsoft SQL Server 2008. Utilice este comando después de actualizar el servidor de base de datos y el servidor de análisis de Microsoft SQL Server 2000 o Microsoft SQL Server 2005 a Microsoft SQL Server 2008.  
  
 Los parámetros NSUser y NSUserPassword son necesarios si ha configurado alertas BAM. Si no se especifica el NSUserPassword en la línea de comandos, bm.exe le pide la contraseña.  
  
 Para migrar las bases de datos de servicios de notificación de SQL Server, deberá tener permisos de administrador y ser miembro del grupo local de administradores, así como ser miembro de otros grupos adicionales de administradores que se hayan configurado, como el grupo de administradores de BTS.  
  
> [!NOTE]
>  Si recibe el mensaje de error "ERROR: no se puede iniciar el servicio NS$ BAMAlerts en equipo '\<nombre_equipo\>'. El servicio no respondió a tiempo a la solicitud de inicio o de control.", intente reiniciar el servicio de forma manual. Si SQL Server está muy ocupado durante una migración, es posible que no se reinicie el servicio.  
  
> [!NOTE]
>  Para ejecutar el comando migrate-sql en el equipo en el que se encuentran instalados los servicios de notificación, tendrá que ser miembro del grupo local de administradores de ese equipo.  
  
 **Ejemplos**  
  
```  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
```  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
## <a name="enable-reference-command"></a>enable-reference (comando)  
 **Uso**  
  
 **bm.exe enable-reference - TargetServer:\<TargetServer\> - TargetDatabase:\<base de datos de destino\>[-Server:\<server\> ] [-base de datos:\<delabasededatos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|TargetServer:\<servidor de destino\>|Nombre del servidor para el que se habilita la referencia. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.|  
|TargetDatabase:\<base de datos de destino\>|Nombre de la base de datos para la que se habilita la referencia.|  
|Servidor:\<server\>|Opcional: El nombre del servidor que tendrá una referencia habilitada para el servidor de destino y la base de datos. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos que tiene una referencia habilitada para el servidor de destino y la base de datos. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Habilita una referencia a otra base de datos distribuida de importación principal de BAM. Permite suscripciones desde la base de datos actual a los metadatos de la actividad y vista en la base de datos de importación principal de BAM. Se utiliza para habilitar la exploración de las actividades distribuidas.  
  
 Puede especificar el servidor de destino como una instancia de SQL Server, por ejemplo 'mymachine2\myinstance'.  
  
 **Ejemplos**  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a>get-references (comando)  
 **Uso**  
  
 **bm.exe get-references [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que se va a obtener una lista de referencias. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos que se va a obtener una lista de referencias. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Enumera las referencias habilitadas en el equipo en el que se ejecuta el comando.  
  
 **Ejemplos**  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a>Comando disable-reference  
 **Uso**  
  
 **bm.exe disable-reference - TargetServer:\<TargetServer\> - TargetDatabase:\<base de datos de destino\>[-Server:\<server\> ] [-base de datos:\<base de datos \> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|TargetServer:\<servidor de destino\>|Nombre del servidor desde el que se deshabilitan las referencias. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe.|  
|TargetDatabase:\<base de datos de destino\>|Nombre de la base de datos desde la que se deshabilitan las referencias.|  
|Servidor:\<server\>|Opcional: El nombre del servidor en que hace referencia al destino servidor y base de datos se va a deshabilitar. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos en la que hace referencia al servidor de destino y la base de datos son va a deshabilitar. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Deshabilita una referencia a otra base de datos de importación principal de BAM  distribuida en el servidor de destino.  
  
 Puede especificar el servidor de destino como una instancia de SQL Server, por ejemplo 'mymachine2\myinstance'.  
  
 **Ejemplos**  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)