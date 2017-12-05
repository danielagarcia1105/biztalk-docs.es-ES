---
title: "CreateApp (ejemplo de implementación de aplicaciones) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, examples
- deploying, .msi file
- deploying, exporting
- .msi files, deploying
- examples, deploying
ms.assetid: 825627ee-21d0-4505-9df4-1dadc51335b6
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 842683d2eec04d77bad2b7726af0d687fae12884
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="createapp-application-deployment-sample"></a>CreateApp (ejemplo de implementación de aplicaciones)
En este tema se describe cómo usar el ejemplo CreateApp, que muestra cómo implementar o anular la implementación de una aplicación de BizTalk utilizando la herramienta de línea de comandos BTSTask. Puede usar secuencias de comandos como los que se incluyen en este ejemplo para automatizar el proceso de implementación nocturno y, así, implementar o anular la implementación de las aplicaciones de BizTalk.  
  
> [!IMPORTANT]
>  Debe escribir siempre las secuencias de comandos de implementación para que se ejecuten en modo silencioso. De lo contrario, los cuadros de diálogo indicarán que requieren la entrada de usuario. Como consecuencia, se detendrá el proceso de implementación hasta que se omita el cuadro de diálogo de forma manual, lo cual puede ocasionar que se cuelgue el proceso de importación.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El ejemplo incluye secuencias de comandos que automatizan las tareas de implementación de aplicaciones. Para realizar estas tareas, ejecute una secuencia de comandos que genere los archivos y el proyecto de BizTalk. A continuación, ejecute una secuencia de comandos que genere dos archivos .msi de la aplicación de BizTalk: un archivo .msi que contenga todos los artefactos de una aplicación y otro que solo contenga un ensamblado de la aplicación. Después, ejecute una secuencia de comandos que use un archivo .msi para importar una aplicación en un grupo de BizTalk e instale la aplicación en el equipo local. Durante la instalación, una secuencia de comandos previa al procesamiento incluida en la aplicación crea carpetas utilizadas por la aplicación y registra las acciones en un archivo. Por último, puede ejecutar una secuencia de comandos que elimina y desinstala la aplicación. Durante la desinstalación, una secuencia de comandos previa al procesamiento incluida en la aplicación elimina los archivos y las carpetas creadas en la instalación y, además, registra las acciones en un archivo.  
  
 A continuación, se muestran las secuencias de comandos incluidas en este ejemplo:  
  
-   **Build.bat.** Genera un archivo de clave y el proyecto en Visual Studio y, por otro lado, firma los archivos .dll.  
  
-   **CreateFullAndPartialMSI.bat.** Realiza las siguientes acciones en el orden que se muestra:  
  
    1.  Usa el BTSTask [comando AddApp](../core/addapp-command.md) para crear una aplicación.  
  
    2.  Usa el BTSTask [comando AddResource](../core/addresource-command.md) para agregar a los ensamblados de BizTalk de la aplicación tres así como otros recursos generados por Build.bat.  
  
    3.  Usa el BTSTask [comando ExportApp](../core/exportapp-command.md) exportar los artefactos de la aplicación a un archivo .msi denominado Createapplicationssample.msi.  
  
    4.  Usa el BTSTask [comando ListApp](../core/listapp-command.md) para generar un manifiesto de aplicación denominado AppManifest.xml, que enumera todos los artefactos contenidos en la aplicación.  
  
    5.  Usa el BTSTask [comando ExportApp](../core/exportapp-command.md) para exportar únicamente el ensamblado de orquestaciones en un archivo .msi denominado CreateApplicationSamplePartial.msi. Esta operación se lleva a cabo proporcionando ResourceSpecPartial.xml para el parámetro ResourceSpec. ResouceSpecPartial.xml es una versión editada de ResourceSpecComplete.xml que ha sido proporcionada con este ejemplo. Este archivo ha sido editado para que sólo contenga una referencia del ensamblado de orquestaciones. Cuando se proporciona este parámetro, BTSTask solo exporta los artefactos enumerados en el archivo ResourcesSpecPartial.xml (en este caso, el ensamblado de orquestaciones).  
  
    6.  Elimina la aplicación de la base de datos de administración de BizTalk para el grupo.  
  
-   **CreateNewAppFromMSI.bat.** Usa CreateApplicationSample.msi generado por CreateFullAndPartialMSI.bat para instalar una aplicación denominada CreateApplicationSample en el equipo local además de importar la aplicación en el grupo de BizTalk. Durante la instalación, PreProcScript.bat se ejecuta automáticamente, tal y como se describe en posteriores epígrafes.  
  
-   **RemoveApp.bat.** Realiza las siguientes acciones en el orden que se muestra:  
  
    1.  Usa el BTSTask [comando RemoveApp](../core/removeapp-command.md) para eliminar la aplicación CreateApplicationSample de la base de datos de administración de BizTalk para el grupo.  
  
    2.  Usa el BTSTask [comando UninstallApp](../core/uninstallapp-command.md) para desinstalar la aplicación CreateApplicationSample desde el equipo local. Durante la instalación, PreProcScript.bat se ejecuta automáticamente, tal y como se describe a continuación.  
  
-   **PreProcScript.bat.** Realiza las siguientes acciones en el orden que se indica:  
  
    -   Cada vez que se ejecuta, establece el token de clave pública para el ensamblado que ha sido proporcionado por el usuario.  
  
    -   Durante la instalación de la aplicación, crea las siguientes carpetas que serán utilizadas por la aplicación CreateApplicationSample para contener mensajes.  
  
         C:\CreateApplicationSample\Out  
  
         C:\CreateApplicationSample\In  
  
    -   Durante la desinstalación de la aplicación, elimina los archivos y carpetas creados en la instalación. También desinstala de la caché de ensamblados global (GAC) cualquier ensamblado que se instaló en la GAC durante la instalación y registra las acciones en un archivo. Para desinstalar los ensamblados de la GAC, hace referencia al token de clave pública proporcionado por el usuario.  
  
    -   Durante la instalación y desinstalación, crea un archivo de registro en la siguiente ubicación:  
  
         C:\ScriptLog.txt  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Puede encontrar los archivos de ejemplo en las siguientes carpetas en  *\<ruta de ejemplos\>*\Application implementación\\:  
  
-   CreateApp (Carpeta)  
  
    -   Build.bat  
  
    -   CreateFullAndPartialMSI.bat  
  
    -   CreateNewAppFromMSI.bat  
  
    -   RemoveApp.bat  
  
-   CreateApp\Bindings (Carpeta)  
  
    -   CreateApplicationSampleBindings.xml  
  
-   CreateApp\Dlls (Carpeta)  
  
    -   Vacía  
  
-   CreateApp\ResourceSpecs (Carpeta)  
  
    -   ResourceSpecPartial.xml  
  
    -   ResourceSpecComplete.xml  
  
-   CreateApp\Scripts (Carpeta)  
  
    -   PreProcScript.bat  
  
-   CreateApp\HelloApplicationDeployment (Carpeta)  
  
    -   HelloApplicationDeployment.suo  
  
    -   HelloApplicationDeployment.sln  
  
-   CreateApp\HelloApplicationDeployment\Maps (Carpeta)  
  
    -   POToInvoice.btm  
  
    -   Maps.btproj  
  
-   CreateApp\HelloApplicationDeployment\Orchestrations (Carpeta)  
  
    -   Orchestrations.btproj  
  
    -   HelloOrchestration.odx  
  
-   CreateApp\HelloApplicationDeployment\Schemas (Carpeta)  
  
    -   Schemas.btproj  
  
    -   POSSchema.xsd  
  
    -   InvoiceSchema.xsd  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Siga el siguiente procedimiento para usar este ejemplo:  
  
### <a name="to-use-the-sample"></a>Para usar el ejemplo  
  
1.  Ejecute Build.bat. Se genera un archivo de clave, se generan los proyectos en la carpeta HelloApplicationDeployment, se firman los archivos resultantes .dll y se colocan los archivos .dll en la carpeta Dlls.  
  
2.  Abra el archivo PreProcScript.bat, ubicado en la carpeta CreateApp\Scripts. En la siguiente línea de código, elimine REM y proporcione el token de clave pública para el ensamblado:  
  
     **REM establece PublicKeyToken =**  
  
     Ejemplo:  
  
     **establece PublicKeyToken = 1234a5b6c1234567**  
  
3.  Ejecute CreateFullAndPartialMSI.bat. Se crean así dos archivos de aplicación .msi: CreateApplicationSample.msi y CreateApplicationSamplePartial.msi.  
  
4.  Ejecute CreateNewAppFromMSI.bat. Se importa la aplicación CreateApplicationSample en el grupo de BizTalk y la instala en el equipo local.  
  
5.  Compruebe el archivo de registro de la secuencia de comandos, ubicado en C:\ScriptLog.txt, para verificar que la secuencia registró las acciones de instalación.  
  
6.  Verifique que la aplicación CreateApplicationSample aparece en la consola de administración de BizTalk Server y en Agregar o quitar programas.  
  
7.  Ejecute RemoveApp.bat Así se elimina CreateApplicationsSample de la base de datos de administración de BizTalk y se desinstala del equipo local.  
  
8.  Compruebe el archivo de registro de la secuencia de comandos, ubicado en C:\ScriptLog.txt, para verificar que la secuencia registró las acciones de desinstalación. Deben aparecer después de las acciones de instalación registradas anteriormente durante la instalación.  
  
9. Verifique que la aplicación CreateApplicationSample ya no aparece en la consola de administración de BizTalk Server ni en Agregar o quitar programas.  
  
10. Verifique que se han eliminado las carpetas que fueron creadas durante la instalación.  
  
11. Verifique que los ensamblados han sido desinstalados de la GAC.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [Implementación de aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)