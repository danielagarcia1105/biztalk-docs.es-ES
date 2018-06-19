---
title: Cambios en el sistema del proyecto de BizTalk en BizTalk Server 2013 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82f0dd18-073c-4cba-aa0d-48076c58f874
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 836ffa11e3b15b379b8f4a07def2269f0f29a453
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006277"
---
# <a name="changes-to-biztalk-project-system-in-biztalk-server-2013"></a>Cambios en el sistema de proyecto de BizTalk en BizTalk Server 2013
Este tema ofrece una descripción general de los cambios al sistema del proyecto de BizTalk en BizTalk Server.  
  
## <a name="project-properties-are-displayed-in-project-designer-window"></a>Las propiedades del proyecto se muestran en la ventana del diseñador de proyectos.  
 Las propiedades para un proyecto de BizTalk se muestran ahora en el diseñador de proyectos de Visual Studio en lugar de en un diálogo Propiedades. El diseñador de proyectos proporciona una ubicación centralizada para administrar las propiedades del proyecto, la configuración y los recursos. El diseñador de proyectos aparece como una única ventana en el IDE de Visual Studio, de forma muy parecida a otros diseñadores, como los diseñadores de formas o clases, y contiene varias páginas a las que se obtiene acceso mediante pestañas del lado izquierdo. Para obtener más información, consulte [http://go.microsoft.com/fwlink/?LinkId=190417](http://go.microsoft.com/fwlink/?LinkId=190417).  
  
## <a name="properties-for-schema-and-map-files-are-displayed-in-properties-window"></a>Las propiedades para los archivos de esquema y de asignación se muestran en la ventana Propiedades.  
 Propiedades de los archivos de esquema y de asignación como **nombre de archivo de instancia de entrada** y **instancia de entrada de asignación de prueba** se muestran en la ventana de propiedades con en lugar de en otro **propiedades** cuadro de diálogo.  
  
## <a name="add-web-reference-option-on-projects"></a>Opción Agregar referencia web en proyectos  
 El **Agregar referencia Web** opción no está disponible cuando hace clic en el nombre del proyecto o **referencias** en el Explorador de soluciones. Puede agregar una referencia web a un servicio web (.asmx) usando los pasos siguientes:  
  
1.  Haga clic en **referencias** en el proyecto y, a continuación, haga clic en **Agregar referencia de servicio**.  
  
2.  En el **Agregar referencia de servicio** cuadro de diálogo, haga clic en **avanzadas**.  
  
3.  En el **configuración de referencia de servicio** cuadro de diálogo, haga clic en **Agregar referencia Web**.  
  
4.  Escriba la dirección URL y, a continuación, haga clic en **vaya**.  
  
5.  Haga clic en **Agregar referencia** para agregar la referencia Web.  
  
    > [!TIP]
    >  Después de agregar una referencia Web a un proyecto de BizTalk, el **Agregar referencia Web** opción de menú está disponible en las referencias, referencias Web y nodos del proyecto.  
  
 Para obtener más información acerca de cómo agregar referencias Web y servicio, consulte [http://go.microsoft.com/fwlink/?LinkId=131577](http://go.microsoft.com/fwlink/?LinkId=131577).  
  
## <a name="msbuild-integration"></a>Integración de MSBUILD  
 Visual Studio usa el formato de archivo de proyecto MSBUILD para almacenar información de generación sobre proyectos administrados, incluidos los proyectos de BizTalk. Para obtener más información, consulte [integración de MSBUILD con Visual Studio](../core/msbuild-integration-with-visual-studio.md).  
  
## <a name="team-foundation-server-integration"></a>Integración de Team Foundation Server  
 Puede usar Team Foundation Server como sistema de control de origen para proyectos de BizTalk. Puede realizar operaciones como proteger o desproteger desde la propia ventana del Explorador de soluciones.  
  
## <a name="support-for-unit-testing"></a>Compatibilidad con pruebas unitarias  
 Esta característica permite probar unitariamente esquemas, mapas y canalizaciones. Para obtener más información, consulte [pruebas unitarias con proyectos de BizTalk Server](../core/unit-testing-with-biztalk-server-projects.md).  
  
## <a name="debug-map-feature"></a>Característica de depuración de asignación  
 **Característica de asignación de depuración**. Puede depurar una asignación (XSLT) usando el depurador XSLT en línea de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para obtener más información, consulte [cómo depurar mapas](../core/how-to-debug-maps.md).  
  
## <a name="migrating-biztalk-server-projects"></a>Migrar proyectos de BizTalk Server  
 Proyectos de Visual Studio desarrollan para la versión anterior de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pueden migrar al entorno de BizTalk Server mediante el Asistente para conversión de Visual Studio. Para obtener más información, consulte [migrar un proyecto de BizTalk Server](../core/migrating-a-biztalk-server-project.md).  
  
## <a name="release-and-debug-build-types"></a>Tipos de generación de lanzamiento y depuración  
 Proyectos de BizTalk ahora tienen dos tipos de compilación: **versión** y **depurar**, que sustituyen **desarrollo** y **implementación** de versiones anteriores versiones. Sin embargo, continuarán viendo el **desarrollo** y **implementación** configuraciones para los proyectos que se migran desde [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)].  
  
## <a name="embedding-tracking-and-debugging-information"></a>Inserción de información de seguimiento y depuración  
 El **incrustar información de seguimiento** y **generar información de depuración** propiedades de configuración de salida se reemplazan por el **definir constante TRACE** y **Definir constante DEBUG** opciones de compilación el **generar** pestaña del Diseñador de proyectos. El **generación de código de compatibilidad con BPEL** propiedad de configuración se sustituye por **generación de código de cumplimiento de BPEL** propiedad en la ventana de propiedades del proyecto.  
  
> [!IMPORTANT]
>  El asistente para conversión de Visual Studio migra automáticamente la configuración precedente mencionada al nuevo entorno.  
  
## <a name="user-access-control"></a>Control de acceso de usuario  
 Visual Studio no permite implementar un proyecto de BizTalk en un equipo con la característica Control de acceso de usuario (UAC) activada a menos que ejecute Visual Studio con privilegios administrativos. Para ejecutar Visual Studio con privilegios de administrador, haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Visual Studio**, haga clic en  **Microsoft Visual Studio \<versión\>** y, a continuación, haga clic en **ejecutar como administrador**.  
  
## <a name="c-files-in-a-biztalk-project"></a>Archivos C# en un proyecto de BizTalk  
 BizTalk Server permite combinar las clases auxiliares con artefactos de BizTalk para sólo las necesidades de empaquetado flexible.  Sin embargo, no se puede agregar un nuevo archivo de C# directamente mediante el **Agregar nuevo elemento** o **agregar nueva clase** opciones de menú.  
  
## <a name="generatecsfiles-registry-key-is-obsolete"></a>La clave de registro GenerateCSFiles está obsoleta  
 El **GenerateCSFiles** clave del registro ahora está obsoleta. Todos los archivos .cs generados se muestran en la ventana del Explorador de soluciones. Debe hacer clic en **mostrar todos los archivos** elemento de barra de herramientas en la ventana Explorador de soluciones para ver los archivos .cs asociados con algunos de los elementos de BizTalk.