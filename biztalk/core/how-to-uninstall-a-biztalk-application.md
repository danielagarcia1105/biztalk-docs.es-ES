---
title: Cómo desinstalar una aplicación de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], uninstalling
- applications, uninstalling
- uninstalling, applications
- undeploying, uninstalling
ms.assetid: ab721c6e-194e-4b8a-bfd1-d0139d284373
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cba0c5f4ea8340612bb42c4a15257acd449848d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256844"
---
# <a name="how-to-uninstall-a-biztalk-application"></a>Cómo desinstalar una aplicación de BizTalk
En este tema se describe cómo usar el panel de control Agregar o quitar programas o la línea de comandos BTSTask para desinstalar una aplicación de BizTalk. Estos son los únicos métodos admitidos para desinstalar una aplicación. Si instaló múltiples archivos .msi para esta aplicación, por ejemplo para actualizarla, haga doble clic en el archivo .msi o puede que msiexec no desinstale completamente la aplicación; por consiguiente no son métodos de desinstalación admitidos.  
  
> [!CAUTION]
>  Desinstalar una aplicación de BizTalk mientras se está ejecutando puede producir errores en la aplicación. Para evitar este problema, como práctica recomendada, se recomienda que compruebe existe no son ninguna ejecución instancias de servicio de la aplicación, como se describe en [cómo buscar todas las instancias de servicio](../core/how-to-search-for-all-service-instances.md). Si es necesario, puede detener la aplicación mediante la opción detención completa para detener todas las instancias en ejecución, como se describe en [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md). Tenga en cuenta que al hacerlo los mensajes en curso no se completarán.  
  
 Al desinstalar la aplicación, debería incluirse en el archivo .msi un script previo o posterior al procesamiento para eliminar todos los archivos y la configuración asociados con la aplicación. Si no se ha incluido un script previo o posterior al procesamiento, los procedimientos que se explican en este tema eliminarán los archivos y la configuración de la aplicación del sistema de archivos local, con las siguientes excepciones:  
  
-   Si la aplicación incluye un directorio virtual, tanto éste como sus archivos se eliminarán, a no ser que los archivos se agregaran al directorio virtual después de que se instalara la aplicación. En este caso, el directorio virtual y los archivos agregados no se eliminan. Si desea eliminar el directorio virtual y los archivos agregados, deberá hacerlo explícitamente.  
  
-   Las secuencias de comandos previas y posteriores al procesamiento se eliminan, pero los archivos que tales secuencias agregaron durante la instalación o desinstalación no se eliminarán, ni tampoco deshacer las acciones de las secuencias de comandos. Si desea eliminar archivos agregados por las secuencias de comandos o deshacer sus acciones, deberá hacerlo explícitamente.  
  
    > [!NOTE]
    >  Sólo se ejecutarán durante la desinstalación aquellas secuencias de comandos previas y posteriores al procesamiento que tengan especificada una ubicación de destino en sus propiedades de implementación cuando se importe la aplicación. Para obtener más información, consulte [cómo agregar un prefijo o procesamiento posterior a la secuencia de comandos a una aplicación](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).  
  
-   Los certificados nunca se eliminan al desinstalar una aplicación de BizTalk. Si desea eliminar un certificado, deberá hacerlo explícitamente. Además, los componentes no se eliminan del Registro de Windows ni los ensamblados de BizTalk se eliminan de la caché de ensamblados global (GAC). Si desea eliminarlos, deberá hacerlo explícitamente. Para obtener más información, consulte [cómo quitar otros archivos y configuración para una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).  
  
 Si cancela la operación de desinstalación antes de que se complete, BizTalk Server deshará la desinstalación, excepto las acciones que las secuencias de comandos previas o posteriores al procesamiento realizaron antes de que se cancelara la operación. Para restaurar la aplicación al estado que tenía antes de iniciar la desinstalación, haga doble clic en el archivo .msi y reinstale la aplicación. Si se han instalado varios archivos .msi para esta aplicación, debería hacer doble clic en cada uno de ellos para reinstalar la aplicación en el orden en que los archivos .msi se instalaron originalmente.  
  
 Para obtener más información acerca de los scripts posteriores al procesamiento, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).  
  
> [!NOTE]
>  Para anular por completo la implementación de una aplicación de BizTalk, también debe eliminar, desde el grupo de BizTalk, tal y como se describe en [cómo eliminar una aplicación de BizTalk del grupo de BizTalk](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los procedimientos explicados en este tema, deberá iniciar sesión con permisos adecuados. Para obtener más información, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-uninstall-a-biztalk-application"></a>Para desinstalar una aplicación de BizTalk  
  
#### <a name="using-uninstall-or-change-a-program"></a>Mediante la opción Desinstalar o cambiar un programa  
  
1.  En el equipo en el que se ejecuta la aplicación, haga clic en **iniciar**, haga clic en **el Panel de Control**y, a continuación, haga doble clic en **programas y características**.  
  
2.  En **desinstalar o cambiar un programa** página, haga clic en la aplicación de BizTalk para quitar y, a continuación, haga clic en **desinstalar**.  
  
     Windows Installer eliminará la aplicación especificada.  
  
3.  Si la aplicación se está ejecutando en varios equipos, repita los pasos anteriores en cada equipo.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo el valor según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask UninstallApp** [**/ApplicationName:***valor*]  
  
     Ejemplo:  
  
     **BTSTask UninstallApp /ApplicationName:MyApplication**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk que se va a desinstalar. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
  
## <a name="see-also"></a>Vea también  
 [Anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md)   
 [Comando UninstallApp](../core/uninstallapp-command.md)