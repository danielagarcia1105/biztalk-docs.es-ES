---
title: "Plantilla (ejemplo de implementación de aplicaciones) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, examples
- scripts, deploying
- deploying, scripts
- examples, deploying
ms.assetid: 7e77ff8e-b2bc-4d38-b5fd-329d6d54221f
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 315a685f0e289d60e3db9dfbe77bae5a7e2b19f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="template-application-deployment-sample"></a>Plantilla (ejemplo de implementación de aplicaciones)
En este tema se describe cómo usar el ejemplo de la plantilla para la implementación de aplicaciones.  
  
 Puede crear y utilizar dos tipos de scripts de implementación para personalizar la implementación de la aplicación de BizTalk: las secuencias de comandos de procesamiento previo y posterior al procesamiento de las secuencias de comandos. Las secuencias de comandos previas al procesamiento se invocan antes de la importación e instalación de la aplicación y después de finalizar el proceso de desinstalación. Las secuencias de comandos posteriores se invocan después de la importación e instalación de la aplicación y antes de finalizar el proceso de desinstalación.  
  
 Puede escribir secuencias de comandos previas y posteriores al procesamiento para que estén invocadas en cada una de estas operaciones. También puede configurar las secuencias de comandos para que sólo se ejecuten después de una operación. Para obtener más información sobre cómo escribir secuencias de comandos, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).  
  
 En este tema se muestra cómo escribir e implementar una secuencia de comandos para que sólo sea invocada antes o después de una operación. Para ello, escriba una secuencia de comandos que compruebe los valores de tres variables de entorno para determinar la operación en el contexto en que se llama. En función de este contexto, la secuencia de comandos continúa o no con la ejecución.  
  
 En este tema se describe cómo realizar los siguientes pasos:  
  
1.  Establezca la ubicación del archivo de registro para poder generar un archivo de registro de las operaciones de secuencias de comandos.  
  
    > [!NOTE]
    >  Se recomienda generar siempre un archivo de registro para poder verificar las operaciones de secuencias de comandos y poder resolver cualquier tipo de problema.  
  
2.  Cree una nueva aplicación de BizTalk y agréguele las secuencias de comandos de ejemplo.  
  
3.  Exporte un archivo .msi que contiene los artefactos de la aplicación.  
  
4.  Elimine la aplicación del grupo de BizTalk para poder importar de nuevo el archivo .msi al mismo grupo e instalarlo desde el archivo .msi.  
  
5.  Importe la aplicación y compruebe el archivo de registro para ver si se ha registrado la operación de importación.  
  
6.  Instale la aplicación y compruebe el archivo de registro para ver si el registro de instalación se anexó al archivo de registro.  
  
7.  Vea los archivos de registro y observe qué operaciones realizaron las secuencias de comandos y cuándo se realizaron.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Los dos archivos .bat proporcionados para este ejemplo contienen los valores de las variables de entorno para la importación, instalación y desinstalación. SamplePreProcessing.bat contiene variables para una secuencia de comandos previa al procesamiento. SamplePostProcessing.bat contiene variables para una secuencia de comandos posterior al procesamiento. Los archivos también muestran cómo registrar los mensajes de las secuencias de comandos. Puede copiar las secciones relevantes de estos archivos en las secuencias de comandos.  
  
> [!IMPORTANT]
>  Algunos de los comentarios de los archivos de secuencias de comandos no son correctos, como por ejemplo:  
>   
>  En SamplePreProcessing.bat, el comentario de la secuencia, “Desinstale previamente parte de la secuencia de comandos llamada a una aplicación existente” debería ser “Desinstale posteriormente parte de la secuencia de comandos llamada a una aplicación existente”.  
>   
>  En SamplePreProcessing.bat, el comentario de la secuencia, “Desinstale posteriormente parte de la secuencia de comandos llamada a una aplicación existente” debería ser “Desinstale previamente parte de desinstalación anterior de la secuencia de comandos llamada a una aplicación existente”.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Este ejemplo se encuentra en la carpeta de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en la ruta de acceso siguiente:  
  
 *\<Ejemplos de ruta de acceso\>*\applicationdeployment\template  
  
 Como se ha mencionado anteriormente, el ejemplo incluye dos archivos:  
  
-   SamplePreProcessing.bat  
  
-   SamplePostProcessing.bat  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Para ejecutar el ejemplo, siga estos pasos.  
  
### <a name="to-set-the-logging-location"></a>Para establecer la ubicación de registro  
  
-   Abra los dos ejemplos de secuencias de comandos y modifique la variable LogFile para indicar la ubicación donde se escribirán los archivos de registro. Debe proporcionar la ruta completa incluyendo el nombre del archivo. Si la ruta incluye espacios, debe ponerla entre comillas dobles (").  
  
     Ejemplo:  
  
     conjunto LogFile = "*\<ruta de ejemplos\>*\ApplicationDeployment\Templates\SampleLogOut.txt"  
  
### <a name="to-create-a-new-application"></a>Para crear una aplicación nueva  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y el grupo de BizTalk.  
  
3.  Haga clic en **aplicaciones** y, a continuación, haga clic en **nuevo**.  
  
4.  En **nombre de la aplicación**, tipo `SamplesTemplate`y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-add-the-scripts-to-the-application"></a>Para agregar las secuencias de comandos a la aplicación  
  
1.  Expanda la carpeta de la aplicación SamplesTemplate que acaba de crear y haga clic en **recursos** en el panel izquierdo.  
  
2.  Seleccione **agregar** y haga clic en **secuencias de comandos de preprocesamiento**.  
  
3.  Haga clic en **agregar** y desplácese a SamplePreProcessing.bat.  
  
4.  Seleccione el archivo y haga clic en **abiertos**.  
  
5.  En **tipo de archivo**, haga clic en **System.BizTalk:PreprocessingScript**y, a continuación, haga clic en **Aceptar**.  
  
     SamplesPreProcessing.bat se agrega a la aplicación y se muestra en la carpeta Recursos de la aplicación.  
  
6.  Haga clic en recursos de nuevo, seleccione **agregar**y, a continuación, haga clic en **secuencias de comandos posteriores al procesamiento**.  
  
7.  Haga clic en **agregar** y desplácese a SamplePostProcessing.bat.  
  
8.  Seleccione el archivo y haga clic en **abiertos**.  
  
9. En **tipo de archivo**, haga clic en **System.BizTalk:PostprocessingScript**y, a continuación, haga clic en **Aceptar**.  
  
     SamplesPostProcessing.bat se agregará a la aplicación y se mostrará en la carpeta Recursos de la aplicación.  
  
### <a name="to-export-an-msi-file"></a>Para exportar un archivo .msi  
  
1.  En la consola de administración de BizTalk Server, haga clic en la aplicación SamplesTemplate, seleccione **exportar**y, a continuación, haga clic en **archivo MSI**.  
  
2.  En la página Asistente para la página del Asistente para exportación, haga clic en **siguiente**.  
  
3.  En la página Seleccionar recursos, haga clic en **siguiente**.  
  
4.  En la página Especificar Hosts de IIS, haga clic en **siguiente**.  
  
5.  En la página dependencias, haga clic en **siguiente**.  
  
6.  En la página de destino, en **nombre de la aplicación de destino**, escriba el nombre de la aplicación.  
  
7.  En **archivo MSI para generar**, escriba la ruta de acceso completa del archivo MSI y, a continuación, haga clic en **exportar**. Ejemplo: C:\MSI\SamplesTemplate.msi  
  
8.  En la página Resumen, haga clic en **finalizar**.  
  
### <a name="delete-the-application"></a>Eliminar la aplicación  
  
-   En la consola de administración de BizTalk Server, haga clic en la aplicación SamplesTemplate y, a continuación, haga clic en **eliminar**.  
  
### <a name="to-import-the-msi-file"></a>Para importar el archivo .msi  
  
1.  En la consola de administración de BizTalk Server, haga clic en **aplicaciones**, seleccione **importación**y, a continuación, haga clic en **archivo MSI**.  
  
2.  En la página Asistente para la página del Asistente para la importación, en **archivo MSI para importar**, escriba la ruta de acceso del archivo .msi que exportó anteriormente y, a continuación, haga clic en **siguiente**. Si es necesario, también puede examinar para encontrar el archivo MSI haciendo clic en el **(...)** botón.  
  
3.  En la página Configuración de la aplicación, en la **nombre de la aplicación** lista desplegable, seleccione el nombre de la aplicación.  
  
4.  En **aplicaciones disponibles para agregar referencias a**, seleccione las aplicaciones que se va a agregar referencias, si los hay y, a continuación, haga clic en **siguiente**.  
  
5.  En la página de configuración del entorno de destino de aplicación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  No es necesario especificar un entorno de destino para los fines de este ejemplo. Para obtener información general acerca de esta característica, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md). Para obtener instrucciones sobre cómo agregar archivos de enlace, consulte [cómo agregar un archivo de enlace a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md).  
  
6.  En la página Importar resumen, confirme que la información de resumen es correcta y, a continuación, haga clic en **importación**.  
  
7.  En la página de resultados, haga clic en **finalizar**.  
  
8.  Abra el archivo de registro que se creó cuando se ejecutaron las secuencias de comandos y verifique que se registró la operación de importación.  
  
### <a name="to-install-the-application"></a>Para instalar la aplicación  
  
1.  Haga doble clic en el archivo .msi y ejecute el Asistente para instalación.  
  
2.  Abra el archivo de registro y verifique que la operación de instalación se agregó a la información de registro.  
  
### <a name="to-verify-that-the-scripts-functioned-correctly"></a>Para verificar que las secuencias funcionaron correctamente  
  
-   Abra los archivos de registro y verifique que se ejecutaron durante las operaciones especificadas.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [Implementación de aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)