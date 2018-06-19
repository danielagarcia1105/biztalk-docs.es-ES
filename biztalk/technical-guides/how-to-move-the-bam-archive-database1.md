---
title: Cómo mover la Database1 de archivo BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e371321c-6b8d-4be6-a6d2-926f6218db01
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 383aef74519f7527383d9f681f83ace2e515eba7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "26009821"
---
# <a name="how-to-move-the-bam-archive-database"></a>Cómo mover la base de datos de archivo de BAM
Este procedimiento se puede utilizar para mover la base de datos de archivo de BAM a otro servidor.  Desde una perspectiva de escenario to-end, mover la base de datos de archivo de BAM consta de dos pasos principales:  
  
-   [Mover la base de datos de archivo BAM](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_MovingArch)  
  
-   [Actualizar las referencias a la nueva base de datos de archivo BAM](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro del rol fijo de servidor sysadmin de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
##  <a name="BKMK_MovingArch"></a> Mover la base de datos de archivo BAM  
 Realice los pasos en el siguiente procedimiento para mover la base de datos de archivo de BAM.  
  
#### <a name="to-move-the-bam-archive-database"></a>Para mover la base de datos de archivo de BAM  
  
1.  Detenga cualquier BAM cubo datos y actualización paquetes SSIS de mantenimiento, o impida su ejecución hasta que haya restaurado la base de datos de archivo de BAM.  
  
2.  Detenga todos los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
3.  Detenga el servicio IIS.  
  
4.  Detenga el servicio de notificación de alertas de BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En el símbolo del sistema, escriba:  
  
         **Net stop NS$ BamAlerts**  
  
5.  Hacer copia de seguridad de la base de datos de archivo de BAM en el servidor anterior. Para obtener instrucciones sobre la copia de seguridad de una base de datos, siga las instrucciones de [Cómo: copia de una base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla acerca de cómo realizar copias de seguridad de una base de datos.  
  
6.  Copiar la base de datos de archivo de BAM en la nueva [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipo.  
  
7.  Restaure la base de datos de archivo de BAM en el nuevo servidor. Para obtener instrucciones acerca de cómo restaurar la base de datos, siga las instrucciones de [Cómo: restaurar una copia de seguridad de base de datos (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla acerca de cómo restaurar una base de datos.  
  
##  <a name="BKMK_UpdateArch"></a> Actualizar las referencias a la nueva base de datos de archivo BAM  
 Después de haber movido la base de datos, debe actualizar todas las referencias a la nueva base de datos de archivo de BAM. Deben actualizar las referencias siguientes:  
  
-   Actualizar la configuración de BAM con los nuevos nombres de base de datos y el servidor. Vea [para actualizar la configuración de BAM](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig).  
  
-   Actualice los nombres de servidor y base de datos nueva en todos los paquetes SSIS de análisis BAM. Vea [para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS).  
  
###  <a name="BKMK_UpdateArchConfig"></a> Para actualizar la configuración de BAM  
  
1.  Obtenga una copia del archivo .xml utilizado para restaurar BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En un equipo que ejecuta BizTalk Server, vaya a la siguiente carpeta:  
  
        -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
             **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
        -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
             **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
    3.  En el símbolo del sistema, escriba:  
  
         **Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -base de datos:\<base de datos\>**  
  
        > [!NOTE]  
        >  Cuando se ejecuta este comando, sustituya el nombre real del servidor desde el que se va a obtener la información de configuración de \<servername\> y sustituya el nombre real de la base de datos que se va a obtener la información de configuración \<base de datos\>. Para obtener más información sobre el uso de la utilidad de administración de BAM (BM), consulte [comandos de administración de infraestructura](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
2.  Edite el archivo BAMConfiguration.xml y cambie la **ServerName** en la `<DeploymentUnit Name="ArchivingDatabase">` sección para el nuevo nombre del servidor.  
  
3.  Guarde el archivo BAMConfiguration.xml y ciérrelo.  
  
4.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
5.  En un equipo que ejecuta BizTalk Server, vaya a la siguiente carpeta:  
  
    -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 64 bits de Windows Server:  
  
         **% ProgramFiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
    -   Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en una versión de 32 bits de Windows Server:  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6.  En el símbolo del sistema, escriba:  
  
     **bm.exe update-config -FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_UpdateArchSSIS"></a> Para actualizar los nombres de servidor y base de datos en todos los paquetes SSIS de BAM  
  
1.  Actualice los nombres de servidor y base de datos en todos los paquetes SSIS análisis BAM, que tienen el prefijo "BAM_DM_". Para ello, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2** o **Microsoft SQL Server 2008 SP1**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.  
  
2.  En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto. Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.  
  
3.  En el **nuevo proyecto** cuadro de diálogo, en la **tipos de proyecto** cuadro, haga clic en **proyectos de Business Intelligence**. En el panel derecho, en la **plantillas** cuadro, haga clic en **proyecto de Integration Services**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el **proyecto de Integration Services** cuadro de diálogo, en el Explorador de soluciones, haga clic en **paquetes SSIS**y, a continuación, haga clic en **Agregar paquete existente**.  
  
5.  En el **Agregar copia de paquete existente** cuadro de diálogo, en la **Server** lista desplegable, seleccione el servidor que contiene los paquetes BAM_DM_ *.  
  
6.  En **ruta de acceso del paquete**, haga clic en el botón de puntos suspensivos.  
  
7.  En el **paquete SSIS** cuadro de diálogo, seleccione el paquete que desea actualizar, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.  
  
     Con ello, el paquete aparecerá en el Explorador de soluciones.  
  
8.  En el Explorador de soluciones, haga doble clic en el paquete que agregó en el paso anterior. En **administradores de conexión** pestaña (disponible hacia la parte inferior de la pantalla), haga doble clic en el número de origen de datos 2 (base de datos BAMArchive).  
  
9. En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]  
    >  Repita este paso para el número de origen de datos 3 (base de datos MSDB).  
  
10. Haga clic en el **Explorador de paquetes** ficha, haga doble clic en el **Variables** carpeta y, a continuación, actualice los valores de la **ArchivingDatabase**, **ArchivingServer** , **PrimaryImportDatabase**, y **PrimaryImportServer** variables. Debe actualizar los valores para que apunte al nuevo servidor y base de datos.  
  
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
  
21. Iniciar todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios. Para obtener más información, vea el tema [cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
22. Inicia el servicio IIS.  
  
23. Inicie el servicio de notificación de alertas de BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En el símbolo del sistema, escriba:  
  
         **Net start NS$ BamAlerts**  
  
24. Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.  
  
> [!TIP]  
>  Como una buena práctica, debe mover también los paquetes de SSIS BAM_DM_ * al servidor que hospeda la base de datos BAMArchive.  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos](../technical-guides/moving-databases.md)