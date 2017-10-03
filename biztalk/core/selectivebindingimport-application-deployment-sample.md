---
title: "SelectiveBindingImport (ejemplo de implementación de aplicaciones) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- examples, applications
- binding files, examples
- examples, importing
- applications, binding files
- applications, examples
- applications, importing
- deploying, scripts
- examples, binding files
ms.assetid: 963bfc80-8cc4-4d90-96b4-e85ae04405cf
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fff8a48a05f310db2d11eeddd5a0082132bbe193
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="selectivebindingimport-application-deployment-sample"></a>SelectiveBindingImport (ejemplo de implementación de aplicación)
En este tema se explica el modo de utilizar el ejemplo SelectiveBindingImport. También puede utilizar esta secuencia de comandos de ejemplo para aplicar distintos enlaces a una aplicación cuando se importa la aplicación en distintos entornos de destino. Puede utilizar este enfoque cuando desee importar los enlaces desde archivos de enlace que estén almacenados en un recurso compartido de red.  
  
> [!NOTE]
>  Si no necesita importar archivos de enlace de forma automática desde un recurso compartido de red durante la importación de la aplicación, puede agregar a la aplicación distintos archivos de enlace que tengan distintos entornos de destino especificados. Al importar la aplicación, puede especificar el entorno y los enlaces para ese entorno se aplicarán de forma automática. Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
 Las aplicaciones de BizTalk se moverán normalmente desde el desarrollo a la prueba o al ensayo y, a continuación, a los entornos de producción. Los enlaces utilizados en distintos entornos suelen ser distintos. Mediante este ejemplo, puede aplicar enlaces para entornos distintos de la siguiente forma:  
  
1.  Puede colocar todos los archivos de enlace que desee utilizar en un recurso compartido de red.  
  
2.  Puede agregar una secuencia de comandos posterior al procesamiento que importará desde esta ubicación el archivo de enlace correspondiente para el entorno de destino particular durante la importación de la aplicación. La secuencia de comandos detecta el entorno leyendo una variable de entorno con el nombre %ENVIRONMENT% que haya definido en el equipo local,  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo se muestra cómo importar archivos de enlace de forma selectiva desde un recurso compartido de red mediante el uso de secuencias de comandos posteriores al procesamiento contenidas en el archivo .msi de la aplicación de BizTalk.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Puede encontrar el siguiente ejemplo carpetas y archivos en  *\<ruta de ejemplos >*\Application Deployment\SelectiveBindingImport:  
  
-   Desarrollo (carpeta)  
  
    -   Dev.xml  
  
-   Producción (carpeta)  
  
    -   Production.xml  
  
-   Ensayo (carpeta)  
  
    -   Staging.xml  
  
-   Prueba (carpeta)  
  
    -   Test.xml  
  
-   SelectiveBindings.bat  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Utilice los procedimientos que se exponen a continuación para ejecutar el ejemplo.  
  
### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Ejecutar **Build.Bat desde el  *\<ruta de ejemplos >*\Application Deployment\CreateApp** directory. Esto crea los siguientes archivos en el  *\<ruta de ejemplos >*\Application Deployment\CreateApp\Dlls carpeta: Schemas.dll, Maps.dll y Orchestrations.dll.  
  
2.  **Crear la aplicación.** En la consola de administración de BizTalk Server, cree una aplicación, como se describe en [cómo crear una aplicación](../core/how-to-create-an-application.md).  
  
3.  **Agregar a la aplicación los archivos .dll creados en el primer paso.** Para obtener instrucciones, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
4.  **Crear la variable de entorno, como se indica a continuación:**  
  
    1.  En el menú Inicio, haga clic en **Mi PC** y haga clic en **propiedades**.  
  
    2.  En el **avanzadas** , haga clic en **Variables de entorno**.  
  
    3.  En el **variables de usuario** sección, haga clic en **nuevo**.  
  
    4.  En **nombre de Variable**, tipo **entorno**.  
  
    5.  En **valor de la Variable**, escriba los siguientes valores para el entorno: **desarrollar**, **producción**, **ensayo**, o **Prueba**. Estos valores distinguen mayúsculas de minúsculas.  
  
5.  Haga clic en **Aceptar** tres veces.  
  
6.  **Copie los archivos de enlace en una ubicación en el sistema de archivos.** Copie los archivos .xml de enlace de las carpetas Desarrollo, Prueba, Ensayo y Producción en una ubicación en su sistema de archivos.  
  
7.  **Editar la secuencia de comandos posteriores al procesamiento.** Edite SelectiveBindings.bat del modo siguiente:  
  
    1.  **Especifique la ubicación del archivo de enlace.** En la línea que contiene BINDINGS_LOC, elimine REM y proporcione la ruta a la ubicación en la que ha copiado los archivos de enlace.  
  
         Ejemplo:  
  
         BINDINGS_LOC=C:\MyBindings  
  
    2.  **Especifique el nombre de la aplicación.** En la línea que contiene APPLICATION_NAME, elimine REM y proporcione el nombre de la aplicación en la que desea importar los enlaces.  
  
         Ejemplo:  
  
         APPLICATION_Name=SelectiveBindingImport  
  
8.  **Agregue la secuencia de comandos a la aplicación como una secuencia de comandos posteriores al procesamiento.** Para obtener instrucciones, consulte [cómo agregar un prefijo o procesamiento posterior a la secuencia de comandos a una aplicación](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).  
  
9. **Exporte la aplicación.** Para obtener instrucciones, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
10. **Eliminar la aplicación.** Para obtener instrucciones, consulte [cómo eliminar una aplicación de BizTalk del grupo de BizTalk](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).  
  
11. **Importe la aplicación.** Para obtener instrucciones, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). No es necesario que especifique un entorno de destino.  
  
12. **Compruebe que se ha aplicado el archivo de enlace correcto.** Puede hacerlo comprobando el campo de descripción de las ubicaciones de recepción del modo que se indica a continuación:  
  
    1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
    2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk y la carpeta Ubicaciones de recepción.  
  
    3.  En el panel derecho, vea la descripción de las ubicaciones de recepción.  
  
13. **Instalar la aplicación.** Para obtener instrucciones, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [Implementar aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)