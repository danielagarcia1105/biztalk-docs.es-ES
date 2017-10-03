---
title: "Cómo mover la Database2 de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc4f2656-2faa-4503-9551-05e1b6eceb1a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f62dc38185f9235dd7d2e08629df4099d7ec4f6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-primary-import-database"></a>Cómo mover la base de datos de importación principal de BAM
Este procedimiento se puede utilizar para mover la base de datos de importación principal de BAM a otro servidor. Desde una perspectiva de escenario to-end, mover la base de datos de importación principal de BAM consta de dos pasos principales:  
  
-   [Mover la base de datos de importación principal de BAM](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_MovingBAMPI)  
  
-   [Actualizar las referencias a la nueva base de datos de importación principal de BAM](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
##  <a name="BKMK_MovingBAMPI"></a>Mover la base de datos de importación principal de BAM  
 Realice los pasos en el siguiente procedimiento para mover la base de datos de importación principal de BAM.  
  
#### <a name="to-move-the-bam-primary-import-database"></a>Para mover la base de datos de importación principal de BAM  
  
1.  Detenga cualquier BAM cubo datos y actualización paquetes SSIS de mantenimiento, o impida su ejecución hasta que haya restaurado la base de datos de importación principal de BAM.  
  
2.  Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
3.  Detenga el servicio IIS.  
  
4.  Detenga el servicio de notificación de alertas de BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En el símbolo del sistema, escriba:  
  
         **Net stop NS$ BamAlerts**  
  
5.  Copia de seguridad principal de BAM Importar base de datos en el servidor anterior. Para obtener instrucciones sobre la copia de seguridad de una base de datos, siga las instrucciones de cómo realizar copias de seguridad de una base de datos en [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla.  
  
6.  Copiar la base de datos de importación principal de BAM en la nueva [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  
  
7.  Restaure la base de datos de importación principal de BAM en el nuevo servidor. Para obtener instrucciones acerca de cómo restaurar la base de datos, siga las instrucciones sobre cómo restaurar una base de datos en [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla.  
  
    > [!NOTE]  
    >  Si restaura la base de datos de importación principal de BAM a partir de una copia de seguridad, también debe restaurar las bases de datos de archivo de BAM, de esquema de estrella de BAM y de análisis de BAM mediante una copia de seguridad anterior a la principal de BAM.  
  
##  <a name="BKMK_BAMPIRef"></a>Actualizar las referencias a la nueva base de datos de importación principal de BAM  
 Después de haber movido la base de datos, debe actualizar todas las referencias a la base de importación principal de BAM nueva. Deben actualizar las referencias siguientes:  
  
-   Actualizar todas las bases de datos de BizTalk con el nuevo nombre del servidor. Puede hacerlo mediante el uso de la secuencia de comandos UpdateDatabase.vbs. Vea [para actualizar las bases de datos de BizTalk con el nuevo nombre del servidor](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB).  
  
-   Actualice el archivo Web.config del portal de BAM. Vea [para actualizar el archivo Web.config del portal de BAM](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config).  
  
-   Actualizar la referencia a BAM Importar base de datos principal en todos los archivos de Excel de Microsoft de datos activos de BAM. Vea [para actualizar la referencia en los archivos de Excel de Microsoft de datos activos de BAM](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel).  
  
-   Actualice los nombres de servidor y base de datos nueva en todos los paquetes SSIS de análisis BAM. Vea [para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg).  
  
-   Actualice los nombres de servidor y base de datos nueva en orígenes de datos para todos los cubos OLAP. Vea [para actualizar los nombres de servidor y base de datos en orígenes de datos para todos los cubos OLAP](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP).  
  
###  <a name="BKMK_UpdateDB"></a>Para actualizar las bases de datos de BizTalk con el nuevo nombre del servidor  
  
1.  En un equipo en el que se ejecute [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], desplácese hasta la siguiente carpeta:  
  
    -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
         **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\bins32\Schema\Restore**  
  
    -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
2.  Haga clic en **SampleUpdateInfo.xml**y, a continuación, haga clic en **editar**.  
  
3.  Convierta en comentario todas las secciones de bases de datos, a excepción de BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert.  
  
4.  En el `OldPrimaryImportDatabase` sección del archivo, para la `ServerName` propiedad, reemplace **SourceServer** con el nombre de servidor existente en el que reside la base de datos.  
  
5.  En el `PrimaryImportDatabase` sección del archivo, para la `ServerName` propiedad, reemplace **DestinationServer** con el nombre del servidor donde se ha movido la base de datos de importación principal de BAM  
  
6.  Para la BizTalkMgmtDb, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase y Alert secciones, establezca el "SourceServer" y "Servidor de destino" en el nombre del servidor existente donde residen las bases de datos.  
  
    > [!IMPORTANT]  
    >  Flanquee el nombre de los sistemas de origen y destino con comillas.  
  
    > [!NOTE]  
    >  Si cambia el nombre de alguna de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], también deberá actualizar los nombres de las bases de datos según corresponda.  
  
7.  Cuando haya terminado de editar el archivo, guárdelo y salga de él.  
  
8.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
9. En el símbolo del sistema, desplácese al directorio siguiente:  
  
    -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
         **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Schema\Restore**  
  
    -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
10. En el símbolo del sistema, escriba:  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
###  <a name="BKMK_Config"></a>Para actualizar el archivo Web.config del portal de BAM  
  
1.  En un equipo que ejecuta [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], actualice los archivos Web.config en  **\<unidad >: \Program 2010\BAMPortal\BAMManagementService\Web.Config BizTalk Server**. Actualice los nombres de servidor y base de datos en la sección siguiente en el archivo Web.config:  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
    </appSettings>  
    ```  
  
2.  En un equipo que ejecuta [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], actualice los archivos Web.config en  **\<unidad >: \Program 2010\BAMPortal\BAMQueryService\Web.Config BizTalk Server**. Actualice los nombres de servidor y base de datos en la sección siguiente en el archivo Web.config:  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
      <add key="MaxResultRows" value="2000" />  
    </appSettings>  
    ```  
  
3.  Guarde y cierre los archivos.  
  
###  <a name="BKMK_UpdateExcel"></a>Para actualizar la referencia en los archivos de Excel de Microsoft de datos activos de BAM  
  
1.  Abra el archivo de datos activos de Excel. El nombre de archivo finaliza con _LiveData.xls.  
  
2.  En el **BAM** menú, haga clic en **conexión de base de datos de BAM**.  
  
3.  En el **Seleccionar base de datos de BAM** diálogo cuadro, escriba la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo y BAMPrimaryImport la base de datos y, a continuación, haga clic en **Aceptar**.  
  
4.  En el **archivo** menú, haga clic en **cerrar y volver a Microsoft Excel**.  
  
5.  En el menú **Archivo** , haga clic en **Guardar**.  
  
###  <a name="BKMK_UpdatePckg"></a>Para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM  
  
1.  Actualice los nombres de servidor y base de datos en todos los paquetes SSIS análisis BAM, que tienen el prefijo "BAM_AN_" o "BAM_DM_". Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.  
  
2.  En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto. Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.  
  
3.  En el **nuevo proyecto** cuadro de diálogo, en la **tipos de proyecto** cuadro, haga clic en **proyectos de Business Intelligence**. En el panel derecho, en la **plantillas** cuadro, haga clic en **proyecto de Integration Services**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el **proyecto de Integration Services** cuadro de diálogo, en el Explorador de soluciones, haga clic en **paquetes SSIS**y, a continuación, haga clic en **Agregar paquete existente**.  
  
5.  En el **Agregar copia de paquete existente** cuadro de diálogo, en la **Server** lista desplegable, seleccione el servidor que contiene los paquetes BAM_AN_ * y BAM_DM_ *.  
  
6.  En **ruta de acceso del paquete**, haga clic en el botón de puntos suspensivos.  
  
7.  En el **paquete SSIS** cuadro de diálogo, seleccione el paquete que desea actualizar, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.  
  
     Con ello, el paquete aparecerá en el Explorador de soluciones.  
  
8.  En el Explorador de soluciones, haga doble clic en el paquete que agregó en el paso anterior. En **administradores de conexión** pestaña (disponible hacia la parte inferior de la pantalla), haga doble clic en el número de origen de datos 1 (base de datos BAMPrimaryImport).  
  
9. En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor y, a continuación, haga clic en **Aceptar**.  
  
10. Haga clic en el **Explorador de paquetes** ficha, haga doble clic en el **Variables** carpeta y, a continuación, actualice los valores de la **PrimaryImportDatabase** y  **PrimaryImportServer** variables. Debe actualizar los valores para que apunte al nuevo servidor y base de datos.  
  
    > [!NOTE]  
    >  Repita el paso 4 y 10 para todos los paquetes que desea actualizar.  
  
11. Haga clic en, a continuación, **archivo** menú y, a continuación, haga clic en **guardar todo**.  
  
12. Inicie SQL Server Management Studio. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en  **SQL Server Management Studio**.  
  
13. En el **conectar al servidor** cuadro de diálogo, desde el **Server** lista de tipo de lista desplegable, seleccione **Integration Services**.  
  
14. Especifique el nombre del servidor y las credenciales para conectarse al servidor y haga clic en **Aceptar**.  
  
15. En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.  
  
16. En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que actualizó anteriormente y, a continuación, haga clic en **Importar paquete**.  
  
17. En el **Importar paquete** cuadro de diálogo, desde el **ubicación del paquete** lista desplegable, seleccione **sistema de archivos**.  
  
18. En **ruta de acceso del paquete**, navegue al proyecto guardado, seleccione el archivo DTSX para el paquete que desea importar y, a continuación, haga clic en **abiertos**.  
  
19. Haga clic dentro del cuadro Nombre del paquete para rellenar automáticamente el cuadro.  
  
    > [!NOTE]  
    >  Repita el paso 16 al 19 para todos los paquetes que desea actualizar.  
  
20. Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.  
  
21. Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.  
  
###  <a name="BKMK_UpdateDSOLAP"></a>Para actualizar los nombres de servidor y base de datos en orígenes de datos para todos los cubos OLAP  
  
1.  Actualice los nombres de servidor y base de datos en orígenes de datos para todos los cubos OLAP. Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo para la **tipo de servidor** lista desplegable, seleccione **Analysis Services**, proporcione el nombre del servidor, seleccione un método de autenticación (y Proporcione credenciales si es necesario) y, a continuación, haga clic en **conectar**.  
  
3.  En el Explorador de objetos, expanda **bases de datos**, expanda **BAMAnalysis**, expanda **orígenes de datos**y, a continuación, haga doble clic en un origen de datos.  
  
4.  En el **propiedades del origen de datos** diálogo cuadro, haga clic en el botón de puntos suspensivos **(...)**  contra la **cadena de conexión** propiedad.  
  
5.  En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor que hospeda la base de datos BAMPrimaryImport, haga clic en **Aceptar**y, a continuación, haga clic en  **Aceptar**.  
  
6.  Iniciar todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios. Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
7.  Inicia el servicio IIS.  
  
8.  Inicie el servicio de notificación de alertas de BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En el símbolo del sistema, escriba:  
  
         **Net start NS$ BamAlerts**  
  
9. Resolver todas las instancias incompletas de seguimiento.  Para obtener información acerca de cómo resolver instancias incompletas de actividad BAM, consulte [cómo resolver instancias de actividad incompletas](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos](../technical-guides/moving-databases.md)