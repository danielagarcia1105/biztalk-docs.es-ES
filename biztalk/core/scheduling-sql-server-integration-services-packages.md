---
title: "Paquetes de programación de SQL Server Integration Services | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 037ae2cf-c352-4823-95df-9a723f2b5a81
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17d8518a8c74f1fef77cf713852f1dfc87c8ef23
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="scheduling-sql-server-integration-services-packages"></a>Programación de paquetes de SQL Server Integration Services
Los usuarios crear vistas de BAM basadas en datos almacenados en un cubo de procesamiento analítico en línea (OLAP). El paquete de actualización de cubos de Integration Services actualiza los datos del cubo para que las vistas OLAP reflejen los datos correctos.  
  
 Debe ejecutar este paquete al menos una vez para que las vistas OLAP funcionen. Para un mantenimiento continuado, es aconsejable programar una ejecución periódica del paquete.  
  
> [!IMPORTANT]
>  Si ha restaurado la base de datos de esquema de estrella de BAM o detenido [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] antes de ejecutar el paquete de servicios de integración de actualización de cubos, deberá actualizar los orígenes de datos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager o reiniciar el servicio OLAP para poder ejecutar el paquete correctamente.  
  
 Puede programar un paquete guardado para ejecutarlo en momentos determinados, una vez o en intervalos periódicos. Por ejemplo:  
  
-   Diariamente a medianoche.  
  
-   Semanalmente, los domingos a las 06:00.  
  
-   El primer o último día del mes.  
  
 Un paquete programado se ejecuta mediante [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] como un trabajo.  
  
 Para obtener información acerca de cómo ejecutar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] paquetes, consulte [http://go.microsoft.com/fwlink/?LinkId=125738](http://go.microsoft.com/fwlink/?LinkId=125738).  
  
> [!NOTE]
>  De forma predeterminada, el registro para archivar paquetes SSIS de BAM y elaborar cubos a partir de ellos está activado y almacenado en la base de datos msdb. Con el tiempo, esto puede resultar en un volumen significativo de datos de registro de eventos SSIS derivado de una gran cantidad de actividades BAM o de la ejecución frecuente de paquetes SSIS de BAM. Para resolverlo, puede eliminar las entradas de registro antiguas, ya que estas entradas se usan, principalmente, para la depuración.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo estos procedimientos, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-run-the-cube-update-integration-services-package"></a>Para ejecutar el paquete de servicios de integración de actualización de cubos  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP1** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo, en la **tipo de servidor** lista desplegable, seleccione **Integration Services**.  
  
3.  En el **nombre del servidor** lista desplegable, seleccione el nombre del servidor en el que se ejecuta el paquete.  
  
4.  En el **autenticación** lista desplegable, seleccione el tipo de autenticación que utilizan para conectarse al servidor.  
  
5.  Si es necesario, escriba su nombre de usuario y contraseña.  
  
6.  Haga clic en **Conectar**.  
  
7.  En el árbol de consola, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.  
  
8.  Haga clic en el **BAM_AN_\<nombre de la vista\>**  del paquete y, a continuación, haga clic en **Ejecutar paquete**.  
  
### <a name="to-run-the-maintaining-bam-data-integration-services-package"></a>Para ejecutar el paquete de mantenimiento de servicios de integración de datos de BAM  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP1** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo, en la **tipo de servidor** lista desplegable, seleccione **Integration Services**.  
  
3.  En el **nombre del servidor** lista desplegable, seleccione el nombre del servidor en el que se ejecuta el paquete.  
  
4.  En el **autenticación** lista desplegable, seleccione el tipo de autenticación que utilizan para conectarse al servidor.  
  
5.  Si es necesario, escriba su nombre de usuario y contraseña.  
  
6.  Haga clic en **Conectar**.  
  
7.  En el árbol de consola, expanda **Integration Services**, expanda **paquetes almacenados**y, a continuación, haga clic en **MSDB**.  
  
8.  Haga clic en el **BAM_DM_\<nombre de la actividad\>**  del paquete y, a continuación, haga clic en **Ejecutar paquete**.  
  
### <a name="to-schedule-the-packages-to-run-regularly"></a>Para programar los paquetes para que se ejecuten con regularidad  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP1** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo, en la **tipo de servidor** lista desplegable, seleccione **motor de base de datos**.  
  
3.  En el **nombre del servidor** lista desplegable, seleccione el nombre del servidor en el que se ejecuta el paquete.  
  
4.  En el **autenticación** lista desplegable, seleccione el tipo de autenticación que utilizan para conectarse al servidor.  
  
5.  Si es necesario, escriba su nombre de usuario y contraseña.  
  
6.  Haga clic en **Conectar**.  
  
7.  En el árbol de consola, expanda el servidor y seleccione **Agente SQL Server**.  
  
8.  Si **Agente SQL Server** está deshabilitado, haga clic en **Agente SQL Server**y, a continuación, seleccione **iniciar**.  
  
9. Haga clic en **Agente SQL Server**y seleccione **nuevo trabajo**.  
  
10. En el **nuevo trabajo** cuadro de diálogo, escriba un nombre para el trabajo en el **nombre** cuadro de texto.  
  
11. En el **seleccionar una página** ventana, haga clic en **pasos**y, a continuación, haga clic en **nuevo**. Se abrirá la **nuevo paso de trabajo** cuadro de diálogo.  
  
12. En el **nombre del paso** texto, escriba un nombre de identificación del paso.  
  
13. En el **tipo** lista desplegable, seleccione **paquete SQL Server Integration Services** y en el **origen del paquete** lista desplegable, seleccione **almacén de paquetes SSIS** .  
  
14. En el **Server** lista desplegable, seleccione el servidor en el que se ejecuta el trabajo.  
  
15. Haga clic en el botón selector de archivos para el **paquete** texto, seleccione el paquete que está programando (ya sea la **BAM_DM_\<nombre de la actividad\>**  o **BAM_AN_ \<Nombre de la vista\>**  paquete) y, a continuación, haga clic en **Aceptar**.  
  
16. En el **seleccionar una página** ventana, haga clic en **programaciones**y, a continuación, haga clic en **nuevo**. Se abrirá la **nueva programación de trabajo** cuadro de diálogo.  
  
17. En el **nombre** cuadro de texto, escriba un nombre para la programación.  
  
18. Cree su programación mediante los campos de frecuencia.  
  
19. Haga clic en **Aceptar** para guardar el trabajo.  
  
    > [!NOTE]
    >  Si BAM se configura con una instancia no predeterminada de SQL Server, BAM_AN_POCube DTSPackage no se programa o ejecuta con precisión. Tiene que modificar el archivo de configuración para que los paquetes sigan ejecutándose. Para obtener más información, consulte la sección "Modificar el contenido del archivo de configuración" en [http://go.microsoft.com/fwlink/?LinkId=196768](http://go.microsoft.com/fwlink/?LinkId=196768).  
  
## <a name="see-also"></a>Vea también  
 [Administración de bases de datos de BAM](../core/managing-bam-databases.md)