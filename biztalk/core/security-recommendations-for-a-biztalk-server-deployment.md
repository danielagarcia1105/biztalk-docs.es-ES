---
title: "Recomendaciones de seguridad para una implementación de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, security
- Windows Server 2003 Security Configuration Wizard (SCW)
- user accounts, security
- permissions
- access control
- security, deploying
- channel level encryption
- security, permissions
ms.assetid: 033fff11-d989-46ba-83ed-5063f7cd7818
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fad4f4a734f396b3ffec726b65fe19d62ee0f5ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-recommendations-for-a-biztalk-server-deployment"></a>Recomendaciones de seguridad para una implementación de BizTalk Server
Esta sección contiene recomendaciones de alto nivel independientes de las características para proteger el entorno de Microsoft BizTalk Server.  
  
## <a name="topology-level-recommendations"></a>Recomendaciones de nivel de topología  
 **Utilice el cifrado de nivel de canal.** De forma predeterminada, los flujos de datos de red entre diferentes componentes de BizTalk Server se encuentran en texto sin cifrar. Cuando existe la preocupación de que se detecten o alteren los datos durante la transmisión de mensajes de un equipo a otro, se recomienda usar cifrado de nivel de canal, tal como el protocolo de seguridad de Internet (IPSec) o la Capa de sockets seguros (SSL). Aunque BizTalk Server no configura el cifrado de nivel de canal de forma predeterminada, no coloca datos críticos, como claves y contraseñas de cifrado, en el texto sin cifrar durante la conexión. La base de datos de SSO administra información confidencial al almacenarla en formato cifrado mediante el secreto principal (clave de cifrado) proporcionado por el servidor secreto principal. De forma predeterminada, la base de datos de SSO recibe, almacena y envía información confidencial en formato cifrado.  
  
 Para obtener más información acerca de SSL, consulte [http://go.microsoft.com/fwlink/p/?LinkId=189708](http://go.microsoft.com/fwlink/p/?LinkId=189708).  
  
 **Ayudar a garantizar la seguridad física de los servidores.** También debe tener en cuenta la seguridad física de los servidores, dispositivos, redes, cables, fuente de alimentación y otros componentes. Debe colocar los equipos en un entorno seguro y limitar el acceso a los equipos que contengan información empresarial importante, como las bases de datos.  
  
 **Instale únicamente los componentes que se va a usar.** Si debe instalar Internet Information Services (IIS) en el entorno (en los equipos de la red perimetral o en los equipos en los que se ejecutan adaptadores de HTTP y SOAP), no es necesario que instale los subcomponentes de IIS Protocolo de transferencia de archivos (FTP), WebDAV y Protocolo simple de transferencia de correo. De igual modo, asegúrese de que solamente instala y configura las características de BizTalk Server necesarias para el entorno. Por ejemplo, configure el adaptador de BizTalk para Message Queue Server únicamente si lo utiliza. Esto le ayudará a reducir la  superficie de ataque potencial del entorno.  
  
Si utiliza Internet Explorer, se recomienda que activar la seguridad mejorada de Internet Explorer.  
  
 **Instalar service packs y actualizaciones**. Se recomienda instalar siempre el service Pack de producto más recientes y las actualizaciones de Microsoft en todos los servidores que tienen [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] recursos, incluidos los [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)].  
  
 **No guarde contraseñas como texto sin formato en secuencias de comandos o archivos de enlace.** Debe guardar las secuencias de comandos en ubicaciones con listas de control de acceso discrecional (DACL) seguras para que sólo los administradores de BizTalk Server tengan permiso para verlas, modificarlas y ejecutarlas. Cuando las secuencias de comandos y los archivos de enlace requieran contraseñas, asegúrese de ocultarlas tan pronto como utilice las secuencias de comandos para tareas de configuración o implementación. No deje las contraseñas de estos archivos como texto sin cifrar.  
  
 **Usar controles de acceso discrecional seguro listas (DACL).** Asegúrese de que sólo proporciona acceso a un recurso a los usuarios y a las cuentas que lo utilizan, así como de que les concede los permisos mínimos para realizar la tarea. Coloque las secuencias de comandos de configuración en ubicaciones con DACL para el administrador de BizTalk Server y no inserte contraseñas como texto sin cifrar en las secuencias de comandos. Asegúrese de que los directorios temporales de todas las cuentas de servicio que utiliza BizTalk Server tienen DACL, de forma que sólo tengan acceso a ellos la cuenta de servicio y los administradores de BizTalk.  
  
 Si dispone de adaptadores personalizados, se recomienda almacenar los componentes de extensión de los adaptadores en una ubicación con listas DACL seguras, de forma que solo los administradores de BizTalk Server tengan permiso de escritura para estos componentes.  
  
 **No coloque los servidores BizTalk Server en la red perimetral.** Independientemente del tamaño de la empresa, la colocación de servidores BizTalk Server en la red perimetral los expone a ataques directos desde Internet y a ataques de otros servidores de la red perimetral cuya seguridad se puede haber comprometido. Dado que BizTalk Server se comunica con bases de datos de Microsoft SQL Server en el dominio de datos, un usuario malintencionado puede aprovechar el hecho de que un servidor BizTalk Server esté desprotegido para alterar datos de configuración y de procesamiento importantes de la empresa.  
  
## <a name="biztalk-server-groups-and-accounts"></a>Grupos y cuentas de BizTalk Server  
 **Utilice cuentas con permisos y derechos de usuario mínimos.** Todas las cuentas del sistema de BizTalk Server deben tener los derechos de usuario mínimos que necesiten para llevar a cabo las tareas. Por ejemplo, las cuentas de servicio utilizadas en los servidores de procesamiento no deben tener derechos de usuario administrativos en BizTalk Server, SQL Server o Windows Server. Para obtener más información acerca de los permisos de seguridad mínimos y derechos de usuario necesita una cuenta para realizar una tarea en BizTalk Server, vea [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md). Para obtener más información acerca de los grupos y cuentas que utiliza BizTalk Server, vea [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
 **Usar cuentas distintas para las distintas funciones.** Para garantizar la seguridad del entorno de BizTalk Server, se recomienda crear cuentas de servicio diferentes para cada una de las instancias de host que se ejecutan en el entorno. Esto también permite una mejor disponibilidad durante las actualizaciones de las contraseñas. Se recomienda que una cuenta de servicio no sea miembro de varios grupos de Windows para BizTalk Server.  
  
 Además, se recomienda usar grupos de Windows diferentes para cada host de BizTalk y que las cuentas de servicio que sean miembro de un grupo no lo sean del grupo de Windows de otro host. Esto proporciona un aislamiento de gran seguridad para los hosts de BizTalk.  
  
 Se recomienda crear un grupo de Windows solo para el host de seguimiento, así como usar una cuenta de servicio en este grupo para la instancia de host de seguimiento. No use esta cuenta de servicio para ningún otro servicio ni utilice una cuenta de administrador de BizTalk para la instancia de host de seguimiento.  
  
 **Utilice hosts diferentes para las distintas funciones.** Se recomienda crear un host únicamente para el seguimiento. Los hosts configurados para "seguimiento de host" tienen acceso de lectura y escritura a las tablas de seguimiento de la base de datos de cuadro de mensajes, así como a las tablas de la base de datos de seguimiento. Por lo tanto, todos los objetos que se ejecuten en un host que realiza el seguimiento también tienen acceso de lectura y escritura a estas tablas. Para bloquear el acceso de elementos de usuario, tales como canalizaciones y orquestaciones, a datos de seguimiento potencialmente confidenciales, se recomienda crear un host específico para el seguimiento que no procese, envíe ni reciba mensajes.  
  
 Además, se recomienda usar hosts diferentes para procesar, recibir y enviar mensajes. Posteriormente, puede aislar las cuentas de servicio que necesiten acceso a los certificados privados de la empresa. Cuanto menos código se ejecute en estas cuentas, menores serán las posibilidades de que les afecten vulnerabilidades, lo que a su vez disminuye el riesgo de poner en peligro los certificados privados.  
  
 **Cambiar las contraseñas periódicamente.** Debe cambiar periódicamente la contraseña de las cuentas de servicio. Tenga en cuenta que puede tener varias cuentas de servicio para las instancias de host y que, por tanto, debe cambiar la contraseña de cada una de ellas.  
  
> [!CAUTION]
>  Debe cambiar las contraseñas de la cuenta de servicio de una instancia de host en la consola de administración de BizTalk. Cambiar la contraseña de la cuenta de servicio de una instancia de host en la consola de administración de equipos puede causar problemas de configuración.  
  
 **Restrinja la pertenencia al grupo de administradores de BizTalk.** Los administradores de BizTalk Server tienen derechos de usuario que abarcan todo el entorno de BizTalk Server, incluido el acceso a la mayoría de datos, ya estén cifrados o no. Por tanto, una configuración inadecuada debido a un error del administrador de BizTalk puede causar graves carencias de seguridad. El comportamiento erróneo de un administrador de BizTalk puede causar un gran daño al sistema, como una puesta en peligro de la confidencialidad, integridad y disponibilidad de los datos de clientes.  
  
 En los casos en los que los programadores implementen directamente orquestaciones en equipos en el entorno de producción, los administradores de dominio deben conceder a los programadores derechos de usuario de administrador de BizTalk. Esto no se recomienda por el motivo indicado anteriormente.  
  
 **Restrinja la pertenencia al grupo de administradores de COM +.** Por varios motivos de arquitectura, el administrador COM+ tiene derechos de administrador en varios componentes de BizTalk Server. Por razones prácticas, debe suponer que un administrador COM+ de un equipo es también un administrador de BizTalk y limitar la pertenencia a este grupo en los servidores de producción de BizTalk.  
  
 **Concede a los usuarios acceso únicamente a los equipos que ejecutan los servicios que necesitan tener acceso a.** No todas las cuentas necesitan disponer de permisos para todos los equipos. Las instancias de host de BizTalk almacenan información confidencial en memoria; pueden ser datos cruciales, como contraseñas o información empresarial. En estos equipos debe configurar una directiva de usuario local muy estricta. Por ejemplo, en estos equipos, conceda únicamente derechos de inicio de sesión a las personas que los necesiten para realizar el mantenimiento de la implementación. De este modo se reducirán las amenazas que pueden producirse por el acceso al archivo de intercambio y los volcados.  
  
 **Limitar los permisos del grupo Usuarios avanzados o quítelo.** Los permisos predeterminados del grupo Usuarios avanzados conceden a los miembros de este grupo derechos de usuario para modificar la configuración de todo el equipo, como los ensamblados de BizTalk registrados en la caché de ensamblados global (GAC). Todos los equipos tienen una GAC, que contiene los ensamblados que comparten una o más aplicaciones. Se recomienda quitar el permiso de cambiar ensamblados del grupo Usuarios avanzados o eliminar el grupo Usuarios avanzados de BizTalk Server de producción.  
  
 
## <a name="see-also"></a>Vea también  
 [Control de acceso para grupos y cuentas de servicio](../core/access-control-for-groups-and-service-accounts.md)   
 [Control de acceso para los Roles administrativos](../core/access-control-for-administrative-roles.md)   
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)   
 [Planeación de la seguridad](../core/planning-for-security.md)