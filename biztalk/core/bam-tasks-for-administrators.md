---
title: Tareas BAM para administradores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d9ae9a6-50fa-4f82-8e48-8dffa55c127f
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b35585d4e3b3ed90df983c8a18f6833ce8aa6bf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008429"
---
# <a name="bam-tasks-for-administrators"></a>Tareas de BAM para administradores
En este tema se describen las tareas habituales que llevan a cabo los administradores de BAM para la administración de la infraestructura de BAM.  
  
## <a name="configuring-bam"></a>Configurar BAM  
 La configuración inicial de BAM se efectúa mediante el Asistente para configuración de BizTalk Server. Con este asistente, los administradores pueden:  
  
-   Habilitar las herramientas de Supervisión de la actividad económica  
  
-   Habilitar SQL Server Analysis Services para las agregaciones de BAM  
  
-   Especificar el nombre del servidor y las bases de datos utilizadas para las herramientas de BAM  
  
-   Habilitar los servicios de notificación de SQL Server para las alertas de BAM  
  
-   Especificar la cuenta utilizada para ejecutar el servicio de notificación de BAM  
  
-   Especificar el servidor SMTP utilizado para enviar alertas de BAM  
  
-   Especificar la ubicación de archivos utilizada para el almacenamiento de alertas de BAM  
  
-   Especificar el nombre del servidor SQL Server en el que residen las bases de datos de alertas de BAM  
  
-   Especificar el prefijo de los nombres de bases de datos de alertas  
  
-   Habilitar el portal de BAM en un equipo  
  
-   Especificar las cuentas del servicio Web utilizado para ejecutar el portal de BAM  
  
-   Especificar los grupos de Windows que tienen acceso al portal de BAM  
  
-   Especificar la ubicación del sitio Web del portal de BAM  
  
 Para obtener más información acerca del uso del asistente para configuración, consulte los siguientes temas:  
  
-   [Configurar alertas BAM](../install-and-config-guides/configure-biztalk-server.md)  
  
-   [Configurar herramientas de BAM](../install-and-config-guides/configure-biztalk-server.md)  
  
-   [Configurar el Portal de BAM](../install-and-config-guides/configure-biztalk-server.md)  
  
### <a name="distributed-notification-services---sql-server-2008-r2-only"></a>Servicios de notificación distribuidos - solo SQL Server 2008 R2
Si BAM se configura para ejecutarse en un entorno distribuido, se obtienen ventajas de rendimiento cuando se procesan alertas y notificaciones. Al hacerlo, los roles de proveedor, generador y distribuidor de los servicios de notificación se encontrarán en equipos distintos y será necesario instalar los servicios de notificación en el entorno de varios equipos.  

> [!NOTE]
> A partir de SQL Server 2012, BizTalk Server utiliza el correo electrónico de base de datos de SQL. Por tanto, si está utilizando SQL Server 2012 o versiones más recientes, esto no se aplica a usted. Vea [las alertas de BAM](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts) para obtener instrucciones.
  
##### <a name="to-configure-distributed-notification-services"></a>Para configurar los servicios de notificación distribuidos  
  
1.  Instalar SQL Server Notification Services. 
  
    > [!NOTE]
    >  Servicios de notificación no se incluye en SQL Server. Instalar SQL Server Notification Services al instalar BizTalk Server seleccionando la **proveedor de alertas BAM para servicios de notificación SQL** opción **Software adicional** en el  **Instalación de componentes** página del Asistente para la instalación.  
  
2.  Para crear la notificación de BAM servicio en cada equipo en el entorno distribuido, ejecute C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol register - name bamalerts-server \<nombre del servidor\> - Service - serviceusername \<alertsuseraccount\> - servicepassword \<passwd\> desde un símbolo del sistema.  
  
3.  Edite el archivo de configuración de la infraestructura de BAM en cada uno de los equipos que se va a configurar para los servicios de notificación distribuidos. Para obtener el archivo de configuración, use la **bm.exe get-config - FileName:\<archivo de salida\>**  comando.  
  
4.  Edite el archivo de configuración para que haga referencia a los servidores del entorno de los servicios de notificación distribuidos:  
  
    ```  
    <Property Name="GeneratorServerName">PFIDWYUK</Property>  
    <Property Name="ProviderServerName">PFIDWYUK</Property>  
    <Property Name="DistributorServerName">PFIDWYUK</Property>  
    ```  
  
5.  Use el bm.exe update-config - FileName:\<el archivo de configuración\> para actualizar la configuración de BAM.  
  
6.  Reinicie los servicios de notificación en todos los equipos del entorno distribuido.  
  
 Para obtener más información acerca de cómo instalar BAM en un entorno de varios equipos, consulte [instalación y configuración de BAM (Business Activity Monitoring) en un entorno de varios equipos](http://go.microsoft.com/fwlink/p/?LinkID=208597).  
  
### <a name="moving-the-bam-primary-import-database"></a>Mover la base de datos de importación principal de BAM  
 Es posible que en algún momento resulte necesario mover la base de datos de importación principal de BAM, como, por ejemplo, al actualizar el hardware o al efectuar operaciones de escalamiento vertical. Para mover la base de datos, es preciso realizar una operación de copia de seguridad y restauración. Para obtener más información acerca de este proceso, consulte [copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md).  
  
### <a name="working-with-bam-definitions"></a>Trabajar con definiciones de BAM  
 Los administradores trabajan a fondo con definiciones de BAM. La herramienta principal utilizada para trabajar con definiciones de BAM es la utilidad de administración de BAM. Mediante esta utilidad se pueden llevar a cabo las siguientes tareas:  
  
-   Cambiar actividades. Puede usar el **all implementar**, **update-all**, **remove-activity**, **y set-actvitywindow** comandos de la utilidad de administración de BAM Para cambiar las actividades implementadas.  
  
-   Aplicar índices a las tablas de actividad para mejorar el rendimiento. Usa el **índice crear** y **delete-index** comandos para modificar los índices de las actividades.  
  
-   Configurar la seguridad de las vistas. Puede usar el **Agregar cuenta** y **remove-account** comandos para conceder a los usuarios derechos de acceso a vistas.  
  
-   Configurar la exploración distribuida de actividades. Usa el **enable-reference** y **disable-reference** comandos para configurar la exploración distribuida de actividades. Para obtener más información acerca de la exploración distribuida de actividades, vea [administración distribuida navegación de actividades remotas](../core/managing-distributed-navigation-of-remote-activities.md).  
  
-   Auditar cambios. Puede enumerar los cambios en la infraestructura dinámica de BAM con el **get-changes** comando.  
  
 Para obtener una descripción de todos los comandos disponibles a través de la utilidad de administración de BAM, consulte [utilidad de administración de BAM](../core/bam-management-utility.md). Para obtener ejemplos del uso de la utilidad de administración de BAM para trabajar con definiciones de BAM, consulte [administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md).  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a>Configurar varios grupos de BizTalk para que hagan referencia a una base de datos de BAM única  
 Al configurar BAM para que use un nuevo o un grupo de BizTalk Server existente, puede configurar el grupo para utilizar las mismas bases de datos BAM que ya están en uso por otro grupo de BizTalk Server.  Para configurar BAM de este modo, se deberán llevar a cabo las siguientes tareas:  
  
-   Obtener la información de configuración de la base de datos de importación principal de BAM existente mediante el Asistente para configuración de BizTalk Server. incluidos los nombres de servidor y base de datos. Tenga en cuenta el estado de las casillas de verificación. Asegúrese de obtener la información de configuración de las páginas de alertas de BAM y herramientas de BAM.  
  
-   Configurar BAM para el nuevo grupo y especificar la información exacta que se configuró para las PIT de destino. Al especificar la información de configuración del nuevo grupo, utilice toda la información recopilada del grupo existente, a excepción del usuario de alertas de BAM, que deberá dejarlo en blanco.  
  
## <a name="backing-up-and-restoring-bam"></a>Realizar una copia de seguridad y la restauración de BAM  
 Los administradores deben elaborar un plan para situaciones de recuperación ante desastres. Es necesario realizar una copia de seguridad de las bases de datos de análisis de BAM, análisis de seguimiento de BAM, esquema de estrella de BAM, archivo de BAM e importación principal de BAM para aquellas situaciones en las que sea preciso restaurarlas.  Para obtener información acerca de la copia de seguridad y restaurar las bases de datos BAM, consulte [copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md).  
  
## <a name="working-with-renamed-servers"></a>Trabajar con servidores cuyo nombre ha cambiado  
 Al cambiar el nombre de un servidor o mover la infraestructura de BAM entre servidores, es preciso actualizar el libro de Excel mediante la actualización de las definiciones de BAM en ese libro.  
  
 Los escenarios que conllevarán la necesidad de actualizar el libro de trabajo incluyen:  
  
-   Un escenario de ensayo en el que la infraestructura de BAM se mueve a una nueva base de datos. Para asegurarse de que los libros Excel aún conservan su funcionalidad, se deben volver a implementar o migrar y, a continuación, se deben actualizar de nuevo.  
  
-   Un escenario en el que se cambia el nombre del equipo que ejecuta BizTalk Server. En este caso, no solo se requiere la actualización del libro, sino también la del origen de datos OLAP y los paquetes DTS.  
  
 Hay dos métodos que puede utilizar para actualizar el libro de Excel:  
  
-   Ejecutar el siguiente comando del administrador de BAM desde el nuevo servidor:  
  
     **bm.exe update-livedataworkbook-Name:\<libro de trabajo de datos dinámicos para update.xls\>**  
  
    > [!NOTE]
    >  También puede especificar el nuevo nombre del servidor o el nombre de la base de datos de importación principal de BAM: **bm.exe update-livedataworkbook-nombre:\<libro de trabajo de datos dinámicos para update.xls\> [-Server:\<server\>] [- Base de datos:\<base de datos\>]**  
  
-   Como alternativa, se puede actualizar el libro de Excel desde Excel:  
  
    1.  Abra el libro que desee actualizar.  
  
    2.  En el menú BAM, haga clic en **conexión de base de datos de BAM**.  
  
    3.  Especifique el nombre del nuevo servidor y el nombre de la base de datos de importación principal de BAM.  
  
## <a name="managing-alerts"></a>Administrar alertas  
 Los administradores pueden administrar las alertas de varias formas:  
  
 Se puede utilizar la utilidad de administración de BAM para implementar y quitar alertas, además de para agregar o quitar suscripciones, y para habilitar y deshabilitar alertas. Para obtener más información sobre el uso de la utilidad de administración de BAM, consulte [utilidad de administración de BAM](../core/bam-management-utility.md), [administrar la seguridad de BAM](../core/managing-bam-security.md), y [administrar definiciones de BAM](../core/managing-bam-definitions.md).  
  
 También se pueden crear y quitar alertas mediante el portal de BAM.  Para obtener información acerca de cómo crear alertas mediante el portal de BAM, consulte [búsquedas de actividad en el Portal de BAM](../core/activity-searches-in-the-bam-portal.md).  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a>Limpiar la tabla de crónica de alertas  
 Si se han configurado las alertas de BAM, se crea un trabajo de SQL para cada vista de actividad que se cree. Se usará la siguiente plantilla para asignar un nombre al trabajo:  
  
 bam_\<nombre de la vista\>_\<vista actividad\>_DelAlertHistJob  
  
 Este trabajo limpia los datos para las alertas de instancia para el elemento especificado de la auditoría \<vista actividad\> en la tabla Bam_Metadata_AlertChronicle. Si ha definido alertas de instancia en esa vista de actividad en concreto, cada vez que se active la alerta, se agregará una nueva fila a esta tabla.  
  
 Puede ejecutar este trabajo manualmente para limpiar la tabla o, si lo profiere, programarlo para que se ejecute en virtud de las necesidades de su aplicación o entorno.  
  
## <a name="see-also"></a>Vea también  
 [Administración de BAM](../core/managing-bam.md)