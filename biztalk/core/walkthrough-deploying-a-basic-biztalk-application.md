---
title: "Tutorial: Implementar una aplicación básica de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, tutorials
- tutorials, deploying
- tutorials, applications
- applications, tutorials
ms.assetid: 21b67153-0f8c-406a-a224-fc792b16192f
caps.latest.revision: "69"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db86f672cd17965ec76877cc3867594bf82b40d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-deploying-a-basic-biztalk-application"></a>Tutorial: Implementar una aplicación de BizTalk básico
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye características que simplifican la administración e implementación de las soluciones empresariales de BizTalk. Ahora incluye un contenedor de aplicaciones de BizTalk para los elementos que componen una solución empresarial, como orquestaciones, esquemas, asignaciones, canalizaciones y ensamblados .NET. Puede administrar, modificar, implementar e instalar todos los elementos en una aplicación como una sola unidad. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]También incluye asistentes para ayudar a automatizar las tareas de implementación de aplicaciones. Para obtener información general, vea [implementación de aplicaciones y características de administración de](../core/application-deployment-and-management-features.md) y [implementación de aplicaciones y herramientas de administración](../core/application-deployment-and-management-tools.md).  
  
 En este tutorial se incluyen instrucciones detalladas para usar las características de implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de manera que pueda ver el modo de funcionamiento conjunto. El proceso de implementación descrito en este tutorial puede o no reflejar el modo en que se administrará la implementación de la aplicación en su compañía.  
  
 En este tutorial se propone crear una aplicación sencilla de BizTalk y, después, implementarla desde el entorno de desarrollo a un entorno de prueba y, desde ahí, a los entornos de ensayo y producción. Cuando concluya el tutorial, comprenderá cómo se realizan las tareas siguientes:  
  
-   Desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] instalado en un equipo de desarrollo, use el comando Implementar para implementar los ensamblados de BizTalk a una instancia local de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. De este modo, se creará una aplicación de BizTalk que se rellenará con los ensamblados. Un ensamblado de BizTalk contiene información de recursos, como orquestaciones, canalizaciones, esquemas y asignaciones que se utilizarán en una solución de BizTalk.  
  
-   Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, agregar, crear, configurar y quitar todos los elementos (denominado *artefactos*) según sea necesario para crear una solución empresarial completamente funcional, como enviar y recibir los puertos, directivas, ensamblados, y secuencias de comandos.  
  
-   Use los asistentes para exportar, importar e instalar para implementar la aplicación BizTalk en un equipo de prueba con el fin de realizar comprobaciones funcionales y del sistema.  
  
-   Use los asistentes para exportar, importar e instalar para implementar la aplicación en un servidor de ensayo desde donde se realizará la configuración final y la implementación en un servidor de producción.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Hay dos opciones para configurar el entorno de prueba para este tutorial:  
  
-   Realizar las tareas de este tutorial en un único equipo.  
  
-   Simular de forma aproximada una implementación real mediante la configuración de diferentes equipos para usarlos como equipos de desarrollo, prueba, ensayo y producción. No obstante, no se debería realizar ninguna de las tareas de este tutorial en un entorno de producción real.  
  
 Para efectuar los pasos descritos en este tutorial, compruebe que el entorno de prueba cumple los requisitos previos siguientes:  
  
-   El equipo de desarrollo desde el que implementa los ensamblados de BizTalk tiene Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] instalado.  
  
-   Todos los equipos que se usen en el proceso de implementación de la aplicación descrito en este tutorial, incluido el equipo de desarrollo, tienen [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalado.  
  
-   Cada instancia de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es una instalación independiente; es decir, dispone de sus propias bases de datos y grupos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Además de estos requisitos, es necesario que tenga disponible una solución o proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] que contenga ensamblados de BizTalk. Si no es así, puede usar la solución de ejemplo de control de errores que se incluye con el SDK de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para este fin. Las instrucciones de uso de este ejemplo se incluyen en este tutorial más adelante.  
  
 Debe tener además una cuenta de usuario que sea miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y del grupo de administradores locales en los equipos donde va a realizar las tareas que se describen en este tutorial.  
  
 Para obtener más información sobre cómo instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [¿qué es nuevo, instalar, configurar y actualizar](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).
  
##  <a name="BKMK_Assumptions"></a>Suposiciones  
 En este tutorial se suponen las circunstancias siguientes:  
  
-   Tiene un conocimiento básico de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. [Introducción a BizTalk Server](../core/getting-started-with-biztalk-server.md) provechoso.
  
-   Los ensamblados de BizTalk que va a utilizar no se han implementado previamente en su entorno de prueba. En el caso de que sí estén implementados, debería anular la implementación de la aplicación de BizTalk en la que se hayan implementado los ensamblados. Para obtener instrucciones, consulte [anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md).  
  
-   No hay recursos de aplicaciones compartidos con otras aplicaciones.  
  
##  <a name="BKMK_Audience"></a>Audiencia  
 La audiencia de este tutorial está compuesta por:  
  
-   **Desarrolladores de aplicaciones de BizTalk.** Los programadores pueden aprender cómo establecer propiedades del proyecto en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] e implementar ensamblados de BizTalk desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] a una aplicación de BizTalk. Además, los programadores aprenden cómo se agregan artefactos a la aplicación y cómo se exporta la aplicación a un archivo MSI. Para obtener información general acerca de las tareas de implementación de aplicación para que un desarrollador, consulte [tareas de desarrollo para la implementación de aplicación de BizTalk](../core/development-tasks-for-biztalk-application-deployment.md).  
  
-   **Evaluadores de aplicaciones de BizTalk.** Los evaluadores pueden aprender cómo importar el archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecuta en su equipo de prueba, lo que lo registra como una aplicación de BizTalk. Después, los evaluadores pueden aprender cómo se instala la aplicación en el equipo de prueba y comprobar la instalación. Para obtener información general acerca de las tareas de implementación de aplicación para las pruebas, consulte [tareas de prueba para la implementación de aplicación de BizTalk](../core/testing-tasks-for-biztalk-application-deployment.md).  
  
-   **Administradores de TI de BizTalk Server.** Los administradores de tecnologías de la información que son responsables de implementar aplicaciones de BizTalk en servidores de ensayo y de producción pueden aprender cuáles son los pasos básicos necesarios para realizar esta tarea. Para obtener información general acerca de las tareas de implementación de aplicación para que un administrador de TI, vea [tareas de almacenamiento provisional para la implementación de aplicación de BizTalk](../core/staging-tasks-for-biztalk-application-deployment.md) y [las tareas de producción para la implementación de aplicación de BizTalk](../core/production-tasks-for-biztalk-application-deployment.md).  
  
##  <a name="BKMK_Overview"></a>Información general de este tutorial  
 La finalidad de este tutorial consiste en implementar una aplicación de BizTalk en un entorno de pruebas con el fin de evaluar el funcionamiento de esta tecnología si la implementación se realizara en un entorno de producción. El escenario sencillo que se describe en este tutorial (implementación de un único archivo MSI como una aplicación de BizTalk en un único equipo) ayudará a familiarizarse con las tareas básicas implicadas en la implementación de aplicaciones.  
  
> [!NOTE]
>  En este tutorial no se incluyen instrucciones para la configuración de la aplicación, como el enlace de orquestaciones, la configuración de puertos y otros aspectos que son necesarios para que la aplicación funcione. Aquí sólo se pretende introducir las nuevas características de implementación de aplicaciones.  
  
 Las instrucciones que se proporcionan en este documento corresponden a las tareas siguientes:  
  
1.  **Configurar los permisos necesarios.** Antes de comenzar el tutorial, es necesario asegurarse de que dispone de los permisos adecuados para realizar las tareas.  
  
2.  **Implementar ensamblados de BizTalk desde Visual Studio.** El programador de aplicaciones es el encargado de realizar este paso. La implementación de ensamblados de BizTalk desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] crea de forma automática los ensamblados e implementa su contenido en una aplicación de BizTalk. Si la aplicación no existe aún, la implementación de los ensamblados también crea la aplicación. Los artefactos de la aplicación se registran y sus datos se almacenan en la base de datos de administración de BizTalk. Además, los ensamblados se instalan de forma predeterminada en la caché de ensamblados global (GAC) del equipo local. Una vez que la aplicación se haya creado, puede ver y administrar sus artefactos desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En la consola de administración, cada aplicación se almacena en su propia carpeta, con subcarpetas que contienen referencias a todos los artefactos de la aplicación.  
  
3.  **Configuración de la aplicación.** El programador de aplicaciones o el administrador de tecnologías de la información realiza este paso para agregar, crear y configurar los artefactos necesarios para que la aplicación funcione correctamente. Desde la consola de administración, puede agregar, crear, configurar y quitar artefactos de forma fácil como son los puertos de envío y recepción, las secuencias de comandos y los ensamblados adicionales. Una vez que la aplicación contenga los artefactos necesarios y estén configurados de forma adecuada, hay que exportarla a un archivo MSI, tal y como se describe a continuación.  
  
4.  **Exportar la aplicación a un archivo MSI.** Este paso está dirigido al programador, al evaluador o al administrador de tecnologías de la información para que puedan generar un archivo MSI que se pueda utilizar para implementar una aplicación de BizTalk en un entorno diferente. Por ejemplo, el programador puede exportar un archivo MSI que el evaluador utilice después para implementar la aplicación en un servidor de prueba. Una vez que las pruebas hayan concluido, el administrador de tecnologías de la información puede utilizar el archivo MSI ya comprobado para implementar la aplicación en un servidor de ensayo o de producción (tal y como se describe a continuación). En este tutorial se describe cómo se exporta una aplicación a un archivo MSI mediante el Asistente para exportar, disponible desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
5.  **Instalar la aplicación desde el archivo .msi de la importación.** El evaluador o el administrador de tecnologías de la información pueden realizar este paso para implementar una aplicación de BizTalk en un servidor de ensayo o de producción. Por ejemplo, el evaluador puede importar la aplicación desde un archivo MSI, que el programador haya proporcionado a un grupo de BizTalk, en un equipo de prueba y, después, puede instalar la aplicación desde el archivo MSI para probar su funcionamiento. Del mismo modo, el administrador de tecnologías de la información puede implementar la aplicación desde un archivo MSI, que haya proporcionado el evaluador, en un servidor de ensayo o de producción. En este tutorial se describe cómo se utiliza el Asistente para importación para poder importar el archivo MSI en una aplicación en un grupo de BizTalk. Como en el paso 2, los artefactos de la aplicación se registran y sus datos se almacenan en la base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este tutorial también se describe cómo se instala la aplicación en el servidor actual mediante el Asistente para instalación o al hacer doble clic en el archivo MSI. De este modo, puede ejecutar la aplicación en el servidor actual.  
  
##  <a name="BKMK_Step-by-step"></a>Guía paso a paso para implementar una aplicación de BizTalk  
 En esta sección se proporcionan procedimientos descritos paso a paso para implementar una aplicación de BizTalk a través de todas sus fases, desde el desarrollo hasta la prueba y después hasta el ensayo y la producción. Como se ha mencionado anteriormente, puede efectuar todos estos pasos en el mismo equipo o, si desea simular de forma más real su entorno, puede utilizar varios equipos.  
  
#### <a name="1-configure-permissions"></a>1. Configurar permisos  
 El primer paso consiste en asegurarse de que dispone de los permisos adecuados para realizar las tareas que se describen en este tutorial. Vea [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos de seguridad mínimos](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).
  
#### <a name="2-deploy-the-biztalk-assemblies"></a>2. Implementar los ensamblados de BizTalk  
 Desde Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] instalado en el equipo de desarrollo, efectúe los procedimientos de este paso para implementar ensamblados de BizTalk en una aplicación de BizTalk.  
  
 Antes de comenzar, debe tener una solución de BizTalk disponible en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Puede crear su propia solución o proyecto, o bien configurar el ejemplo de control de errores que se incluye con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]. Puede configurar la solución de ejemplo de control de errores ErrorHandling en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] de la forma siguiente.  
  
###### <a name="to-set-up-the-errorhandling-solution"></a>Para configurar la solución ErrorHandling  
  
1.  En el equipo de desarrollo, desplácese a:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Messaging\ErrorHandling\ErrorHandler  
  
2.  Haga doble clic en **ErrorHandler.btproj**.  
  
     La solución ErrorHandler se abre en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Esta solución consta de dos proyectos: ErrorHandler y PipelinesAndSchemas.  
  
     ![Proyectos de Visual Studio en una solución](../core/media/errorhandlingprojects.gif "ErrorHandlingProjects")  
  
 A continuación, debe definir las propiedades de cada proyecto de la solución. La solución de ejemplo ErrorHandling incluye dos proyectos para el que se deben establecer las propiedades: ErrorHandler y PipeLinesAndSchemas. Configure las propiedades para que se refleje el entorno del equipo de desarrollo. Por ejemplo, el servidor SQL Server que especifique debería ser la instancia que se ejecute en el equipo de desarrollo y donde esté alojada la base de datos de administración de BizTalk local.  
  
###### <a name="to-configure-project-properties"></a>Para configurar las propiedades del proyecto  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga un proyecto para el que desea configurar las propiedades y, a continuación, haga clic en **propiedades**.  
  
2.  Haga clic en el **implementación** ficha en el Diseñador de proyectos.  
  
     ![Hoja de propiedades de implementación en Visual Studio 2005](../core/media/deploymentproperties.gif "DeploymentProperties")  
  
3.  Configurar propiedades del proyecto, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Propiedad|Valor|Explicación|  
    |--------------|-----------|-----------------|  
    |Application Name|\<Name>|Nombre de la aplicación de BizTalk en la que se van a implementar los ensamblados de este proyecto. Si la aplicación ya existe, los ensamblados se agregarán a ella cuando implemente el proyecto. En cambio, si no existe, se creará la aplicación. Si se deja este campo en blanco, los ensamblados se implementarán en la aplicación de BizTalk predeterminada del grupo actual, "BizTalk Application 1" de forma predeterminada. Los nombres que incluyen espacios deben flanquearse con comillas dobles (").|  
    |Base de datos de configuración|\<Nombre de la base de datos de administración de BizTalk >|Nombre de la base de datos de administración de BizTalk del grupo; el nombre predeterminado es BizTalkMgmtDb.|  
    |Server|\<Nombre del servidor >|Nombre de la instancia del servidor SQL Server que aloja la base de datos de administración de BizTalk en el equipo local. En las instalaciones de un solo equipo, suele ser el nombre del equipo local. **Nota:** si mueve este proyecto de BizTalk a un equipo diferente, debe modificar la propiedad del servidor para reflejar el nuevo nombre del equipo antes de poder implementar el ensamblado.|  
    |Volver a implementar|True o False|Si se define en True (valor predeterminado), puede volver a implementar los ensamblados de BizTalk sin cambiar el número de versión.|  
    |Instalar caché de ensamblados total (GAC)|True o False|Si se define en True (valor predeterminado), los ensamblados se instalan en la caché de ensamblados global (GAC) del equipo local al implementar el ensamblado.|  
    |Reiniciar instancias de Host|True o False|Si se define en True, se reinician de forma automática todas las instancias de host que se ejecutan en el equipo local cuando el ensamblado se vuelve a implementar. En cambio, si se define en False (valor predeterminado), debe reiniciar manualmente las instancias de host al volver a implementar un ensamblado. **Nota:** si está volviendo a implementar ensamblados desde el nivel de solución, instancias de host se reiniciará una vez para cada proyecto que tenga esta opción se establece en True. Esto puede ocasionar varios reinicios. Si tiene intención de volver a implementar desde el nivel de solución, se recomienda establecer esta propiedad en True en solo un proyecto de la solución para evitar que la instancia de host se reinicie varias veces. Esto debe establecerse en el último proyecto que se vaya a volver a implementar en la solución. Además, si se detiene una instancia de host cuando esté llevando a cabo la nueva implementación, no se iniciará.|  
    |Habilitar pruebas de unidades|True o False|Especifica si se deben habilitar las pruebas de unidades para el proyecto.|  
  
4.  Repita los pasos 1, 2 y 3 para cada proyecto de la solución.  
  
 El proceso de implementación necesita que el ensamblado esté firmado de forma segura. Esto se consigue al asociar el proyecto con un archivo de clave de ensamblado de nombre seguro. Si aún no lo ha hecho, siga el procedimiento siguiente para generar un archivo de clave de ensamblado de nombre seguro.  
  
###### <a name="to-create-a-strong-name-assembly-key-file"></a>Para crear un archivo de clave de ensamblado de nombre seguro  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
2.  En el símbolo del sistema, desde la carpeta donde desea almacenar el archivo de clave, escriba el comando siguiente y, a continuación, presione ENTRAR:  
  
     **sn -k***file_name* **.snk**   
  
     Ejemplo: **sn -k ErrorHandling.snk**  
  
     Un mensaje de confirmación, **escribe en el par de claves \<**  *file_name***> .snk** `,` muestra en la línea de comandos.  
  
 A continuación, necesita asociar cada proyecto de la solución al archivo de clave.  
  
###### <a name="to-associate-your-projects-with-the-key-file"></a>Para asociar proyectos al archivo de clave  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **propiedades**.  
  
2.  Haga clic en el **firma** ficha en el Diseñador de proyectos.  
  
3.  En el panel derecho, compruebe el **firmar el ensamblado** cuadro.  
  
4.  Haga clic en el cuadro de lista desplegable en **elegir un archivo de clave de nombre seguro**, haga clic en  **\<Examinar... >**y, a continuación, busque el archivo de clave.  
  
5.  Haga clic en el archivo de clave y haga clic en **abiertos**.  
  
6.  Repita los pasos del 1 al 5 para cada proyecto de su solución.  
  
 Ahora puede generar e implementar todos los ensamblados de la solución en un solo paso, como se explica a continuación.  
  
###### <a name="to-deploy-the-assemblies-in-a-solution"></a>Para implementar los ensamblados en una solución  
  
-   En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en la solución y, a continuación, haga clic en **implementar solución**.  
  
     El estado del proceso de generación e implementación se muestra en la esquina inferior izquierda de la página. Si utiliza la solución de ejemplo ErrorHandling, aparecerán varios mensajes de advertencia en la ventana de resultados. Por lo que respecta a esta guía, puede pasarlos por alto. Cuando la implementación haya finalizado, "implementar: 2 se realizó correctamente, 0 incorrectos, 0 omitidos" se muestra en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de salida.  
  
 Al implementar los ensamblados de BizTalk, éstos se registran como parte de la aplicación de BizTalk especificada en la base de datos de administración de BizTalk. También rellena la base de datos con todos los elementos, o *artefactos*, que se encuentra en los ensamblados. Si la aplicación no existía antes de la implementación, en este paso también se crea una aplicación nueva. Ahora puede ver la aplicación de BizTalk y sus artefactos desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el equipo de desarrollo.  
  
###### <a name="to-view-the-biztalk-application-and-its-artifacts"></a>Para ver la aplicación de BizTalk y sus artefactos  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la carpeta de la aplicación en la que acaba de implementar los ensamblados.  
  
4.  Haga clic en las carpetas situadas debajo de la carpeta de la aplicación para ver su contenido. En las carpetas adecuadas, debería ver los artefactos incluidos en los ensamblados que ha implementado. Si ha implementado la solución de ejemplo ErrorHandling de BizTalk, debería ver artefactos en las carpetas Orquestaciones, Esquemas y Recursos. Puede haga clic en un artefacto y haga clic en **propiedades** para ver su configuración.  
  
5.  Expanda el **recursos** carpeta, haga clic en uno de los ensamblados y, a continuación, haga clic en **modificar**.  
  
6.  En el **opciones** cuadro, tenga en cuenta las opciones de implementación que están configuradas para el ensamblado.  
  
7.  En **ubicación de destino**, tenga en cuenta la ruta de acceso a la ubicación donde se copiará el archivo de ensamblado cuando se instala la aplicación. Es la ubicación de origen del ensamblado de forma predeterminada.  
  
> [!NOTE]
>  Si la aplicación no aparece, haga clic en **grupo de BizTalk** y haga clic en **actualizar**.  
  
 Para obtener más información sobre cómo implementar ensamblados, vea [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  
  
#### <a name="3-configure-the-application"></a>3. Configurar la aplicación  
 Desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede configurar la aplicación mediante la creación, agregación y configuración de artefactos.  
  
 Para que una aplicación funcione, es necesario que esté configurada de forma correcta. Por ejemplo, las orquestaciones deben estar enlazadas a un host y deben disponer de puertos de envío y ubicaciones de recepción configurados. Si ha implementado la solución de ejemplo ErrorHandling, observará que la aplicación no tiene puertos de envío ni de recepción, ni ubicaciones de recepción. Esto implica que las orquestaciones no pueden enviar ni recibir mensajes. En este tutorial no se abarcan las instrucciones necesarias para configurar aplicaciones. Sin embargo, si quiere hacerlo, lo más rápido es utilizar el cuadro de diálogo Configurar aplicación, al que tiene acceso al hacer clic con el botón secundario en la aplicación y, después, al hacer clic en Configurar. Para obtener más información, consulte [cómo configurar una aplicación](../core/how-to-configure-an-application.md). Como complemento a este respecto, también puede configurar orquestaciones, así como crear, configurar y eliminar puertos de envío, grupos de puertos de envío, puertos de recepción y ubicaciones de recepción de forma individual. Para obtener más información, vea los temas correspondientes en [administrar artefactos](../core/managing-artifacts.md).  
  
 Quizás desee también agregar artefactos a la aplicación, como por ejemplo secuencias de comandos previas o archivos Léame, o bien quitar artefactos. Puede probar esta funcionalidad mediante los procedimientos siguientes. (El ejemplo ErrorHandling no incluye artefactos adicionales para agregar; no obstante, puede probar esta funcionalidad si agrega elementos que pueden existir ya en su entorno.)  
  
> [!NOTE]
>  Puede utilizar secuencias de comandos previas y posteriores al procesamiento para realizar acciones antes o después de la importación, instalación o desinstalación de la aplicación. Por ejemplo, puede que quiera utilizar una secuencia de comandos previa al procesamiento para desinstalar los ensamblados de la GAC tras la desinstalación. Para obtener más información, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).  
  
###### <a name="to-add-an-artifact-to-an-application"></a>Para agregar un artefacto a una aplicación  
  
1.  Abra la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Para agregar los siguientes tipos de artefactos, haga clic en la carpeta de aplicación ErrorHandling y, a continuación, haga clic en **agregar**. Observe que al agregar un ensamblado de BizTalk, los artefactos que contiene también se agregan a las carpetas adecuadas de la aplicación.  
  
    -   Ensamblados de BizTalk  
  
    -   Secuencias de comandos previas al procesamiento  
  
    -   Scripts posteriores al procesamiento  
  
    -   Recursos (ensamblados de BizTalk, ensamblados .NET, secuencias de comandos previas al procesamiento, secuencias de comandos posteriores al procesamiento, archivos, certificados, componentes COM, artefactos de BAM, archivos de enlace y directorios virtuales)  
  
    -   Directivas  
  
 También puede quitar un artefacto de una aplicación.  
  
###### <a name="to-remove-an-artifact-from-an-application"></a>Para quitar un artefacto de una aplicación  
  
1.  Abra la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la carpeta que contiene el artefacto, haga clic en el artefacto y, a continuación, haga clic en **quitar**.  
  
 Para obtener más información acerca de cómo configurar la aplicación, consulte [crear y modificar las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md).  
  
#### <a name="4-export-the-application"></a>4. Exportar la aplicación  
 Una vez que haya creado una aplicación de BizTalk y que la haya modificado como corresponda, puede exportarla mediante el Asistente para exportar archivos MSI disponible en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Este asistente generará un archivo MSI que podrá importar después a otro grupo de BizTalk para volver a crear la aplicación en el grupo nuevo. Para poder ejecutar la aplicación en un servidor concreto, también deberá instalarla de forma local desde el archivo MSI.  
  
###### <a name="to-export-the-application"></a>Para exportar la aplicación:  
  
1.  Abra la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Haga clic en la aplicación de BizTalk, seleccione **exportar**y, a continuación, haga clic en **archivo MSI**.  
  
4.  En el **éste es el Asistente para exportar archivos MSI** página, haga clic en **siguiente**.  
  
5.  En el **seleccionar recursos** , seleccione los recursos para exportar al archivo .msi y, a continuación, haga clic en **siguiente**. Para los fines de este tutorial, puede aceptar los valores predeterminados.  
  
6.  Si se le pide, en la **especificar Hosts de ISS** página, escriba el nombre del servidor del equipo que hospeda el directorio virtual que desea incluir y, a continuación, haga clic en **siguiente**. Se le pedirá que especifique el servidor sólo si el directorio virtual no se ha agregado previamente a la base de datos de administración de BizTalk, como cuando se agregó a la aplicación o se importó a una aplicación.  
  
    > [!NOTE]
    >  No hay directorios virtuales en la solución de ejemplo ErrorHandling.  
  
7.  En el **dependencias** página, revise las dependencias de la aplicación y, a continuación, haga clic en **siguiente**.  
  
8.  En el **destino** página **nombre de la aplicación de destino**, escriba el nombre de la aplicación.  
  
9. En **archivo MSI para generar**, escriba la ruta de acceso completa para el archivo .msi y, a continuación, haga clic en **exportar**. Ejemplo: C:\MSI\Errorhandling.msi  
  
    > [!NOTE]
    >  Se recomienda almacenar los archivos .msi en una carpeta segura.  
  
10. En el **resumen** página, tome nota de la ubicación del archivo de registro para esta operación y, a continuación, haga clic en **finalizar**.  
  
 En el sistema de archivos, compruebe que el archivo MSI se ha creado en la ubicación especificada.  
  
> [!NOTE]
>  Por motivos de seguridad, las contraseñas se quitan de los enlaces de aplicación durante la exportación de la aplicación. Después de instalar la aplicación desde el archivo .msi, deberá volver a configurar las contraseñas para que funcione la aplicación. No obstante, las contraseñas no se quitan de ningún archivo de enlace que se haya agregado a la aplicación.  
  
 Para obtener más información acerca de cómo exportar las aplicaciones y artefactos, vea [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
#### <a name="5-import-and-install-the-application"></a>5. Importar e instalar la aplicación  
 El paso siguiente consiste en la importación de la aplicación desde el archivo MSI, que acaba de generar, en un grupo de BizTalk, así como en la instalación de la aplicación en el equipo local. Para ello, puede usar el Asistente para importación de MSI y el Asistente para la instalación disponibles en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  La aplicación se debe instalar en cada equipo del grupo que ejecutará la aplicación. Puede hacer doble clic en el archivo MSI para instalarla en otros equipos.  
  
 Puede repetir las tareas descritas en este paso siempre que quiera migrar una aplicación de un grupo de BizTalk a otro, como puede ser la migración de un entorno de desarrollo a un entorno de prueba, de un entorno de prueba a un entorno de ensayo o de un entorno de ensayo a un entorno de producción.  
  
 Llegados a este punto, si sólo está utilizando un equipo para este tutorial, debería eliminar la aplicación del grupo de BizTalk. También debería eliminar los ensamblados de la caché de ensamblados global (GAC). De este modo, al importar la aplicación podrá comprobar si se ha vuelto a crear de forma correcta. En cambio, si utiliza varios equipos para este tutorial, no es necesario que realice estas tareas enunciadas.  
  
###### <a name="to-delete-the-application-from-the-biztalk-group"></a>Para eliminar la aplicación del grupo de BizTalk:  
  
1.  Abra la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  Haga clic en la aplicación y haga clic en **eliminar**.  
  
###### <a name="to-delete-assemblies-from-the-gac"></a>Para eliminar ensamblados de la GAC  
  
1.  En el sistema de archivos, desplácese a %systemdrive%\Windows\Assembly.  
  
2.  Haga clic en cada archivo de ensamblado que se generó para la solución, haga clic en **desinstalar**y, a continuación, haga clic en **Sí** para confirmar. Por ejemplo, los archivos de ensamblado asociados al proyecto ErrorHandling son ErrorHandling.ErrorHandler y ErrorHandling.PipelinesAndSchemas.  
  
     ![Eliminar un ensamblado de la GAC](../core/media/deleteassembly.gif "DeleteAssembly")  
  
 Ahora ya puede importar la aplicación a un grupo de BizTalk. Si desea importar la aplicación a un grupo de BizTalk que se encuentra en otro equipo, es necesario que se pueda tener acceso al archivo MSI desde el otro equipo.  
  
> [!CAUTION]
>  Antes de instalar aplicaciones, asegúrese de que ha recibido el archivo MSI de una fuente de confianza. Un usuario malintencionado puede incluir un código en el archivo MSI que tenga un efecto no deseado en el sistema o en la red. Para obtener más información, consulte [seguridad y Windows Installer](../core/security-and-windows-installer.md).  
  
###### <a name="to-import-and-install-the-application"></a>Para importar e instalar la aplicación  
  
1.  Abra la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para la instancia de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la que desea importar la aplicación. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y, a continuación, expanda **grupo de BizTalk**.  
  
3.  Haga clic en **aplicaciones**, seleccione **importación**y, a continuación, haga clic en **archivo MSI**.  
  
4.  En el **Asistente para importar** página **archivo MSI para importar**, escriba la ruta de acceso completa del archivo .msi y, a continuación, haga clic en **siguiente**. Ejemplo: C:\msi\MyApplication.msi  
  
5.  En el **configuración de la aplicación** página **aplicaciones disponibles para agregar referencias a**, seleccione las aplicaciones que se va a agregar referencias y, a continuación, haga clic en **siguiente**. Si utiliza la solución de ejemplo ErrorHandling, puede aceptar los valores predeterminados.  
  
     ![Agregue referencias a una aplicación](../core/media/appreferences.gif "AppReferences")  
  
6.  En el **configuración del entorno de destino de aplicación** página, confirme que  **\<predeterminado >** está seleccionada y haga clic en **siguiente**.  
  
7.  En el **resumen de importación** página, confirme que la información de resumen es correcta y, a continuación, haga clic en **importación**.  
  
8.  En la pantalla final del Asistente para importación de MSI, seleccione **ejecutar el Asistente para instalación de aplicaciones para instalar la aplicación en el equipo local**y, a continuación, haga clic en **finalizar**.  
  
     ![Iniciar instalación del Asistente para importar](../core/media/startinstallation.gif "StartInstallation")  
  
9. En el **seleccionar la carpeta de instalación** página **carpeta**, escriba la ruta de acceso de instalación para la aplicación de BizTalk y, a continuación, haga clic en **siguiente**.  
  
10. Haga clic en **siguiente** en las siguientes tres páginas para continuar con la instalación.  
  
     Windows Installer instalará la aplicación en el equipo local.  
  
11. En el **instalación finalizada** página, haga clic en **cerrar**.  
  
 Para obtener más información acerca de cómo importar aplicaciones, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). Para obtener más información acerca de cómo instalar aplicaciones, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).  
  
 A continuación, puede comprobar si la aplicación se ha importado e instalado mediante la comprobación de los siguientes aspectos:  
  
-   La aplicación y todos sus artefactos existen en la carpeta de la aplicación en la consola de administración.  
  
-   Los ensamblados de la aplicación se encuentran en la GAC.  
  
-   Los archivos asociados a la aplicación existen en la ruta especificada durante la instalación de la aplicación.  
  
-   La aplicación aparece en Agregar o quitar programas en el Panel de control.  
  
-   Si ha configurado la aplicación para que funcione, mediante la especificación de envío y puertos de recepción, ahora puede iniciar la aplicación haciendo clic en él y, a continuación, haga clic en **iniciar**. En cambio, de forma predeterminada, la aplicación de ejemplo ErrorHandling no está configurada para funcionar y no podrá iniciarla a menos que la configure manualmente.  
  
-   Para quitar completamente la aplicación desde el grupo de BizTalk y el equipo local, siga las instrucciones de [anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md).  
  
## <a name="see-also"></a>Vea también  
[Descripción de la implementación de aplicaciones de BizTalk y administración](../core/understanding-biztalk-application-deployment-and-management.md)