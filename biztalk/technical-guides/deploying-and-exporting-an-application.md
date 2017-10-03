---
title: "Implementación y exportar una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4106a0a7-878d-4052-8eca-02d546233048
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b33762f50f32dda58f1453fde7be37bc959af6aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-and-exporting-an-application"></a>Implementación y exportación de una aplicación
Esta sección contiene información detallada sobre cómo realizar los pasos necesarios para implementar una aplicación de BizTalk. Los temas de esta sección son compatibles con las listas de comprobación siguientes:  
  
-   [Lista de comprobación: Implementar una aplicación](../technical-guides/checklist-deploying-an-application.md), que muestra cómo implementar una aplicación en un entorno de desarrollo, exportarlo a un archivo .msi y, a continuación, importarlo en un entorno de producción desde el archivo MSI.  
  
-   [Lista de comprobación: Exportar enlaces desde una aplicación a otra](../technical-guides/checklist-exporting-bindings-from-one-application-to-another.md), que muestra cómo exportar enlaces desde una aplicación a otra aplicación en la vista en un entorno de desarrollo o de producción.  
  
 Puede usar las siguientes herramientas para implementar y administrar una aplicación de BizTalk:  
  
|Herramienta|Utilice|  
|----------|---------|  
|Consola de administración de BizTalk Server|Desde esta interfaz gráfica de usuario, puede realizar todas las operaciones de administración e implementación de una aplicación de BizTalk, incluidas las siguientes:<br /><br /> -Iniciando la importación, instalación y asistentes para exportación<br />-Agregar y quitar artefactos de una aplicación y realizar otras modificaciones en la aplicación<br />-Generar archivos .msi de BizTalk Server para una aplicación de BizTalk<br />-Instalar la aplicación en un equipo desde el archivo .msi o importar la aplicación desde el archivo .msi en otro grupo de BizTalk<br />-Importar los enlaces de una aplicación desde un archivo de enlace<br /><br /> Para obtener más información acerca de la consola de administración, consulte [mediante la consola de administración de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154689) (http://go.microsoft.com/fwlink/?LinkID=154689).|  
|herramienta de línea de comandos BTSTask|Puede realizar muchas tareas de administración de aplicaciones desde la línea de comandos. Para obtener más información acerca de la herramienta de línea de comandos, consulte [referencia de línea de comandos de BTSTask](http://go.microsoft.com/fwlink/?LinkId=155003) (http://go.microsoft.com/fwlink/?LinkId=155003).|  
|API de programación y secuencias de comandos|Utilice Instrumental de administración de Microsoft Windows (WMI) o el Modelo de objetos para el explorador de BizTalk para crear y ejecutar secuencias de comandos que automaticen muchas tareas de administración de aplicaciones. Para obtener más información acerca de scripting, consulte [referencia de clase WMI](http://go.microsoft.com/fwlink/?LinkId=155004) (http://go.microsoft.com/fwlink/?LinkId=155004).|  
|[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]|Puede crear ensamblados de BizTalk en Visual Studio, use el comando implementar para implementarlos automáticamente en una aplicación de BizTalk y utilice el Explorador de BizTalk para configurar los artefactos de la aplicación desde Visual Studio. Para obtener más información acerca de cómo trabajar en Visual Studio, vea [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Crear una aplicación](../technical-guides/creating-an-application.md)  
  
-   [Implementar un ensamblado](../technical-guides/deploying-an-assembly.md)  
  
-   [Agregar artefactos a una aplicación](../technical-guides/adding-artifacts-to-an-application.md)  
  
-   [Cómo exportar una aplicación a un archivo .msi](../technical-guides/how-to-export-an-application-to-an-msi-file.md)  
  
-   [Cómo exportar enlaces a un archivo de enlace](../technical-guides/how-to-export-bindings-to-a-binding-file.md)  
  
-   [Cómo agregar un archivo de enlace a una aplicación de 1](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)  
  
-   [Cómo importar una aplicación desde un archivo .msi](../technical-guides/how-to-import-an-application-from-an-msi-file.md)  
  
-   [Cómo instalar una aplicación](../technical-guides/how-to-install-an-application.md)  
  
-   [Cómo importar enlaces desde un archivo de enlace](../technical-guides/how-to-import-bindings-from-a-binding-file.md)  
  
-   [Probar una aplicación](../technical-guides/testing-an-application.md)  
  
-   [Cómo agregar una referencia a una aplicación](../technical-guides/how-to-add-a-reference-to-an-application.md)