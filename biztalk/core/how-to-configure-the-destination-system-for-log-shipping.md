---
title: Cómo configurar el sistema de destino del trasvase de registros | Microsoft Docs
ms.custom: ''
ms.date: 2015-12-03
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- system failures, preventing
- log shipping
- databases, backing up
- backing up, databases
- system failures, backing up
- backing up, system failures
ms.assetid: 7b4425f5-b105-4fb2-a503-94ca1e75ad55
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ee5c7a5d59ce60923fa4ad3ba015f60bc30a0c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971469"
---
# <a name="how-to-configure-the-destination-system-for-log-shipping"></a>Cómo configurar el sistema de destino para el envío de registros
El trasvase de registros proporciona funciones de servidor en espera para reducir el tiempo de inactividad en caso de error del sistema. El envío de registros permite enviar automáticamente registros de transacciones desde el sistema de origen al de destino. En el sistema de destino, los registros de transacciones se restauran en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos; mantienen estrechamente sincronizados con las bases de datos de origen.  
  
 El envío de registros funciona tanto en entornos de servidor distribuido como de un solo servidor. El servidor o grupo de servidores que contiene datos activos se conoce como sistema de origen (o principal). El servidor o grupo de servidores que se usa para restaurar las copias de seguridad de base de datos que genera el sistema de origen (o principal) se conoce como sistema de destino (o secundario).  
  
 [Acerca del trasvase de registros](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server) en el código SQL documentación proporciona detalles específicos.  
  
 Puede seguir los siguientes pasos para crear un sistema de destino compuesto de un servidor para un sistema de origen único. Si el sistema de destino contiene varios servidores, repita los pasos en cada uno de éstos.  
  
> [!IMPORTANT]
>  Guarde siempre una copia de sus archivos de copia de seguridad en una ubicación segura. Aunque haya registrado copias de seguridad, no podrá restaurar las bases de datos sin los archivos de copia de seguridad.  
  
## <a name="prerequisites"></a>Requisitos previos  
* Inicie sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  
  
* Utilice la misma versión de SQL Server en los sistemas de origen y destino. SQL Server debe instalarse en la misma ubicación relativa en los sistemas de origen y destino.  
  
* El directorio para el registro de transacciones SQL (archivos .LDF) del sistema de origen también debe existir en el sistema de destino. Si este directorio no se encuentra en el sistema de destino, cree el directorio con el mismo nombre y con los mismos permisos del sistema de origen.  
  
### <a name="configure-the-destination-system-for-log-shipping"></a>Configurar el sistema de destino del trasvase de registros  
  
1. En el sistema de destino, abra **SQL Server Management Studio**y conectarse a SQL Server. Seleccione **maestro** de bases de datos disponibles.  
  
2. En el **archivo** menú, **abierto** el siguiente script SQL:  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Schema.sql  
   ```  
  
3. En el **consulta** menú, seleccione **Execute**.  
  
    El *script LogShipping_Destination_Schema* quita y vuelve a crear las tablas utilizadas para restaurar las bases de datos de origen del sistema de destino. Se incluyen las tablas para almacenar la lista de bases de datos que se están recuperando, copias del historial de copias de seguridad importado desde la base de datos BizTalkMgmtDb del sistema de origen e información acerca de los trabajos del Agente SQL Server que se configuraron para que se ejecutaran respecto a las bases de datos de origen.  
  
4. En el **archivo** menú, **abierto** el siguiente script SQL:  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Logic.sql  
   ```  
  
5. En el **consulta** menú, seleccione **Execute**.  
  
6. En el equipo o equipos identificados como sistemas de destino, abra **SQL Server Management Studio** y conectarse a SQL Server.  
  
7. Seleccione **nueva consulta**. Pegue el comando siguiente en la ventana de consulta:  
  
   ```  
   exec bts_ConfigureBizTalkLogShipping @nvcDescription = '<MyLogShippingSolution>',  
   @nvcMgmtDatabaseName = '<BizTalkServerManagementDatabaseName>',  
   @nvcMgmtServerName = '<BizTalkServerManagementDatabaseServer>',  
   @SourceServerName = null, -- null indicates that this destination server restores all databases  
   @fLinkServers = 1 -- 1 automatically links the server to the management database  
   ```  
  
    A continuación:  
  
   1.  En el sistema de destino, habilite  **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**.  
  
   2.  En la ventana de consulta, reemplace *\<MyLogShippingSolution\>* con una descripción significativa entre comillas simples.  
  
   3.  En la ventana de consulta, reemplace *\<BizTalkServerManagementDatabaseName\>* y *\<BizTalkServerManagementDatabaseServer\>* con el nombre y la ubicación de la base de datos de administración de BizTalk de origen, entrecomillado comillas simples.  
  
   > [!NOTE]
   >  Si tiene más de un servidor de origen, puede restaurar cada uno de ellos en su propio servidor de destino. En cada servidor de destino en el  **@SourceServerName = null** parámetro, reemplace *null* con el nombre del servidor de origen que corresponda, flanqueado por comillas (por ejemplo,  **@SourceServerName = 'Miservidordeorigen',**).  
  
8. En el **consulta** menú, seleccione **Execute**.  
  
   > [!IMPORTANT]
   >  Si la consulta produce un error, después de corregir el problema con la consulta, debe empezar desde el paso 1 de este procedimiento para volver a configurar el sistema de destino.  
  
   > [!NOTE]
   >  Los trabajos de restauración del sistema de destino intentan volver a crear los archivos de datos y registros para cada una de las bases de datos restauradas en la misma ubicación en la que existieron en el servidor de base de datos de origen.  
  
9. En el sistema de destino en **SQL Server Management Studio**, expanda **del Agente SQL Server**y expanda **trabajos**.  
  
     En el panel de detalles, hay tres trabajos nuevos:  
  
   - **Registro BTS-obtener historial de copia de seguridad**  
  
      Este trabajo de BizTalk mueve los registros de historial de copia de seguridad desde el origen al destino. De forma predeterminada, está programado para ejecutarse cada minuto. Este trabajo se ejecuta con la mayor frecuencia posible para mover registros de historial del origen al destino. En el caso de que se produzca un error en el sistema de origen, el servidor identificado como el sistema de destino sigue procesando los registros de historial ya importados.  
  
   - **Servidor de registro BTS-Restaurar bases de datos**  
  
      Este trabajo de BizTalk restaura los archivos de copia de seguridad para las bases de datos del origen en el servidor de destino. De forma predeterminada, está programado para ejecutarse cada minuto. Este trabajo se ejecuta de forma continua sin completarse siempre que haya archivos de copia de seguridad que restaurar. Como precaución adicional, puede ejecutar este trabajo una vez más para garantizar que está completo.  
  
   - **Registro BTS-Restaurar en marca**  
  
      Este trabajo de BizTalk restaura todas las bases de datos a una marca en la última copia de seguridad de registros. Con ello, se garantiza que todas las bases de datos se encuentren en un estado transaccionalmente coherente. Además, este trabajo vuelve a crear todos los trabajos del Agente SQL Server que estuvieron en el sistema de origen en el sistema de destino.  
  
     > [!IMPORTANT]
     >  Debe supervisar estos trabajos para garantizar que no se produzcan errores en ellos.  
  
10. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], vaya a la siguiente carpeta:  
  
     equipo de 32 bits: %SystemDrive%\Program Files\Microsoft BizTalk Server \<versión\>\Schema\Restore  
  
     equipo de 64 bits: %SystemDrive%\Program Files (x86) \Microsoft BizTalk Server \<versión\>\Bins32\Schema\Restore  
  
11. Haga clic en **SampleUpdateInfo.xml**y seleccione **editar**. Realice lo siguiente:  
  
    -   Reemplace todas las instancias de **"SourceServer"** con el nombre del sistema de origen.  
  
    -   Reemplace todas las instancias de **"DestinationServer"** con el nombre del sistema de destino.  
  
    > [!IMPORTANT]
    >  Flanquee el nombre de los sistemas de origen y destino con comillas.  
    > 
    > [!NOTE]
    >  Si cambió el nombre de cualquier base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe actualizar los nombres de la base de datos en el archivo XML.  
    > 
    > [!NOTE]
    >  Si ha configurado BAM, debe agregar las siguientes líneas en el **OtherDatabases** sección de la **SampleUpdateInfo.xml** archivo para las bases de datos BAMAlertsApplication y BAMAlertsNSMain:   
    > `<Database Name="BAM Alerts Application DB" oldDBName="BAMAlertsApplication" oldDBServer="SourceServer" newDBName=" BAMAlertsApplication" newDBServer="DestinationServer"/>`  
    > `<Database Name="BAM Alerts Instance DB" oldDBName="BAMAlertsNSMain" oldDBServer="SourceServer" newDBName="BAMAlertsNSMain" newDBServer="DestinationServer"/>`  
    > 
    >  Si ha cambiado el nombre predeterminado para estas dos bases de datos, use los nombres reales correspondientes.  
  
12. Si tiene más de una base de datos de cuadro de mensajes en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system, agregue otra línea MessageBoxDB a la lista y, a continuación, establezca **IsMaster = "0"** para las bases de datos no principales.  
  
13. Si usa BAM o el motor de reglas, quite los comentarios de estas líneas según corresponda.  
  
14. Si dispone de las bases de datos personalizados, agregarlos en el **\<OtherDatabases\>** sección. Consulte [cómo realizar copias de seguridad de bases de datos personalizadas](../core/how-to-back-up-custom-databases.md).  
  
15. Cuando termine de editar el archivo, guárdelo y salga.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md)  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [Cómo programar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-schedule-the-backup-biztalk-server-job.md)   
 [Cómo realizar copias de seguridad de bases de datos personalizadas](../core/how-to-back-up-custom-databases.md)