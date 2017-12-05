---
title: "Planeación del Portal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, prerequisites
- BAM portal, deploying
- developing, BAM portal
- planning, BAM portal
- BAM portal, planning
- BAM portal, developing
- deploying, BAM portal
- security, BAM portal
ms.assetid: 8a8bd331-c5a8-4d8b-9e93-96e6cd581a1d
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85f7291d56d662a8e3a9d46308d6b16ca2a1cafc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-the-bam-portal"></a>Planear el portal de BAM
Este tema describe los puntos que debería tener en cuenta cuando planee la implantación del portal de Supervisión de la actividad económica (BAM).  
  
## <a name="prerequisites"></a>Requisitos previos  
 **Requisitos del sistema**. Además de los requisitos del sistema para que BizTalk Server, debe instalar el software siguiente para instalar el portal de BAM:  
  
-   Servicios de Internet Information Server (IIS)  
  
-   Microsoft Office Excel  
  
-   Microsoft Internet Explorer  
  
-   Microsoft .NET Framework  
  
-   Microsoft XML Core Services (MSXML) 6.0  
  
-   Microsoft Data Access Components (MDAC) 2.7  
  
## <a name="configuration-planning"></a>Planeamiento de la configuración  
 **Migrar desde versiones anteriores de BizTalk Server**. Una vez realizada la migración versiones anteriores de BizTalk Server, es posible que las instalaciones de las páginas existentes en el portal de BAM ya no sean funcionales. Para que el portal de BAM funcione correctamente, vea las consideraciones y directrices para BAM descritas en la guía de actualización de BizTalk Server.  
  
 **Las bases de datos**. Tenga en cuenta la información siguiente cuando realice el planeamiento de bases de datos.  
  
-   Será necesario que planee los índices de sus bases de datos para mejorar el rendimiento. Las columnas de fecha y hora normalmente necesitan un índice en la dimensión de progreso. Las consultas de la dimensión de progreso que no tengan índices son lentas y tendrán un impacto negativo en el rendimiento de la tabla de importación principal de ASE.  
  
-   Tendrá que tener en cuenta si debe configurar BAM sin alertas.  
  
 **SQL Server Notification Services**. Los Servicios de notificación del servidor SQL Server no admiten host locales o direcciones IP para que los nombres de servidores identifiquen los servidores.  Se puede producir esta situación en dos ubicaciones:  
  
1.  Durante la configuración – Si ha seleccionado BAM y ha activado las alertas, el proceso de configuración le pedirá un nombre de servidor.  
  
2.  Modificar la configuración del archivo .xml – Si intenta modificar la configuración del archivo .xml resultante del proceso de configuración en lugar de volver a utilizarla.  
  
 **Instalación de IIS**. Portal de BAM sólo se ejecuta en un modo de 32 bits. Si instala IIS en un equipo de 64 bits, debe asegurarse de que ASP.NET 2.0 está habilitado en el modo de 32 bits. Para ello, abra el Administrador de IIS, abra **grupo de aplicaciones**, seleccione el grupo de aplicaciones (BAMAppPool) y, a continuación, haga clic en **configuración avanzada**. En **Habilitar aplicaciones de 32 bits**, seleccione **True**. Para obtener más información, consulte la guía de actualización de BizTalk Server.  
  
## <a name="deployment-planning"></a>Planeamiento de la implementación  
 **Implementación de varios equipos**. ¿Se está implementando BizTalk Server en un entorno de varios equipos? Si su portal de BAM está configurado en un servidor diferente del de su base de datos de alertas, debe aumentar el valor del tiempo de espera del servicio de consulta en un entorno de varios servidores. Para obtener información de configuración adicional, consulte [personalizar la configuración del Portal de BAM](../core/customizing-the-bam-portal-configuration.md).  
  
-   **Implementación en varias culturas**. ¿Se está implementando BizTalk Server en un entorno multicultural? Cuando instala BizTalk Server, la interfaz de usuario (UI) está en el mismo idioma que la versión que ha instalado y el portal de BAM adquiere los parámetros de la cultura del usuario que lo configura. Para modificar el archivo web.config del portal de BAM para reflejar la configuración de la referencia cultural correcta, consulte [personalizar la configuración del Portal de BAM](../core/customizing-the-bam-portal-configuration.md).  
  
 **Implementación de clúster**. ¿Está realizando la implementación en un clúster de equilibrio de carga de red (NLB)? Vea [personalizar la configuración del Portal de BAM](../core/customizing-the-bam-portal-configuration.md) para obtener información de configuración adicional.  
  
 **SSL**. ¿Está implementando el portal de BAM en una instalación de IIS mediante SSL? Consulte la [personalizar la configuración del Portal de BAM](../core/customizing-the-bam-portal-configuration.md) tema para obtener información de configuración adicional.  
  
 Es necesario que los usuarios que crean vistas tengan instalado el complemento de BAM para Excel.  
  
## <a name="permissions"></a>Permissions  
 **Administrador de BAM**. El comando add-account del administrador de BAM (bm.exe) no concede automáticamente permisos de bases de datos al usuario que se ha agregado. Esto se debe a que solo es necesario tener permisos dbo para ejecutar el administrador de BAM. En consecuencia, obtener acceso a agregaciones en tiempo real (ATR) desde el portal de BAM genera un error en el servidor SQL Server, a no ser que pertenezca a ciertos grupos del servidor SQL Server, como se detalla a continuación.  
  
 **Roles de SQL Server**. Para concederle a un usuario acceso a una base de datos, debe ser miembro del grupo securityadmin o sysadmin.  
  
 Un miembro del grupo securityadmin o del sysadmin puede conceder permisos al ejecutar sp_grantdbaccess y sp_grantlogin.  
  
 Para obtener más información acerca de los roles de SQL Server, vea "Roles de arquitectura de SQL Server" en [http://go.microsoft.com/fwlink/?LinkId=56205](http://go.microsoft.com/fwlink/?LinkId=56205).  
  
## <a name="development-planning"></a>Planeamiento del desarrollo  
 **Cadenas de conexión para las tablas dinámicas**. La utilidad de administrador de BAM no siempre cambia las cadenas de conexión para las definiciones de tabla dinámica de la agregación en tiempo real (ATR) durante la implementación. Esto ocurre cuando la tabla dinámica de ATR tiene cadenas de conexión OLAP preexistentes que se han editado manualmente y la diferencia entre mayúsculas y minúsculas de la clave del valor es incorrecta. Por ejemplo, en esta línea del archivo XML de definición de BAM la clave es RTARef en lugar de la clave esperada RtaRef:  
  
 **\<PivotTableView CubeRef = "POCube" RTARef = "POAmountByLocation"\>**  
  
 Esto hace que se vuelva a generar la tabla dinámica mediante el cubo OLAP en lugar de mediante la tabla dinámica de ATR.  
  
 **Nombres de campo**. Se recomienda elegir convenciones diferentes de nombres para los nombres de campos cuando implementa una solución de supervisión. No es necesario que BAM tenga nombres únicos entre la sección de vista de la definición de BAM y el cubo OLAP de la agregación.  En consecuencia, el selector de columnas y la lista desplegable de selección de campos en el generador de consultas de la Búsqueda de actividad contienen dos campos con el mismo nombre. Esto puede generar errores al intentar seleccionar los campos correctos que se incluyan en los resultados.  
  
 Para los puertos de BizTalk Server que utilicen canalizaciones de paso a través, no es posible realizar el seguimiento de datos desde la carga del mensaje. Las canalizaciones de paso a través no evalúan los tipos de mensajes como nombres de esquemas, lo que da lugar a que todos los mensajes tengan esquemas nulos.  
  
-   Ya que el perfil de seguimiento se asigna a un par puerto y esquema, intentar realizar el seguimiento de datos de carga de mensaje para una canalización de paso a través puede dar lugar a que no se realice el seguimiento de nada.  
  
 **Nombres de las tablas dinámicas**: cuando se planea y desarrolla el usuario experimentan en la tarea de agregaciones del portal de BAM, debe crear usuario nombres descriptivos para las tablas dinámicas que se crean en Excel.  Puede personalizar los nombres si hace clic con el botón secundario en la tabla dinámica y selecciona las opciones de tabla del menú contextual.  
  
 **Intervalos de fechas**. Al crear instancias y consultas de alertas utilizando la página de búsqueda de actividad tenga en cuenta que, si el @@DateFirst valor en las consultas SQL no coincide con el valor CultureInfo.CurrentCulture.DateTimeFormat.FirstDayOfWeek, a continuación, los intervalos de fechas se muestran en la página de búsqueda no coincidirá con los límites semanales que se usa para generar las agregaciones.  
  
 Por ejemplo, si el día de inicio semanal en el servidor SQL Server está establecido en domingo, el intervalo de fechas para la segunda semana de 2005 es de 1/2/2005 a 1/8/2005 y las agregaciones del servidor SQL Server y OLAP que se muestran para la semana 2 están basadas en este intervalo de fechas. Sin embargo, si el portal de BAM determina una fecha de inicio semanal en sábado, entonces el usuario que ve los detalles de la semana 2 de 2005 verá en la página de búsqueda el intervalo de fechas desde 1/8/2005 a 1/14/2005. En consecuencia, el valor que recupera la consulta de búsqueda puede que no coincida con el valor agregado que se muestra en la tabla dinámica.  
  
 Para obtener el resultado deseado, ajuste el intervalo de tiempo en la consulta para recuperar el intervalo de fechas deseado.  
  
 **Navegación distribuida**. La característica de exploración distribuida del portal de BAM permite a los usuarios ver las relaciones de actividad a través de límites remotos. Al desarrollar actividades, tenga en cuenta lo siguiente:  
  
-   Puede que se produzcan situaciones en las que colocará actividades relacionadas de bases de datos de importación principal de BAM diferentes en la misma vista. Es posible que las actividades tengan los mismos nombres, pero que existan en servidores diferentes, como dos departamentos diferentes que tienen una actividad de pedido. Cuando el usuario del portal de BAM selecciona Vista en el panel del portal Mis vistas, verá las dos actividades enumeradas en la misma tarea.  
  
-   Si los usuarios utilizan portales de BAM en servidores diferentes para ver las vistas implementadas, es necesario que las referencias se habiliten simétricamente por orden para dos experiencias del portal, que se ejecutan cada una en la base de datos de importación principal de BAM, para que sean la misma.  
  
## <a name="see-also"></a>Vea también  
 [Personalización de la configuración del portal de BAM](../core/customizing-the-bam-portal-configuration.md)