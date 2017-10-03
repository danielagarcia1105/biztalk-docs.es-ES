---
title: "Implementar una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04bb4496-b1e9-400b-a849-a355381849ff
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61bc0e446e635fd4111804f7160651df6492a60c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-an-application"></a>Implementar una aplicación
La implementación es la distribución logística de artefactos de la aplicación para asegurarse de que todos los componentes necesarios están disponibles para los sistemas que los necesiten. Estos artefactos incluyen el servidor BizTalk Server ensamblados, .NET ensamblados, esquemas, mapas, enlaces, reglas de negocios y certificados. La aplicación de BizTalk puede aprovecharse para ayudar a implementar artefactos a otros equipos que se agregan al grupo o para el almacenamiento provisional (cuando el transporte de una aplicación a otro entorno).  
  
 Hay muchas maneras de implementar los artefactos de BizTalk como importarlos como parte de una aplicación utilizando el Asistente para la implementación (un archivo .msi), importarlos mediante BTSTask.exe, su implementación desde Visual Studio o con MSBuild. Si se importan mediante BTSTask.exe o implementarlos desde Visual Studio, puede especificar una aplicación e implementarlos en, o deje el nombre de la aplicación en blanco, en cuyo caso se implementará en la aplicación predeterminada.  
  
## <a name="deploying-by-using-an-msi-file"></a>Implementar mediante un archivo .msi  
 Con BizTalk Server, puede implementar una aplicación y sus artefactos exportándolas a un archivo MSI. (Para obtener más información acerca de las aplicaciones y artefactos, vea [¿qué es una aplicación de BizTalk?](http://go.microsoft.com/fwlink/?LinkId=154994) (http://go.microsoft.com/fwlink/?LinkId=154994). Implementación de una aplicación de BizTalk implica importar los artefactos de la aplicación en la base de datos de administración de BizTalk, así como para instalar los artefactos en cada equipo que sea miembro del grupo. Implementación en un archivo .msi serializa todos los artefactos de la aplicación en un paquete. Esto puede realizarse realizando una operación de exportación desde la consola de administración o mediante BTSTask.exe desde la línea de comandos. Una vez que tenga un archivo .msi, puede implementar todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblados a la administración de BizTalk para el grupo de la base de datos o ejecutar secuencias de comandos para ejecutarse en el momento de la importación. Esto se realiza mediante Microsoft Management Console (MMC) y realizar una operación de importación del archivo .msi (o a través de una operación de importación desde la línea de comandos BTSTASK). La operación de importación del archivo .msi que crea la aplicación de BizTalk de destino.  
  
 Con el archivo .msi, puede implementar la aplicación en un único equipo, para que todos los ensamblados de BizTalk Server y ensamblados de dependencias se almacenan en la caché Global de ensamblados en el equipo. A continuación, el equipo tiene todos los archivos binarios que necesita para tiempo de ejecución. En esta operación, también puede implementar servicios Web que forman parte de la solución o aplicar cambios específicos del equipo por secuencias de comandos. Esta operación se realiza ejecutando el archivo MSI. Puede realizar esta operación en cada equipo que ejecuta BizTalk Server que sea miembro del grupo de BizTalk correspondiente. También puede usar un archivo .msi para instalar una aplicación en un servidor nuevo que se agrega a un grupo.  
  
 Si va a migrar la aplicación de BizTalk a un nuevo grupo, debe ejecutar la instalación .msi en todos los servidores en el nuevo grupo. Debe importar el archivo .msi una vez para el grupo. Al hacerlo, la aplicación y su contenido está instalado en todos los equipos de tiempo de ejecución en el nuevo grupo y también se registra con la base de datos de administración de BizTalk para el grupo. También puede agregar varios archivos de enlace a un archivo .msi, además de los enlaces implícita. Cada archivo de enlace adicional puede asociarse con un "entorno". Cuando hay varios archivos de enlace asociados con una aplicación de BizTalk durante la implementación, puede elegir qué archivos de enlace que se utilizarán según el entorno (de producción, de ensayo o de prueba) para que se va a implementar.  
  
 Puede utilizar secuencias de comandos con archivos .msi para personalizar un servidor (operación de instalación) o el grupo (operación de importación). Para obtener más información sobre el uso de scripts con archivos .msi, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](http://go.microsoft.com/fwlink/?LinkId=154995) (http://go.microsoft.com/fwlink/?LinkId=154995).  
  
 Para una lista de comprobación de los pasos para implementar una aplicación, consulte [lista de comprobación: implementar una aplicación](../technical-guides/checklist-deploying-an-application.md).  
  
## <a name="exporting-an-applications-bindings-by-using-a-binding-file"></a>Exportar enlaces de una aplicación mediante un archivo de enlace  
 Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede exportar los enlaces de una aplicación en un archivo de enlace y, a continuación, importar los enlaces desde el archivo de enlace a otra aplicación. Para ello, la aplicación de destino ya debe existir; el procedimiento de importación no crea la aplicación. El archivo de enlace es un archivo XML que contiene los enlaces de todos los artefactos de una aplicación, un grupo o un ensamblado. También puede exportar todos los enlaces para un grupo de BizTalk o los enlaces para un ensamblado de BizTalk. Para obtener más información sobre cómo trabajar con enlaces, vea [cómo exportar enlaces a un archivo de enlace](../technical-guides/how-to-export-bindings-to-a-binding-file.md) y [cómo importar enlaces desde un archivo de enlace](../technical-guides/how-to-import-bindings-from-a-binding-file.md).  
  
 También puede agregar un archivo de enlace como un recurso a un archivo MSI. Para obtener más información acerca de cómo agregar un archivo de enlace como un recurso, vea [cómo exportar una aplicación a un archivo .msi](../technical-guides/how-to-export-an-application-to-an-msi-file.md).  
  
 Para obtener más información acerca de la implementación de aplicaciones en general, vea [implementación de aplicación de BizTalk de descripción y administración](http://go.microsoft.com/fwlink/?LinkId=154996) (http://go.microsoft.com/fwlink/?LinkId=154996).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Prácticas recomendadas para implementar una aplicación](../technical-guides/best-practices-for-deploying-an-application.md)  
  
-   [Problemas conocidos con la implementación de una aplicación](../technical-guides/known-issues-with-deploying-an-application.md)  
  
-   [Permisos para administrar una aplicación](../technical-guides/permissions-for-managing-an-application.md)  
  
-   [Artefactos que deben ser únicos en una aplicación](../technical-guides/artifacts-that-must-be-unique-in-an-application.md)  
  
-   [Implementación y exportación de una aplicación](../technical-guides/deploying-and-exporting-an-application.md)