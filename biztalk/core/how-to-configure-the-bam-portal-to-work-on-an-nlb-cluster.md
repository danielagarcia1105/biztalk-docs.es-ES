---
title: "Cómo configurar el Portal de BAM para trabajar en un clúster NLB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96c04fde-dc12-42fb-9193-aa74819fe880
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73bd5013cd2a09d240fa58b7cf5283c8d1903c69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster"></a>Cómo configurar el portal de BAM para trabajar en un clúster NLB
Se puede configurar el portal de BAM para trabajar en un clúster de equilibrio de carga de red (NLB).  
  
> [!IMPORTANT]
>  Portal de BAM *sólo* se ejecuta en modo de 32 bits. Si se instala IIS en un equipo de 64 bits, debe comprobar que ASP.NET 2.0 esté habilitado en el modo de 32 bits. Para ello, abra el Administrador de IIS, abra **grupo de aplicaciones**, seleccione el grupo de aplicaciones (BAMAppPool) y, a continuación, haga clic en **configuración avanzada**. En **Habilitar aplicaciones de 32 bits**, seleccione **True**.  
>   
>  Para los requisitos adicionales de Portal de BAM, consulte [planeación para el Portal de BAM](../core/planning-for-the-bam-portal.md).  
  
### <a name="to-prepare-to-configure-bam-portal-on-an-nlb-cluster"></a>Para configurar el portal de BAM en un clúster NLB  
  
1.  Instale y configure el portal en el primer equipo.  
  
    > [!NOTE]
    >  Sólo se configura el portal en el primer equipo. Tiene la opción de habilitar el portal de BAM en un equipo diferente o en otros equipos del clúster, pero la configuración sólo se realiza en el primer equipo.  
  
2.  Instale los componentes del portal en todos los equipos que se van a incluir en el clúster NLB y, a continuación, una el resto de equipos del clúster al grupo de equipos de BizTalk en el que está configurado el portal. Debe habilitar los grupos de BizTalk Server y unirse al grupo apropiado.  
  
3.  Seleccione la base de datos de administración de BizTalk que está configurada para el equipo en el que está instalado el portal.  
  
4.  Cree el clúster NLB Para obtener más información acerca de cómo crear y administrar clústeres de equilibrio de carga de red, vea "Crear y administrar red cargar clústeres de equilibrio" en [http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206).  
  
    > [!NOTE]
    >  Antes de continuar, debería confirmar que el clúster NLB funciona correctamente fuera del contexto de BizTalk Server.  
  
    > [!NOTE]
    >  Para configurar NLB basado en hardware, consulte la documentación de su proveedor de hardware.  
  
### <a name="to-update-the-bam-configuration-to-reflect-the-location-of-the-cluster"></a>Para actualizar la configuración de BAM para reflejar la ubicación del clúster  
  
1.  Use la utilidad de administración de BAM para obtener la configuración actual de BAM. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**y el tipo [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm get-config-MyConfig.  
  
2.  Reemplace el nombre de host local por el nombre del clúster NLB. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**y escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\myconfig.  
  
3.  Únicamente para NLB basado en hardware, compruebe que el archivo de configuración contiene lo siguiente:  
  
    ```  
    <GlobalProperty Name="BAMVRoot">  
    http://<NLB IP Address>:portname/BAM</GlobalProperty>  
    ```  
  
    > [!NOTE]
    >  Los pasos 4 y 5 no son necesarios cuando se actualiza la configuración BAM en NLB basado en hardware.  
  
4.  Modifique la línea siguiente para seleccionar el clúster NLB al reemplazar el nombre del equipo (machinename) por el nombre del clúster:  
  
    ```  
    <GlobalProperty Name=" BAMVRoot">  http://machinename:portname/BAM  
    </GlobalProperty>   
    ```  
  
5.  Guarde la nueva configuración. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**y el tipo [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm update-config-MyConfig.  
  
### <a name="to-edit-the-bam-portal-webconfig-file-to-change-the-bammanagementservice-and-queryservice-urls-to-point-to-the-nlb-server-name-note-this-procedure-is-not-necessary-for-hardware-based-nlb"></a>Para editar el archivo web.config del portal de BAM para cambiar el BAMmanagementService y las URL de QueryService para que apunten al nombre del servidor de NLB. Nota: Este procedimiento no es necesario para NLB basado en hardware.  
  
1.  Abra el archivo web.config mediante el Bloc de notas haciendo clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Bamportal\web y, a continuación, haga clic en **Aceptar**.  
  
2.  Modifique el nombre de equipo (machinename) y el nombre de puerto siguientes en las dos líneas que aparecen a continuación para que señalen al nombre del clúster:  
  
    ```  
    <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
    <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />   
    ```  
  
3.  Guarde el archivo. Para ello, haga clic en **archivo**y, a continuación, haga clic en **guardar** en la barra de menús del Bloc de notas.  
  
### <a name="to-configure-each-additional-computer-in-the-cluster"></a>Para configurar cada equipo adicional en el clúster  
  
1.  Copie el archivo web.config en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal en cada equipo adicional del clúster.  
  
    > [!NOTE]
    >  En los pasos siguientes todas las referencias a la **archivos de programa** carpeta será **archivos de programa (x86)** para equipos de 64 bits.  
  
    > [!IMPORTANT]
    >  En los pasos siguientes, cuando crea directorios virtuales, asegúrese de que no hayan valores idénticos a los de los tres directorios virtuales de BAM que creó la configuración de BizTalk Server en el primer equipo. Confirme las rutas de archivos, la versión de ASP.NET, los permisos de directorios y el grupo de aplicaciones.  Utilice la misma cuenta de servicio de dominio para ejecutar BAMAppPool en el equipo que está configurando que la que utilizó para configurar el primer equipo. Asegúrese de que BAMAppPool se ejecuta en todos los equipos. Hay dos archivos web.config que debe configurar.  
    >   
    >  Además del archivo web.config de [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal, debe copiar el archivo web.config en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService y [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService en las mismas carpetas de este sistema.  
  
2.  Únicamente para NLB basado en hardware, modifique el siguiente nombre de equipo (machinename) y el nombre de puerto de las dos líneas siguientes para que apunten al nombre del clúster:  
  
    ```  
    <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
    <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />  
    ```  
  
3.  Cree un grupo de aplicaciones denominado BAMAppPool.  
  
    > [!NOTE]
    >  La ruta de directorio para los directorios virtuales debería ser %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, y %InstallationFolder%/BamPortal/BAMQueryService.  
  
4.  Cree un directorio virtual en el sitio Web predeterminado denominado BAM.  
  
5.  Cambie el grupo de aplicaciones del directorio virtual de BAM a BAMAppPool.  
  
    > [!NOTE]
    >  La ruta de directorio para los directorios virtuales debería ser %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService y %InstallationFolder%/BamPortal/BAMQueryService.  
  
6.  Cree un directorio virtual denominado BAMManagementService en BAM.  
  
7.  Cambie el grupo de aplicaciones de BAMManagementService a BAMAppPool.  
  
    > [!NOTE]
    >  La ruta de directorio para los directorios virtuales debería ser %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, y %InstallationFolder%/BamPortal/BAMQueryService.  
  
8.  Cree un directorio virtual denominado BAMQueryService en BAM.  
  
9. Cambie el grupo de aplicaciones de BAMQueryService a BAMAppPool.  
  
10. Utilice el INETMGR, ubicado en el directorio virtual ficha ASP NET de propiedades, para cambiar la versión para BAM, BAMMANAGEMENTSERVICE y BAMQUERYSERVICE configurar la versión de las aplicaciones a .NET Framework 4.  
  
11. Ejecute aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password.  Cuenta de servicio que se indica es la cuenta de usuario del servicio Web de administración de BAM.  
  
    > [!CAUTION]
    >  Portal de BAM *sólo* se ejecuta en modo de 32 bits. Si se instala IIS en un equipo de 64 bits, ASP.NET 2.0 debe estar habilitado en el modo de 32 bits. Para ello, abra el Administrador de IIS, abra **grupo de aplicaciones**, seleccione el grupo de aplicaciones (BAMAppPool) y, a continuación, haga clic en **configuración avanzada**. En **Habilitar aplicaciones de 32 bits**, seleccione **True**.  
    >   
    >  [Planeación del Portal de BAM](../core/planning-for-the-bam-portal.md) incluyen los requisitos adicionales.  
  
12. Configure la lectura ACL para el usuario AppPool en WebServices al ejecutar SubInACL, una herramienta de línea de comandos que permite a los administradores obtener información de seguridad sobre archivos, claves de Registro y servicios, así como transferir información de usuario a usuario, de grupo local o global a grupo, y de dominio a dominio.  
  
13. Descargue SubInAcl desde [http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990).  
  
14. Abra un símbolo del sistema. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
15. Escriba lo siguiente en el símbolo del sistema: subinacl.exe /subkeyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices" "/ conceder = servicio de red = R"  
  
    > [!NOTE]
    >  El propósito de este comando es conceder acceso de lectura al usuario de grupo de aplicaciones de BAM a la clave del registro SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity. Este ejemplo utiliza el servicio de red ya que es el servicio predeterminado que utiliza IIS para el grupo de aplicaciones. Si no utiliza los valores predeterminados de IIS, debería sustituir al usuario del grupo de aplicaciones que utiliza la implementación.  
  
16. Escriba lo siguiente en el símbolo del sistema: subinacl.exe /keyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3. 0" "/ conceder =\<BAM WebService Account >"  
  
    > [!NOTE]
    >  El objetivo de este comando es conceder a la cuenta de usuario del servicio Web de administración de BAM acceso de lectura a la clave del Registro SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity.  
  
17. Compruebe que la identidad del grupo de aplicaciones bajo el que se ejecuta el servicio web BAMManagement tiene acceso de lectura para la clave ASPNET_SETREG.  
  
18. Utilice la herramienta de administrador de Administración de equipos para agregar al usuario de servicio Web de administración de BAM y a la cuenta de usuario de grupo de aplicaciones de BAM al grupo de proceso de trabajo de IIS (IIS_WPG) y al grupo de servicios (STS_WPG) de SharePoint.  
  
19. Establecer los permisos en las carpetas temporales de ASP.NET para el grupo de aplicaciones y usuarios del servicio Web: c:\windows\system32\cacls "%windir%\Microsoft.NET\Framework\ v2.0. \<número mínimo de versión > \Temporary ASP.NET Files "/T /E /G \<BAM WebService Account >: F  
  
    > [!NOTE]
    >  Concede acceso tanto a la cuenta de usuario de servicio Web de administración de BAM como a la cuenta de usuario de grupo de aplicaciones de BAM.  
  
## <a name="see-also"></a>Vea también  
 [Administración del Portal BAM](../core/managing-the-bam-portal.md)