---
title: "Cómo mover la Database1 de análisis BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8094153-072b-427a-b3a0-7310a37cf584
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b21168c1955db8bbbae3e29019632807231b40a1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-move-the-bam-analysis-database"></a>Cómo mover la base de datos de análisis de BAM
Este procedimiento se puede utilizar para mover la base de datos de análisis de BAM a otro servidor.  Desde una perspectiva de escenario to-end, mover la base de datos de análisis de BAM consta de dos pasos principales:  
  
-   [Mover la base de datos de análisis BAM](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyMoveDB)  
  
-   [Actualizar las referencias a la nueva base de datos de análisis BAM](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
##  <a name="BKMK_AnalyMoveDB"></a>Mover la base de datos de análisis BAM  
 Realice los pasos en el siguiente procedimiento para mover la base de datos de análisis de BAM.  
  
#### <a name="to-move-the-bam-analysis-database"></a>Para mover la base de datos de análisis de BAM  
  
1.  Detenga todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE, o impida su ejecución hasta que se haya restaurado la base de datos de análisis de SAE.  
  
2.  Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
3.  Detenga el servicio IIS.  
  
4.  Detenga el servicio de notificación de alertas de BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En el símbolo del sistema, escriba:  
  
         **Net stop NS$ BamAlerts**  
  
5.  Hacer copia de seguridad de la base de datos de análisis de BAM en el servidor anterior. Para obtener instrucciones sobre la copia de seguridad de una base de datos, siga las instrucciones de [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla acerca de cómo realizar copias de seguridad de una base de datos.  
  
6.  Copiar la base de datos de análisis de BAM en la nueva [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  
  
7.  Restaure la base de datos de análisis de BAM en el nuevo servidor. Para obtener instrucciones acerca de cómo restaurar la base de datos, siga las instrucciones de [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla acerca de cómo restaurar una base de datos.  
  
##  <a name="BKMK_AnalyUpdate"></a>Actualizar las referencias a la nueva base de datos de análisis BAM  
 Después de haber movido la base de datos, debe actualizar todas las referencias a la nueva base de datos de análisis de BAM. Deben actualizar las referencias siguientes:  
  
-   Actualizar la configuración de BAM con los nuevos nombres de base de datos y el servidor. Vea [para actualizar la configuración de BAM](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig).  
  
-   Actualice los nombres de servidor y base de datos nueva en todos los paquetes SSIS de análisis BAM. Vea [para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS).  
  
###  <a name="BKMK_AnalyUpdateBAMConfig"></a>Para actualizar la configuración de BAM  
  
1.  Obtenga una copia del archivo .xml utilizado para restaurar BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En un equipo que ejecuta BizTalk Server, vaya a la siguiente carpeta:  
  
        -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
             **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
        -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
             **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
    3.  En el símbolo del sistema, escriba:  
  
         **Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -base de datos:\<base de datos\>**  
  
        > [!NOTE]  
        >  Cuando se ejecuta este comando, sustituya el nombre real del servidor desde el que se va a obtener la información de configuración de \<servername\> y sustituya el nombre real de la base de datos que se va a obtener la información de configuración \<base de datos\>. Para obtener más información sobre el uso de la utilidad de administración de BAM (BM), consulte [comandos de administración de infraestructura](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
2.  Edite el archivo BAMConfiguration.xml y cambie la **ServerName** en la `<DeploymentUnit Name="AnalysisDatabase">` sección para el nuevo nombre del servidor.  
  
3.  Guarde el archivo BAMConfiguration.xml y ciérrelo.  
  
4.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
5.  En un equipo que ejecuta BizTalk Server, vaya a la siguiente carpeta:  
  
    -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
         **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
    -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6.  En el símbolo del sistema, escriba:  
  
     **bm.exe update-config-FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_AnalyUpdateSSIS"></a>Para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM  
  
1.  Actualice los nombres de servidor y base de datos en todos los paquetes SSIS análisis BAM, que tienen el prefijo "Bam_an_". Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.  
  
2.  En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto. Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.  
  
3.  En el **nuevo proyecto** cuadro de diálogo, en la **tipos de proyecto** cuadro, haga clic en **proyectos de Business Intelligence**. En el panel derecho, en la **plantillas** cuadro, haga clic en **proyecto de Integration Services**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el **proyecto de Integration Services** cuadro de diálogo, en el Explorador de soluciones, haga clic en **paquetes SSIS**y, a continuación, haga clic en **Agregar paquete existente**.  
  
5.  En el **Agregar copia de paquete existente** cuadro de diálogo, en la **Server** lista desplegable, seleccione el servidor que contiene los paquetes BAM_AN_ *.  
  
6.  En **ruta de acceso del paquete**, haga clic en el botón de puntos suspensivos.  
  
7.  En el **paquete SSIS** cuadro de diálogo, seleccione el paquete que desea actualizar, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.  
  
     Con ello, el paquete aparecerá en el Explorador de soluciones.  
  
8.  En el Explorador de soluciones, haga doble clic en el paquete que agregó en el paso anterior. En **administradores de conexión** pestaña (disponible hacia la parte inferior de la pantalla), haga doble clic en el número de origen de datos 2 (base de datos BAMArchive).  
  
9. En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]  
    >  Repita este paso para el número de origen de datos 3 (base de datos MSDB).  
  
10. En el **administradores de conexión** ficha, haga doble clic en el número de origen de datos 4 (base de datos BAMAnalysis). En el **Agregar administrador de conexión de Analysis Services** cuadro de diálogo, haga clic en **editar**.  
  
11. En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.  
  
12. Haga clic en el **Explorador de paquetes** ficha, haga doble clic en el **Variables** carpeta y, a continuación, actualice los valores de la **AnalysisDatabase**, **AnalysisServer** , **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, y **StarSchemaServer** variables. Debe actualizar los valores para que apunte al nuevo servidor y base de datos.  
  
    > [!NOTE]  
    >  Repita el paso 4 y 12 para todos los paquetes que desea actualizar.  
  
13. Haga clic en, a continuación, **archivo** menú y, a continuación, haga clic en **guardar todo**.  
  
14. Inicie SQL Server Management Studio. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en  **SQL Server Management Studio**.  
  
15. En el **conectar al servidor** cuadro de diálogo, desde el **Server** lista de tipo de lista desplegable, seleccione **Integration Services**.  
  
16. Especifique el nombre del servidor y las credenciales para conectarse al servidor y haga clic en **Aceptar**.  
  
17. En el **Explorador de objetos**, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.  
  
18. En el **detalles del explorador de objetos** pestaña, haga clic en el paquete que actualizó anteriormente y, a continuación, haga clic en **Importar paquete**.  
  
19. En el **Importar paquete** cuadro de diálogo, desde el **ubicación del paquete** lista desplegable, seleccione **sistema de archivos**.  
  
20. En **ruta de acceso del paquete**, navegue al proyecto guardado, seleccione el archivo DTSX para el paquete que desea importar y, a continuación, haga clic en **abiertos**.  
  
21. Haga clic dentro del cuadro Nombre del paquete para rellenar automáticamente el cuadro.  
  
    > [!NOTE]  
    >  Repita el paso 18 al 21 para todos los paquetes que desea actualizar.  
  
22. Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.  
  
23. Iniciar todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios. Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
24. Inicia el servicio IIS.  
  
25. Inicie el servicio de notificación de alertas de BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En el símbolo del sistema, escriba:  
  
         **Net start NS$ BamAlerts**  
  
26. Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos](../technical-guides/moving-databases.md)