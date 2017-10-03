---
title: "Tareas de desarrollo para la implementación de aplicación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, deploying
- deploying [applications], developing
- applications, tasks
- deploying [applications], warnings
- applications, developing
- developing, tasks
ms.assetid: b441d4f4-122e-4caf-8381-723c6142b0b6
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 237a3f95fa33b8265be9d7af2a55ed14e2bbe408
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="development-tasks-for-biztalk-application-deployment"></a>Tareas de desarrollo para la implementación de una aplicación de BizTalk
A continuación, se indican los pasos implicados en la implementación de ensamblados de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en una aplicación de BizTalk, la finalización de la aplicación y su preparación para la implementación en el entorno de prueba. Este escenario de implementación es común en un entorno de desarrollo, donde un programador desarrolla y depura una solución empresarial de BizTalk concreta.  
  
> [!IMPORTANT]
>  No se deben realizar las tareas que se describen en este tema en un equipo de producción. Durante el proceso de desarrollo, el programador suele volver a implementar ensamblados de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para que se pueda volver a implementar, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] puede anular la implementación, anular el enlace, detener y dar de baja ensamblados que existen en la misma aplicación o en aplicaciones diferentes. Aunque esto resulta necesario y apropiado en un entorno de desarrollo, puede producir consecuencias inesperadas no deseadas en un entorno de producción. Además, para evitar la posibilidad de que alguien intente implementar un ensamblado desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en un equipo de producción, se recomienda que no instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en un equipo de producción.  
  
1.  **Desarrollar y compilar los ensamblados de BizTalk.** Empiece por crear su solución empresarial de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], mediante las orquestaciones, esquemas, asignaciones y canalizaciones. Al trabajar en la solución, ésta se genera en un ensamblado de BizTalk o en varios. Para obtener más información, consulte [desarrollar aplicaciones de BizTalk Server](../core/developing-biztalk-server-applications.md). Además, debe desarrollar y generar los ensamblados .NET que no sean de BizTalk pero que resulten necesarios para que la solución funcione.  
  
2.  **Establecer propiedades de implementación.** Cuando esté listo para implementar los ensamblados de BizTalk, establezca las propiedades de implementación en cada [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de la solución. Además de las propiedades de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (Servidor, Configuración, Base de datos, Volver a implementar, Reiniciar instancias de host e Instalar en caché global de ensamblados), también puede establecer la propiedad Nombre de aplicación. Esta propiedad especifica la aplicación de BizTalk en la que se va a implementar cada ensamblado. Si Nombre de aplicación está en blanco, el ensamblado se implementa en la aplicación predeterminada. Para obtener más información, consulte [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md). Debe implementar los ensamblados .NET que no sean de BizTalk agregándolos a la aplicación de BizTalk. Éste es un paso independiente que se describe posteriormente en el paso 4.  
  
3.  **Implementar los ensamblados de BizTalk en BizTalk Server que se ejecutan en el equipo local.** Puede implementar los ensamblados de BizTalk desde una opción de menú, haciendo clic en un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] soluciones y seleccionando el comando implementar. Esto genera los ensamblados de BizTalk en los proyectos que contiene la solución y los agrega a la aplicación de BizTalk definida en las propiedades de implementación para cada proyecto. Si la aplicación no existe, se creará. Los ensamblados y sus recursos, que se llaman "artefactos", se implementan también en la base de datos de administración de BizTalk del grupo, y podrá verlos, además de administrarlos, mediante el uso de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otras herramientas. Para obtener más información acerca de este paso, consulte [cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).  
  
4.  **Agregue los artefactos que son necesarios para la aplicación funcione correctamente.** Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, puede modificar fácilmente una aplicación para completarla, por ejemplo agregando y quitando artefactos como el envío y puertos de recepción, secuencias de comandos, directivas, ensamblados de .NET que no sean de BizTalk y así sucesivamente. Para obtener más información, consulte [crear y modificar las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md).  
  
5.  **Separe los artefactos en varias aplicaciones.** Durante el proceso de desarrollo, es posible que se hayan implementado los ensamblados en una única aplicación por comodidad. Puede que, por distintas razones, desee descomponer los artefactos en varias aplicaciones antes de que se implementen en la producción. Para obtener más información sobre los procedimientos recomendados para la descomposición de las aplicaciones, consulte [prácticas recomendadas para implementar una aplicación de BizTalk](../core/best-practices-for-deploying-a-biztalk-application.md).  
  
6.  **Crear archivos .msi para todas las aplicaciones de la solución e instalarlas localmente.** Puede usar el Asistente para exportación, disponible desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración o la herramienta de línea de comandos de BTSTask para crear un archivo .msi que contenga los artefactos de cada aplicación. Para obtener más información, consulte [exportar aplicaciones de BizTalk, los enlaces y directivas](../core/exporting-biztalk-applications-bindings-and-policies.md). Como paso adicional, puede instalar los artefactos a partir de los archivos .msi si desea ejecutar la solución en el equipo local y comprobar que funcionan del modo previsto. Para obtener más información, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md). Compruebe que la solución funciona del modo previsto.  
  
7.  **Volver a implementar los ensamblados de BizTalk según sea necesario.** En el proceso de desarrollar y depurar los ensamblados de BizTalk, debe volver a implementarlos varias veces. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Proporciona un mecanismo sencillo para volver a implementar. Para obtener más información, consulte [cómo volver a implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md).  
  
8.  **Exporte archivos de enlace y agréguelos de nuevo a las aplicaciones (opcionales).** Para facilitar la importación posterior de las aplicaciones en el entorno de desarrollo para hacer cambios o agregaciones, es posible que desee exportar los enlaces para cada aplicación y, a continuación, agregarlos de nuevo a las aplicaciones, mediante la especificación de un entorno de destino de desarrollo para los enlaces. Después, cuando importe los archivos .msi de la aplicación de nuevo a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el equipo de desarrollo, puede especificar que se apliquen estos enlaces. Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
9. **Generar un archivo .msi para cada aplicación a mano desactivar al equipo de pruebas**. Cuando haya terminado de desarrollar y depurar la solución de BizTalk, puede usar el Asistente para exportación o BTSTask para generar los archivos .msi de aplicación, tal como se describe anteriormente en el paso 6. Debe importar estos archivos en otro grupo de BizTalk en el entorno de desarrollo, instalarlos y, a continuación, compruebe que la solución funciona según lo previsto. Puede, a continuación, pasar al equipo de pruebas los archivos .msi, que puede usar para importar las aplicaciones a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutando en equipos de prueba, así como instalarlos, tal y como se describe en [tareas de prueba para la implementación de aplicación de BizTalk](../core/testing-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>Vea también  
 [Tareas de implementación de aplicaciones](../core/application-deployment-tasks.md)