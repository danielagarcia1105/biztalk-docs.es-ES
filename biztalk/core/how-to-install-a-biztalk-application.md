---
title: Cómo instalar una aplicación de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, requirements
- installing, applications
- installing, warnings
- applications, installing
ms.assetid: 99ee0b1a-d46a-4fb6-802b-6827dc740418
caps.latest.revision: 56
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc3d1d6d8fdbfcc168446883e2b65a7d8ed0351
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "26010541"
---
# <a name="how-to-install-a-biztalk-application"></a>Cómo instalar una aplicación de BizTalk
Este tema describe cómo instalar una aplicación en un equipo local al hacer doble clic en el archivo (.msi) de Windows Installer para la aplicación de la interfaz de Windows o al ejecutar msiexec desde la línea de comandos. También puede iniciar el Asistente para la instalación como último paso del Asistente para importación, tal y como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
> [!CAUTION]
>  Si esta aplicación ya se ha instalado en este equipo, se le ofrecerá la posibilidad de reparar la aplicación. Sólo se admite la reparación cuando se ha instalado un único .msi para esta aplicación. Si ha instalado más de un .msi en este equipo para esta aplicación, no debería seleccionar esta opción. Esto se debe a que si selecciona Reparar, se desharán los cambios realizados por los archivos .msi que se instalaron posteriormente a este archivo .msi, lo que puede producir un error de funcionamiento de la aplicación.  
  
 Antes de poner en funcionamiento una aplicación debe instalarla en los equipos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que la ejecutarán. Al instalar una aplicación, se colocan sus recursos en el sistema de archivos local. En función de la aplicación, sus contenidos y su configuración, la instalación también puede realizar lo siguiente:  
  
-   Agregar ensamblados a la caché de ensamblados global (GAC)  
  
-   Instalar certificados y directorios virtuales  
  
-   Agregar componentes al Registro de Windows  
  
-   Ejecutar secuencias de comandos previas y posteriores al procesamiento, si están presentes en el archivo .msi.  
  
 Para obtener información general, vea [qué ocurre con los artefactos durante la instalación y desinstalación](../core/what-happens-to-artifacts-during-installation-and-uninstallation.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos de este tema, deberá iniciar sesión con una cuenta que tenga permisos de escritura en el sistema de archivos local. En función de los elementos que incluye la aplicación, también necesita permisos de escritura en el Registro de Windows, GAC, almacén de certificados y en los Servicios de Internet Information. La cuenta de administradores del equipo local tiene estos permisos. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="considerations-for-installing-an-application"></a>Consideraciones para instalar aplicaciones  
 Al instalar una aplicación, es preciso tener en cuenta lo siguiente:  
  
-   **También debe instalar las aplicaciones en el que esta aplicación tiene una dependencia.** Cuando instale una aplicación que tenga dependencia de un artefacto, como de un ensamblado de BizTalk, que está contenido en otra aplicación, también es necesario instalar la aplicación que contiene el artefacto. Debe hacerlo antes de poder ejecutar la aplicación. Por ejemplo, si una aplicación depende de un ensamblado de la aplicación B, también debe instalar aplicación B. A continuación, puede instalar a aplicación. Para obtener información general, vea [dependencias e implementación de aplicaciones](../core/dependencies-and-application-deployment.md).  
  
-   **Se debe detener una aplicación que va a actualizar.** Si realiza la instalación para actualizar el artefacto en la aplicación, no es necesario detener la aplicación a menos que la actualización incluya uno o más ensamblados que tengan la misma extensión que los ensamblados existentes. En este caso, debe detener la aplicación antes de instalar la actualización. Sin embargo, se recomienda detener la aplicación en todos los casos a menos que sepa que la actualización no interferirá en la aplicación cuando se ejecute. Para obtener más información, consulte [actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md).  
  
-   **Al instalar varios archivos .msi para la misma aplicación, hay realizada solo una entrada en Agregar o quitar programas.** Puede hacer esto para actualizar una aplicación existente, por ejemplo. Puede usar la opción Agregar o quitar programas (en el Panel de control) para desinstalar la aplicación por completo, incluyendo todos los elementos actualizados. Tenga en cuenta que no se admite desinstalar una aplicación haciendo doble clic en el archivo .msi o mediante msiexec. Para obtener más información, consulte [cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md).  
  
-   **Certificados deben estar presentes en todos los equipos que hospedan los puertos de envío antes de que una aplicación puede ejecutarse.** El almacén de certificados Otras personas contiene los certificados que utilizan los puertos de envío.  
  
-   **Puede descomponer los artefactos de la aplicación en varios archivos .msi para la instalación.** No es necesario instalar todos los artefactos de la aplicación en cada equipo que ejecutará la aplicación. En su lugar, puede exportar subconjuntos de los artefactos de la aplicación en varios archivos .msi que se van a instalar en distintos equipos. Para obtener instrucciones, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
-   **Si el archivo .msi de aplicación incluye un directorio virtual, Internet Information Services (IIS) se debe ejecutar en el equipo local.** De no ser así, se producirá un error en la instalación  
  
-   **Si la aplicación incluye un directorio virtual con el mismo nombre que una que ya exista en el equipo local, los recursos de la aplicación se agregan a él.** De lo contrario, se crea un directorio virtual. Se sobrescribirán todos los archivos que tengan el mismo nombre que los archivos agregados. Asimismo, la configuración de seguridad para el directorio virtual existente no cambia y debería comprobar que es lo suficiente segura.  
  
-   **Crear grupos de aplicaciones para los directorios virtuales antes de instalar una aplicación.** Si la aplicación incluye un directorio virtual y el grupo de aplicaciones no existe en IIS, debe crear de forma manual el grupo de aplicaciones antes de la instalación. De esta forma, el directorio virtual se enlazará al grupo de aplicaciones durante la instalación. Si no crea la aplicación, el directorio virtual se enlazará al grupo de aplicaciones predeterminado durante la instalación.  
  
-   **Asegúrese de que BTSHttpReceive.dll está registrado como asignación de controlador con servicios de Internet Information Server (IIS) 7.0.** Debe hacerlo si la aplicación incluye un directorio virtual en el orden de ubicación para que funcione de recepción de HTTP.  
  
-   **Puede encontrar problemas al instalar una aplicación que incluya artefactos de 64 bits en un equipo de 32 bits.** Para obtener más información, consulte [cómo agregar un artefacto de 64 bits a una aplicación](../core/how-to-add-a-64-bit-artifact-to-an-application.md).  
  
-   **Se pueden producir problemas si la longitud del directorio de destino supera los 260 caracteres.** Si el número de caracteres del directorio de destino que se ha especificado durante la instalación de un paquete MSI supera los 260 caracteres, se producirá un error en la instalación. Para solucionar este problema, asegúrese de que el número de caracteres especificado para el directorio de destino no supera los 260 caracteres.  
  
-   **No se debe cambiar la ubicación de una carpeta de instalación.** Tras instalar la aplicación, no debería cambiar la ubicación de la carpeta de instalación o de los archivos que la contienen. Si lo hace e intenta quitar (desinstalar) la aplicación, se producirá un error en la operación de eliminación. En concreto, la carpeta de instalación de la aplicación contiene archivos generados por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que son necesarios para realizar la eliminación. No debe cambiar el nombre, mover o quitar estos archivos. Los archivos son:  
  
    -   ApplicationDefinition.adf  
  
    -   Microsoft.BizTalk.CustomInstaller.dll  
  
    -   Microsoft.BizTalk.CustomInstaller.InstallState  
  
> [!NOTE]
>  Puede cancelar la operación de instalación antes de que se complete, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deshará la instalación, salvo para las acciones que realicen las secuencias de comandos posteriores o previas al procesamiento antes de que se cancelara la operación.  
  
> [!IMPORTANT]
>  Antes de instalar aplicaciones, asegúrese de que ha recibido el archivo .msi de una fuente de confianza. Un usuario malintencionado puede incluir un código en el archivo .msi que tenga un efecto no deseado en el sistema o en la red.  Para obtener más información, consulte [seguridad y Windows Installer](../core/security-and-windows-installer.md).  
>   
>  Si la aplicación incluye un sitio Web o una orquestación que utilice un servicio Web, tenga en cuenta que la configuración de seguridad del directorio virtual es la que está activa cuando se genera el archivo .msi durante la exportación de la aplicación, salvo en el caso de directorios virtuales existentes, ya que se utiliza la configuración existente. Tras instalar la aplicación, debe comprobar que la configuración satisface sus requisitos de seguridad.  
>   
>  Listas de control de acceso de Alldiscretionary (DACL) se quitan de los archivos y carpetas cuando se exporta la aplicación. Tras instalar una aplicación en una instancia de host, debe volver a configurar la configuración de seguridad de los archivos y carpetas, incluyendo la de los directorios virtuales.  
  
-   **Puede que necesite cambiar la ruta de acceso Local: designación de un directorio virtual que se hace referencia a un elemento HTTP la ubicación de recepción después de crearlo en el equipo de destino.**  
  
     Cuando el directorio virtual se crea en el equipo de destino, apuntará a uno de los siguientes directorios físicos:  
  
     \<*unidad de instalación*\>\Program BizTalk Server\HttpReceive  
  
     \- **or** –  
  
     \<*unidad de instalación*\>\Program archivos (x86) \Microsoft BizTalk Server\HttpReceive  
  
     Si el archivo BTSHTTPReceive.dll de la extensión ISAPI de recepción HTTP de BizTalk no se encuentra en el directorio especificado, o si el equipo de destino ejecuta un sistema operativo de 64 bits, tendrá que cambiar la ruta local: designación del directorio virtual con el que se apunta al directorio físico que contiene el archivo de extensión ISAPI de recepción HTTP de BizTalk. Por ejemplo, si el equipo de destino está ejecutando la versión de 64 bits de Windows Vista, a continuación, la ruta de acceso Local: designación del directorio virtual debe cambiarse a \<unidad de instalación\>\Program archivos (x86) \Microsoft BizTalk Server\ HttpReceive64.  
  
## <a name="to-install-a-biztalk-application"></a>Para instalar una aplicación de BizTalk  
  
#### <a name="using-the-windows-interface"></a>Utilización de la interfaz de Windows  
  
1.  Copie el archivo .msi para la aplicación en el equipo local.  
  
2.  Si va a volver a instalar o actualizar una aplicación de BizTalk existente y la nueva instalación incluye un ensamblado que tiene la misma versión que uno que ya existe en la aplicación, o interactúa con un artefacto que está actualizando, asegúrese de que el se detiene la aplicación haciendo clic en la carpeta de la aplicación y, a continuación, haga clic en **detener**.  
  
3.  En el Explorador de Windows, haga doble clic en el archivo .msi para iniciar el Asistente para instalación.  
  
4.  En el **seleccionar la carpeta de instalación** página **carpeta**, escriba la ruta de instalación completa para la aplicación de BizTalk. Ejemplo: C:\Archivos de programa\Generated by BizTalk\MyApplication.  
  
5.  Haga clic en **siguiente** cuatro veces y, a continuación, en la **instalación finalizada** página, haga clic en **cerrar**.  
  
6.  Si varios equipos ejecutarán la aplicación, repita los pasos anteriores en cada equipo.  
  
     Una vez que la aplicación está instalada en todos los equipos que vayan a ejecutarla y la aplicación se ha importado en el grupo de BizTalk, puede iniciar la aplicación desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] la consola de administración haciendo clic en la carpeta de la aplicación y haga clic en **Iniciar**. Para obtener instrucciones detalladas, consulte [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Copie el archivo .msi para la aplicación en el equipo local.  
  
2.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
3.  Desplácese a la ubicación en la que se almacena el archivo .msi.  
  
4.  Escriba el comando siguiente para instalar la aplicación, proporcionando los valores y parámetros apropiados, como se muestra en la tabla siguiente:  
  
    > [!IMPORTANT]
    >  Sólo se admiten los valores de msiexec que se muestran en la tabla siguiente.  
  
     **msiexec** [**/i**] *Package* [**/qn**] **TARGETDIR="***value***"**]  
  
     Ejemplo: **msiexec /i MyApplication.msi**  
  
    |Parámetro|Value|  
    |---------------|-----------|  
    |**/i**|Instala la aplicación.|  
    |*Paquete*|Nombre del archivo (.msi) de Windows Installer.|  
    |**/qn**|Efectúa la instalación sin mostrar una interfaz de usuario.|  
    |**TARGETDIR="** *value* **"**|Especifica la carpeta de instalación de la aplicación. El valor se ha configurado en la variable de entorno %BTAD_InstallDir%.<br /><br /> Ejemplo: TARGETDIR="C:\Archivos de programa\BizTalk Applications\My Application"|  
  
5.  Si varios equipos ejecutarán la aplicación, repita los pasos anteriores en cada equipo.  
  
     Una vez que la aplicación se instala en todos los equipos que vayan a ejecutarla, puede iniciar la aplicación desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración haciendo clic en la carpeta de la aplicación y haga clic en **iniciar**. Para obtener instrucciones detalladas, consulte [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Implementar aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)   
 [Cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md)