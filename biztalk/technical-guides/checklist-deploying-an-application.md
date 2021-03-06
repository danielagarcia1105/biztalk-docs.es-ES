---
title: 'Lista de comprobación: Implementar una aplicación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e699ac3-7998-48d6-96b7-2f8f1a3d52e5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 713eef12a06cb8331faf39acede7c14143a45032
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299860"
---
# <a name="checklist-deploying-an-application"></a>Lista de comprobación: Implementar una aplicación
En este tema se describe los pasos necesarios para implementar una aplicación de BizTalk y sus artefactos en un entorno de producción. Muestra cómo implementar una aplicación en el entorno de desarrollo, exportarlo a un archivo .msi y, a continuación, importarlo en el entorno de producción desde el archivo MSI.  
  
 Implementación de la aplicación consta de importar la aplicación a un grupo e instalación de la aplicación en servidores individuales (instancias de host) en el grupo. Para obtener más información sobre la importación y la instalación de aplicaciones, consulte [cómo importar una aplicación desde un archivo .msi](../technical-guides/how-to-import-an-application-from-an-msi-file.md).  
  
 Para obtener más información acerca de la implementación de aplicaciones, consulte [el proceso de implementación de aplicación](http://go.microsoft.com/fwlink/p/?LinkId=154716) (http://go.microsoft.com/fwlink/p/?LinkId=154716).  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Asegúrese de que tiene los permisos adecuados para realizar la implementación.|[Permisos para administrar una aplicación](../technical-guides/permissions-for-managing-an-application.md)|  
|Establecer las propiedades de implementación en Visual Studio para cada proyecto de la solución de BizTalk Server, incluida la aplicación que se implementará el ensamblado a.<br /><br /> Implementar los ensamblados de BizTalk Server necesarios en la aplicación de BizTalk en el entorno de desarrollo (o volver a implementar).|-   [Cómo establecer propiedades de implementación en Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=154718) (http://go.microsoft.com/fwlink/p/?LinkId=154718).<br />-   [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](http://go.microsoft.com/fwlink/p/?LinkId=154719) (http://go.microsoft.com/fwlink/p/?LinkId=154719).<br />-   [Cómo volver a implementar un ensamblado de BizTalk desde Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=154720) (http://go.microsoft.com/fwlink/p/?LinkId=154720).<br />-   [Implementar un ensamblado](../technical-guides/deploying-an-assembly.md)<br />-"Implementar una aplicación de BizTalk", "Crear una aplicación de BizTalk" e "Implementar un ensamblado de BizTalk" secciones de [prácticas recomendadas para implementar una aplicación](http://msdn.microsoft.com/library/gg634504.aspx).<br />-Sección "Implementar una aplicación de BizTalk" de [problemas conocidos con la implementación de una aplicación](../technical-guides/known-issues-with-deploying-an-application.md).|  
|Agregar artefactos a la aplicación de BizTalk y configure los artefactos en el entorno de desarrollo.<br /><br /> Esto puede incluir la factorización de artefactos en varias aplicaciones de BizTalk.|-   [Cómo crear o agregar un artefacto](http://go.microsoft.com/fwlink/p/?LinkId=154724) (http://go.microsoft.com/fwlink/p/?LinkId=154724).<br />-   [Administrar artefactos](http://go.microsoft.com/fwlink/p/?LinkId=154725) (http://go.microsoft.com/fwlink/p/?LinkId=154725).<br />-   [Archivos de enlace e implementación de la aplicación](http://go.microsoft.com/fwlink/p/?LinkId=154726) (http://go.microsoft.com/fwlink/p/?LinkId=154726).<br />-   [Agregar artefactos a una aplicación](../technical-guides/adding-artifacts-to-an-application.md)<br />-Sección "Agregar artefactos a una aplicación de BizTalk" de [prácticas recomendadas para implementar una aplicación](http://msdn.microsoft.com/library/gg634504.aspx).<br />-Sección "Agregar artefactos a una aplicación de BizTalk" de [problemas conocidos con la implementación de una aplicación](../technical-guides/known-issues-with-deploying-an-application.md).|  
|Exporte la aplicación de BizTalk a un archivo .msi en el entorno de desarrollo.|-   [Cómo exportar una aplicación a un archivo .msi](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-"Exportación de una aplicación de BizTalk" sección de [prácticas recomendadas para implementar una aplicación](http://msdn.microsoft.com/library/gg634504.aspx).<br />-"Exportación de una aplicación de BizTalk" sección de [problemas conocidos con la implementación de una aplicación](../technical-guides/known-issues-with-deploying-an-application.md).|  
|Importar la aplicación de BizTalk en el entorno de producción desde el archivo MSI. (Esta operación consiste en importar la aplicación en el grupo y si la aplicación incluye artefactos basados en archivos, instalar la aplicación en cada servidor del grupo.)|-   [Cómo exportar una aplicación a un archivo .msi](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [Cómo instalar una aplicación](http://go.microsoft.com/fwlink/p/?LinkId=154728) (http://go.microsoft.com/fwlink/p/?LinkId=154728).<br />-"Importación de una aplicación de BizTalk" sección de [prácticas recomendadas para implementar una aplicación](http://msdn.microsoft.com/library/gg634504.aspx)<br />-"Importación de una aplicación de BizTalk" sección de [problemas conocidos con la implementación de una aplicación](../technical-guides/known-issues-with-deploying-an-application.md)|  
|Realice las modificaciones adicionales a la aplicación de BizTalk en el entorno de producción para que se ejecute en ese entorno, como cambiar las configuraciones de puerto. Si lo hace, exporte la aplicación a un archivo MSI.|-   [Cómo exportar una aplicación a un archivo .msi](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [Creación y modificación de las aplicaciones de BizTalk](http://go.microsoft.com/fwlink/p/?LinkId=154727) (http://go.microsoft.com/fwlink/p/?LinkId=154727).<br />-   [Cómo agregar un archivo de enlace a una aplicación de 1](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)<br />-"Exportación de una aplicación de BizTalk" sección de [prácticas recomendadas para implementar una aplicación](http://msdn.microsoft.com/library/gg634504.aspx)<br />-"Exportación de una aplicación de BizTalk" sección de [problemas conocidos con la implementación de una aplicación](../technical-guides/known-issues-with-deploying-an-application.md)|  
|Si ha realizado modificaciones adicionales en la aplicación de BizTalk en el entorno de producción, debe instalar la aplicación de BizTalk desde el archivo .msi en cualquier otro equipo en el entorno de producción que vayan a ejecutarla.<br /><br /> Además, importar la aplicación a cualquier otro grupo de BizTalk que desea implementar y si la aplicación incluye artefactos basados en archivos, instale la aplicación en los servidores en los grupos.|-   [Cómo instalar una aplicación de BizTalk](http://go.microsoft.com/fwlink/p/?LinkId=154728) (http://go.microsoft.com/fwlink/p/?LinkId=154728).<br />-   [Cómo importar una aplicación desde un archivo .msi](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-"Importación de una aplicación de BizTalk" sección de [prácticas recomendadas para implementar una aplicación](http://msdn.microsoft.com/library/gg634504.aspx)<br />-"Importación de una aplicación de BizTalk" sección de [problemas conocidos con la implementación de una aplicación](../technical-guides/known-issues-with-deploying-an-application.md)|  
|Inicie la aplicación de BizTalk en el entorno de producción desde la consola de administración de BizTalk Server y compruebe que funciona correctamente.|-   [Cómo iniciar y detener una aplicación de BizTalk](http://go.microsoft.com/fwlink/p/?LinkId=154729) (http://go.microsoft.com/fwlink/p/?LinkId=154729).<br />-   [Probar una aplicación](../technical-guides/testing-an-application.md)|  
  
## <a name="see-also"></a>Vea también  
 [Implementar un ensamblado](../technical-guides/deploying-an-assembly.md)   
 [Agregar artefactos a una aplicación](../technical-guides/adding-artifacts-to-an-application.md)   
 [Cómo exportar una aplicación a un archivo .msi](../technical-guides/how-to-export-an-application-to-an-msi-file.md)   
 [Cómo exportar enlaces a un archivo de enlace](../technical-guides/how-to-export-bindings-to-a-binding-file.md)   
 [Cómo importar una aplicación desde un archivo .msi](../technical-guides/how-to-import-an-application-from-an-msi-file.md)   
 [Cómo instalar una aplicación](../technical-guides/how-to-install-an-application.md)   
 [Cómo importar enlaces desde un archivo de enlace](../technical-guides/how-to-import-bindings-from-a-binding-file.md)