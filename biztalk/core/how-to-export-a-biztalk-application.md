---
title: "Cómo exportar una aplicación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, exporting
- exporting, warnings
- exporting, applications
- applications, exporting
- applications, security
- applications, warnings
- exporting, security
ms.assetid: a1d6ffca-3d29-44c7-a811-6cf8b42e23f6
caps.latest.revision: "50"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f1b2becead061ec1bad089bd5ceddbbc076d83f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-a-biztalk-application"></a>Cómo exportar una aplicación de BizTalk
En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o la línea de comandos para exportar una aplicación. Exportar una aplicación de BizTalk genera un archivo (.msi) de Windows Installer que contiene la aplicación y los artefactos seleccionados para que se exportaran. La opción predeterminada es seleccionar todos los artefactos de la aplicación, pero puede seleccionar un subconjunto de ellos. A continuación, puede importar el archivo .msi a otro grupo de BizTalk para agregar los artefactos a una aplicación existente de un grupo nuevo, actualizar los artefactos de una aplicación existente o crear una aplicación nueva en el grupo que contiene los artefactos que se van a importar. Para obtener más información, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). Utiliza también el archivo .msi para instalar la aplicación en los equipos que vayan a ejecutarla, tal y como se describe en [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md). Si la aplicación incluye artefactos basados archivos, debe instalarla antes de que pueda funcionar.  
  
 Al exportar una aplicación, tenga en cuenta que los siguientes puntos son importantes:  
  
-   **Los enlaces importados sobrescriben automáticamente los enlaces existentes.** Si no desea que los enlaces de la aplicación que se está exportando sobrescriban los enlaces de la aplicación en la que se está importando un archivo .msi, no seleccione el archivo de enlace como un recurso que es preciso exportar. Al importar un archivo .msi que contenga un archivo de enlace en una aplicación existente, los enlaces importados sobrescribirán los existentes, incluso si no ha activado la opción de sobrescribir artefactos existentes..  
  
-   **Un usuario puede estar realizando cambios en un artefacto mientras exporta la aplicación.** Si el usuario modifica un artefacto basado en bases de datos, tal como un directorio virtual, un certificado o una directiva, mientras está en curso una operación de exportación, los cambios no se reflejarán en el archivo .msi exportado. Por lo tanto, se recomienda programar las operaciones de exportación durante horas cuando sea probable que los usuarios no realicen cambios en estos artefactos.  
  
-   **Se mostrará el error incorrecto al instalar un archivo .msi en Windows Vista**. Al instalar un paquete .msi exportado mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], recibirá el siguiente mensaje de error "el instalador ha encontrado un error inesperado al instalar este paquete. Esto puede deberse a un problema del paquete. El código de error es 2869". Para corregir este error, primero importe el paquete .msi mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y luego vuelva a exportar e instalar el paquete.  
  
-   **La aplicación puede tener dependencias en otra aplicación.** Esto puede afectar a cómo implemente la aplicación. Para obtener más información, consulte [dependencias e implementación de aplicaciones](../core/dependencies-and-application-deployment.md).  
  
-   **Puede modificar el directorio de destino de los recursos en la aplicación antes de exportar.** Si desea cambiar la ubicación de destino, expanda el nodo de recursos de la aplicación, haga clic en el recurso que desea cambiar y, a continuación, elija **modificar**. En el cuadro de diálogo Modificar recursos, escriba la nueva ubicación en **ubicación de destino**.  
  
-   **Se producirá un error en la exportación si la aplicación contiene una directiva que se ha quitado de la base de datos de motor de reglas.** Cuando se quita una directiva de la base de datos del motor de reglas mediante el Asistente para implementar el motor de reglas, ésta se mostrará en la consola de administración en estado “No publicada” y no se podrá exportar la aplicación. Para obtener más información sobre el Asistente para la implementación del motor de reglas, consulte [cómo implementar y anular la implementación de directivas y vocabularios](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).  
  
> [!IMPORTANT]
>  El archivo .msi puede contener datos confidenciales. Asegúrese de seguir los pasos necesarios para garantizar que el archivo es seguro. Para obtener más información, consulte [seguridad y Windows Installer](../core/security-and-windows-installer.md).  
>   
>  Las contraseñas se quitan de los enlaces de aplicación durante la exportación de la aplicación. Después de instalar la aplicación desde el archivo .msi, deberá volver a configurar las contraseñas para que funcione la aplicación. No obstante, las contraseñas no se quitan de ningún archivo de enlace que se haya agregado a la aplicación.  
>   
>  Si la aplicación incluye un sitio Web o una orquestación que utilice un servicio Web, tenga en cuenta que la configuración de seguridad del directorio virtual es la que está activa cuando el archivo .msi se genera durante la exportación de la aplicación. Si va a implementar una aplicación en un entorno de producción, a continuación, antes de exportar la aplicación, debe comprobar que la configuración satisface sus requisitos de seguridad. Si el directorio virtual ya existe en el equipo host, su configuración de seguridad no se sobrescribe, pero se le agregan los archivos de la aplicación. Debería comprobar la configuración de seguridad después de importar la aplicación.  
>   
>  Todas las listas de control de acceso discrecional (DACL) se quitan de los archivos y carpetas cuando se exporta la aplicación. Tras instalar una aplicación, debe volver a definir la configuración de seguridad de los archivos y carpetas, incluyendo la de los directorios virtuales.  
  
> [!NOTE]
>  Si se produce un error en la operación de exportación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] elimina todos los archivos temporales junto con el archivo .msi, si se ha creado uno.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los procedimientos de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md). Asimismo, debe estar instalado el motor de reglas de negocios. Para obtener más información, consulte [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).  
  
## <a name="to-export-an-application"></a>Para exportar a una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk y, a continuación, expanda **aplicaciones**.  
  
3.  Haga clic en la aplicación que desea exportar, seleccione **exportar**y, a continuación, haga clic en **archivo MSI**.  
  
4.  En la página de bienvenida para el Asistente para exportar archivos MSI, haga clic en **siguiente**.  
  
5.  En la página Seleccionar recursos, seleccione los artefactos que se va a exportar al archivo .msi y, a continuación, haga clic en **siguiente**.  
  
6.  Si se le pide, en la página Especificar Hosts de ISS, escriba el nombre del servidor del equipo que hospeda el directorio virtual que desea incluir y, a continuación, haga clic en **siguiente**. Se le pedirá que especifique el servidor sólo si el directorio virtual no se ha agregado previamente a la base de datos de administración de BizTalk, como cuando se agregó a la aplicación o se importó a una aplicación.  
  
7.  En la página dependencias, revise las dependencias de la aplicación y, a continuación, haga clic en **siguiente**.  
  
8.  En la página de destino, en **nombre de la aplicación de destino**, escriba el nombre de la aplicación.  
  
9. En **archivo MSI para generar**, escriba la ruta de acceso completa para el archivo .msi y, a continuación, haga clic en **exportar**. Ejemplo: C:\MSI\Errorhandling.msi  
  
    > [!NOTE]
    >  Se recomienda almacenar los archivos .msi en una carpeta segura.  
  
10. En la página Resumen, tome nota de la ubicación del archivo de registro para esta operación y, a continuación, haga clic en **finalizar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **ExportApp de BTSTask** [**/ApplicationName:***valor*] **/paquete:***valor* [**ResourceSpec :***valor* [**/Server:***valor*] [**/Database:***valor*]  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
     Ejemplo:  
  
     **BTSTask ExportApp /ApplicationName:MyApplication /Package:C:/MSI/MyApplication.msi /ResourceSpec: "C:\My Files\ResourceSpec.xml" /Server:MySQLServer /Database:BizTalkMgmtDb**  
  
     Los artefactos especificados se exportan al archivo .msi en la ubicación especificada.  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk que se va a exportar. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk. Si el nombre incluye espacios, debe ir entre comillas dobles (").|  
    |**/ Paquete**|Ruta de acceso del archivo .msi que se va a crear, incluyendo el nombre de archivo.|  
    |**/ ResourceSpec**|Ruta de acceso del archivo XML de especificación del recurso, incluido el nombre de archivo. Puede especificar qué artefactos se van a exportar, edite el archivo XML de especificación de recursos, que se crea cuando se ejecuta el ListApp comando con el parámetro ResourceSpec, como se describe en [comando ListApp](../core/listapp-command.md). Debe editar manualmente este archivo para agregar el nombre del servidor de host de Servicios de Internet Information Services (IIS) para el directorio virtual que desea exportar si el servidor Web no se encuentra en un equipo remoto.|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Exportar aplicaciones de BizTalk, los enlaces y directivas](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [Comando ExportApp](../core/exportapp-command.md)