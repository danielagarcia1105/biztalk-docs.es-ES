---
title: Cómo mover la base de datos2 del esquema de estrella de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6832ac2-c8c5-4515-883e-26d125d6ace0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ad0e2b649757ee591b476f29d030b2d49b8850
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017024"
---
# <a name="how-to-move-the-bam-star-schema-database"></a>Cómo mover la base de datos de esquema de estrella de BAM
Este procedimiento se puede utilizar para mover la base de datos de esquema de estrella de BAM a otro servidor.  Desde una perspectiva de escenario de extremo a otro, mover la base de datos de esquema de estrella de BAM consta de dos pasos principales:  
  
-   [Mover la base de datos de esquema de estrella de BAM](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarMoveDB)  
  
-   [Actualizar las referencias a la nueva base de datos de esquema de estrella de BAM](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
##  <a name="BKMK_StarMoveDB"></a> Mover la base de datos de esquema de estrella de BAM  
 Realice los pasos en el siguiente procedimiento para mover la base de datos de esquema de estrella de BAM.  
  
#### <a name="to-move-the-bam-star-schema-database"></a>Para mover la base de datos de esquema de estrella de BAM  
  
1. Detenga todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE, o impida su ejecución hasta que se haya restaurado la base de datos de esquema de estrella de SAE.  
  
2. Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
3. Detenga el servicio IIS.  
  
4. Detenga el servicio de notificación de alertas de BAM:  
  
   1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
   2.  En el símbolo del sistema, escriba:  
  
        **Net stop NS$ BamAlerts**  
  
5. Copia de seguridad de la base de datos de esquema de estrella de BAM del antiguo servidor. Para obtener instrucciones sobre copias de una base de datos, siga las instrucciones de [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros acerca de cómo realizar copias de seguridad de una base de datos.  
  
6. Copie la base de datos de esquema de estrella de BAM en el nuevo [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  
  
7. Restaure la base de datos de esquema de estrella de BAM en el nuevo servidor. Para obtener instrucciones sobre cómo restaurar la base de datos, siga las instrucciones de [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla sobre cómo restaurar una base de datos.  
  
##  <a name="BKMK_StarUpdate"></a> Actualizar las referencias a la nueva base de datos de esquema de estrella de BAM  
 Después de haber movido la base de datos, debe actualizar todas las referencias a la base de datos de esquema de estrella de BAM nuevo. Deben actualizarse las referencias siguientes:  
  
-   Actualice la configuración de BAM con los nuevos nombres de base de datos y el servidor. Consulte [para actualizar la configuración de BAM](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig).  
  
-   Actualice los nombres de servidor y base de datos nueva en todos los paquetes SSIS de análisis BAM. Consulte [para actualizar los nombres del servidor y base de datos en todos los paquetes de SSIS de BAM](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef).  
  
-   Actualice los nombres de servidor y base de datos nueva en orígenes de datos para todos los cubos de OLAP no. Consulte [para actualizar los nombres del servidor y base de datos en orígenes de datos para todos los cubos de OLAP no](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP).  
  
###  <a name="BKMK_StarUpdateBAMConfig"></a> Para actualizar la configuración de BAM  
  
1. Obtenga una copia del archivo .xml utilizado para restaurar BAM:  
  
   1. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
   2. En un equipo que ejecuta BizTalk Server, vaya a la carpeta siguiente:  
  
      - Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
         **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
      - Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
   3. En el símbolo del sistema, escriba:  
  
       **Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -base de datos:\<base de datos\>**  
  
      > [!NOTE]
      >  Al ejecutar este comando, sustituya el nombre real del servidor desde el que se va a obtener la información de configuración \<servername\> y sustituya el nombre real de la base de datos que se va a obtener la información de configuración \<base de datos\>. Para obtener más información sobre el uso de la utilidad de administración de BAM (BM), consulte [comandos de administración de infraestructura](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
2. Edite el archivo BAMConfiguration.xml y cambie el **ServerName** en la `<DeploymentUnit Name="StarSchemaDatabase">` sección para el nuevo nombre del servidor.  
  
3. Guarde el archivo BAMConfiguration.xml y ciérrelo.  
  
4. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
5. En un equipo que ejecuta BizTalk Server, vaya a la carpeta siguiente:  
  
   - Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
      **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
   - Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6. En el símbolo del sistema, escriba:  
  
    **bm.exe update-config-FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_StarUpdateRef"></a> Para actualizar los nombres del servidor y base de datos en todos los paquetes de SSIS de BAM  
  
1.  Actualice los nombres de servidor y base de datos en todos los paquetes SSIS análisis BAM, que tienen el prefijo "Bam_an_". Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.  
  
2.  En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto. Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.  
  
3.  En el **nuevo proyecto** cuadro de diálogo el **tipos de proyecto** cuadro, haga clic en **proyectos de Business Intelligence**. En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en MSDB.  
  
4.  En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que se ha actualizado anteriormente y, a continuación, haga clic en **Importar paquete**.  
  
5.  En el **Importar paquete** cuadro de diálogo desde el **ubicación del paquete** lista desplegable, seleccione sistema de archivos.  
  
6.  En **ruta de acceso de paquete**, vaya al proyecto guardado, seleccione el archivo. dtsx para el paquete que desea importar y, a continuación, haga clic en abierto.  
  
7.  Haga clic en el cuadro Nombre del paquete para rellenar automáticamente el cuadro.  
  
     Con ello, el paquete aparecerá en el Explorador de soluciones.  
  
8.  Repita el paso 18 al 21 para todos los paquetes que desea actualizar. En **administradores de conexión** pestaña (disponible hacia la mitad inferior de la pantalla), haga doble clic en el número de origen de datos 2 (base de datos BAMStarSchema).  
  
9. Iniciar todos ** servicios.  
  
    > [!NOTE]  
    >  Inicie el servicio de notificación de alertas de BAM:  
  
10. Net start NS$ BamAlerts En el **Agregar administrador de conexiones de Analysis Services** cuadro de diálogo, haga clic en **editar**.  
  
11. En el **Connection Manager** cuadro de diálogo el **nombre del servidor** cuadro, escriba el nombre del servidor, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.  
  
12. Haga clic en el **Explorador de paquetes** pestaña, haga doble clic en el **Variables** carpeta y, a continuación, actualice los valores para el **AnalysisDatabase**, **AnalysisServer** , **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, y **StarSchemaServer** variables. Debe actualizar los valores para que apunte al nuevo servidor y base de datos.  
  
    > [!NOTE]  
    >  Repita el paso 4 y 12 para todos los paquetes que desea actualizar.  
  
13. Haga clic en, a continuación, **archivo** menú y, a continuación, haga clic en **guardar todo**.  
  
14. Inicie SQL Server Management Studio. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en  **SQL Server Management Studio**.  
  
15. En el **conectar al servidor** cuadro de diálogo desde el **Server** lista desplegable de tipo, seleccione **Integration Services**.  
  
16. Especifique el nombre del servidor y las credenciales para conectarse al servidor y haga clic en **Aceptar**.  
  
17. En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.  
  
18. En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que se ha actualizado anteriormente y, a continuación, haga clic en **Importar paquete**.  
  
19. En el **Importar paquete** cuadro de diálogo desde el **ubicación del paquete** lista desplegable, seleccione **sistema de archivos**.  
  
20. En **ruta de acceso de paquete**, vaya al proyecto guardado, seleccione el archivo. dtsx para el paquete que desea importar y, a continuación, haga clic en **abierto**.  
  
21. Haga clic en el cuadro Nombre del paquete para rellenar automáticamente el cuadro.  
  
    > [!NOTE]  
    >  Repita el paso 18 al 21 para todos los paquetes que desea actualizar.  
  
22. Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.  
  
23. Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.  
  
###  <a name="BKMK_UpdateDS_non_OLAP"></a> Para actualizar los nombres del servidor y base de datos en orígenes de datos para todos los cubos de OLAP no  
  
1. Actualice los nombres de servidor y base de datos en orígenes de datos para todos los cubos de OLAP no. Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2. En el **conectar al servidor** cuadro de diálogo para la **tipo de servidor** lista desplegable, seleccione **Analysis Services**, proporcione el nombre del servidor, seleccione un método de autenticación (y Proporcione las credenciales si es necesario) y, a continuación, haga clic en **Connect**.  
  
3. En el Explorador de objetos, expanda **bases de datos**, expanda **BAMAnalysis**, expanda **orígenes de datos**y, a continuación, haga doble clic en un origen de datos.  
  
4. En el **propiedades del origen de datos** diálogo cuadro, haga clic en el botón de puntos suspensivos **(...)**  contra la **cadena de conexión** propiedad.  
  
5. En el **Connection Manager** cuadro de diálogo el **nombre del servidor** cuadro, escriba el nombre del servidor que hospeda la base de datos BAMStarSchema, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.  
  
6. Iniciar todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios. Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
7. Inicia el servicio IIS.  
  
8. Inicie el servicio de notificación de alertas de BAM:  
  
   1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
   2.  En el símbolo del sistema, escriba:  
  
        **Net start NS$ BamAlerts**  
  
9. Resolver todas las instancias de seguimiento incompletas.  Para obtener información acerca de cómo resolver instancias de actividad incompletas de BAM, consulte [cómo resolver instancias de actividad incompletas](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).  
  
> [!TIP]  
>  Como una buena práctica, también debe mover los paquetes SSIS BAM_AN_ * al servidor que hospeda la base de datos BAMStarSchema.  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos](../technical-guides/moving-databases.md)