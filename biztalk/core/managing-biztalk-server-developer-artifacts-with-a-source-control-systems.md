---
title: Administrar artefactos del programador de BizTalk Server con un origen de sistemas de Control | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce25b112-38c9-40c8-9a5f-a2855572aabb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ce9483518275c57c7defb730aeeffc8a4139115
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991013"
---
# <a name="managing-biztalk-server-developer-artifacts-with-a-source-control-systems"></a>Administración de artefactos de programadores de BizTalk Server con sistemas de control de código fuente
Proteger su proyecto de BizTalk de errores inesperados del sistema debería ser un tema de máxima prioridad. Una manera de proteger los archivos del proyecto es usar un sistema de control de código fuente, por ejemplo, Team Foundation Server Source Control y Microsoft Visual SourceSafe. En este tema se analizan algunas estrategias básicas para organizar proyectos con el fin de que funcionen mejor con un sistema de control de código fuente, y proporciona algunas sugerencias específicas para usar Visual SourceSafe.  
  
## <a name="basic-organization-strategies"></a>Estrategias básicas de organización  
 Puede seguir algunas estrategias básicas de organización independientemente del sistema de control de fuente que utilizará en última instancia. Estas estrategias garantizan que la estructura del archivo del proyecto de BizTalk está organizada para realizarle el control de código de fuente y de desarrollo.  
  
### <a name="use-a-consistent-folder-structure-for-solutions-and-projects"></a>Utilizar una estructura de carpetas coherente para soluciones y proyectos  
 Es más fácil de administrar el desarrollo en un entorno de equipo si se utiliza en todo el equipo una estructura común para almacenar proyectos y soluciones de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Esto ocurre especialmente cuando cada proyecto de BizTalk genere y utilice archivos como archivos de enlace que necesitarán los equipos de generación, prueba e implementación.  
  
 Suele resultar sencillo comenzar la implementación sin normalizar las estructuras de las carpetas. Inevitablemente llevará más tiempo posteriormente ya que es necesario “revisar” los vínculos del proyecto y el aprovechamiento de la prueba a medida que se desarrolla la solución.  
  
### <a name="keep-source-control-and-file-system-structures-identical"></a>Mantener idénticas las estructuras del sistema de archivos y del control de fuente  
 Para simplificar la administración de varios entornos de programadores, configure la estructura de una carpeta en el sistema de control de fuente que coincida con la estructura del sistema de archivos local. Le ayudará a garantizar que un programador pueda obtener simplemente una última versión y saber que la estructura del disco cumple los estándares del equipo.  
  
### <a name="define-and-use-a-common-root-folder"></a>Definir y utilizar una carpeta raíz común  
 Se recomienda guardar todos los requisitos y códigos de proyecto en una única carpeta raíz que, a su vez, se puede crear en todos los equipos de los programadores. Cuando todos los programadores utilizan la misma raíz, se simplifica la administración de los artefactos de desarrollo y el mantenimiento de una configuración coherente. Por ejemplo, si crea una carpeta raíz $/SysInteg2009 en Visual SourceSafe, todos los programadores pueden crear C:\SysInteg2009 en sus sistemas de archivos locales.  
  
### <a name="create-a-master-solution-that-will-hold-all-projects"></a>Crear una solución principal que contenga todos los proyectos  
 Normalmente, se utilizará la solución principal como la solución de generación principal. Se recomienda en proyecto de BizTalk de complejidad media o alta.  
  
### <a name="store-all-biztalk-projects-under-the-master-solution"></a>Almacenar todos los proyectos de BizTalk en la solución principal  
 Resulta útil organizar todos los proyectos de BizTalk en la misma solución principal. La estructura del sistema de control de fuente debería reflejar esta jerarquía.  
  
### <a name="divide-the-folder-structure-into-shared-and-process-specific-sections"></a>Dividir la estructura de carpetas en sección Compartida y en sección Específica del proceso  
 Al crear la estructura de archivos, normalmente se divide la estructura de la carpeta para separar las entidades compartidas de las entidades específicas del proceso. Las entidades compartidas son comunes de varios proyectos y pueden incluir clases auxiliares.  
  
 Por ejemplo, las tres primeras carpetas de la siguiente lista están organizadas por entidad compartida, mientras que las dos últimas están organizadas por proceso empresarial:  
  
 C:\SysInteg2009\\_Master_Solution\Shared\  
  
 C:\SysInteg2009\\_Master_Solution\Shared\EmailHelper  
  
 C:\SysInteg2009\\_Master_Solution\Shared\SharedSchema  
  
 C:\SysInteg2009\\_Master_Solution\AccountRequest\  
  
 C:\SysInteg2009\\_Master_Solution\AccountValidate\  
  
### <a name="separate-pipeline-projects-into-distinct-projects"></a>Dividir proyectos de canalizaciones en proyectos distintos  
 Durante el desarrollo de los componentes de canalización, un requisito habitual suele ser modificar y volver a probar una canalización independientemente del resto de la solución. Por esta razón suele ser útil conservar las soluciones de canalización como un proyecto diferente de BizTalk, que da lugar a un ensamblado de canalización diferente que se puede quitar y volver a implementar sin necesidad de volver a enlazar el resto de la solución.  
  
 Asimismo, es una práctica habitual conservar el código que implementa las interfaces de canalización reales y la lógica de procesamiento de canalización en un proyecto diferente con una referencia del proyecto de BizTalk (que contiene archivos .btp) en [!INCLUDE[btsCSharp](../includes/btscsharp-md.md)] o en el proyecto de Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)].  
  
### <a name="keep-deployment-and-test-scripts-with-their-projects"></a>Conservar las secuencias de comandos de prueba y de implementación con sus proyectos  
 Para habilitar el desarrollo de a un proceso de implementación y de generación unificado, las secuencias de comandos de instalación y generación deberían haber sido generadas por programadores independientes, pero se deberían considerar partes reutilizables de la solución total. Si las secuencias de comandos se escriben para que sean reutilizables, tareas como la implementación de un paquete de soluciones total puede volver a utilizar las secuencias de comandos. Por ejemplo, si las secuencias de comandos de implementación y anulación de la implementación aceptan parámetros para determinar las rutas de DLL y las ubicaciones de carpeta de archivos de enlace, las secuencias de comando se pueden volver a utilizar cuando los ensamblados compilados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se encuentren en una ubicación diferente.  
  
 Con este enfoque, los programadores agregan las secuencias de comandos de instalación para sus procesos específicos en la carpeta y, a continuación, se puede escribir fácilmente un único proceso para realizar una implementación total de todos los procesos.  
  
### <a name="use-unique-strong-name-keys-when-appropriate"></a>Utilizar claves de nombre seguro único cuando corresponda  
 Normalmente, una solución de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] utiliza un archivo de clave única. La razón es que la solución se trata como una entidad única y se administra como tal. Si la solución empresarial que se está desarrollando está realmente compuesta por dos partes diferentes o más, tenga en cuenta si se deberían utilizar los dos archivos de clave. Varias claves de este escenario permiten que se puedan tratar las partes como entidades independientes en el futuro, por ejemplo, con rutas de actualización distintas.  
  
 Para proyectos auxiliares se aplican las mismas consideraciones. Si el proyecto auxiliar es (o será) una entidad diferente, se debería generar mediante una clave de nombre seguro diferente.  
  
### <a name="put-dependent-dlls-into-a-separate-folder"></a>Poner DLL dependiente en una carpeta diferente  
 Al crear la estructura de carpeta, es útil crear una carpeta común que contenga los archivos DLL a los que se hace referencia como dependencias de archivos. Si se garantiza que los programadores seguirán la misma estructura de carpetas, las referencias de archivo no se dividirán cuando se muevan las soluciones entre programadores y estaciones de trabajo.  
  
### <a name="keep-test-messages-in-a-msgs-folder"></a>Mantener mensajes de prueba en una carpeta “Msgs”  
 Cuando se desarrollan esquemas y se utilizan mensajes, es habitual realizar un esfuerzo considerable en probar muchos mensajes de ejemplo diferentes con respecto a un esquema XML y a procesos de orquestación.  
  
 En una solución real, los mensajes de ejemplo son un valioso activo porque contienen datos significativos para la solución empresarial. Los valores aleatorios o ficticios del mismo mensaje normalmente harán que se produzca un error en el proceso. Por esta razón, los mensajes de ejemplo se deberían tratar con el mismo cuidado que el código de la solución.  
  
 Para facilitar la administración de archivos de mensaje, mantenga los mensajes de prueba en una carpeta específica denominada “msgs”. En los casos en los que haya tanto “instancias generadas” y “mensajes de ejemplo” (por ejemplo, mensajes de un sistema existente), resulta útil mantener estos mensajes aparte para permitir realizar una comparación entre el esquema desarrollado y los datos reales.  
  
 En un proyecto de integración es habitual tener varias versiones de esquemas y, por lo tanto, varias versiones de los archivos de mensaje. Para distinguir los mensajes de ejemplo, utilice números de versiones cuando les dé nombre a los archivos.  
  
### <a name="managing-other-files"></a>Administrar otros archivos  
 Algunos tipos de archivos se pueden agrupar y almacenar en una carpeta distinta, mientras que otros se pueden almacenar con otros archivos en una carpeta común. Redacte una directiva acerca de cómo tratar cada tipo de archivo y seguirlo consistentemente.  
  
## <a name="working-with-biztalk-server-and-visual-sourcesafe"></a>Trabajar con BizTalk Server y Visual SourceSafe  
 En esta sección se describen algunas consideraciones para trabajar con Visual SourceSafe, como el control de Unicode, mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para el control de fuente, momento de la comprobación, el control de versiones y otros asuntos.  
  
### <a name="solution-character-sets"></a>Juegos de caracteres de la solución  
 Existe una conocida limitación con Visual SourceSafe relacionada con el control de archivos Unicode. Cuando se trabaja con soluciones de BizTalk, es necesario impedir que Visual SourceSafe dañe los archivos Unicode de BizTalk Server.  
  
##### <a name="to-enable-visual-sourcesafe-to-work-with-biztalk-server-unicode-files"></a>Para habilitar Visual SourceSafe para que trabaje con archivos Unicode de BizTalk Server  
  
1. Inicie el administrador de Visual SourceSafe 8.0.  
  
2. Seleccione la base de datos de SourceSafe que se va a utilizar.  
  
3. En el menú **Herramientas** , haga clic en **Opciones**.  
  
4. Haga clic en el **tipos de archivo** ficha.  
  
5. Agregue lo siguiente al final de la lista de archivos binarios. Compruebe que hay puntos y comas entre cada tipo de archivo:  
  
    *.btm; \*.btp; \*.xsd; \*.odx  
  
6. Haga clic en **Aceptar**.  
  
   Visual SourceSafe no inspeccionará los archivos de BizTalk Server y no intentará cambiar su formato.  
  
### <a name="use-visual-studio-for-source-control-operations"></a>Usar Visual Studio para las operaciones de control de código fuente  
 Cualquier manipulación o creación de proyectos en Visual SourceSafe se debería desarrollar mediante los menús integrados de soporte de Visual SourceSafe existentes en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. No utilice el Explorador de Visual SourceSafe para realizar estas operaciones.  
  
### <a name="when-to-check-in-biztalk-server-projects"></a>Cuándo controlar proyectos de BizTalk Server  
 El enfoque que se recomienda para utilizar Visual SourceSafe implica controlar el código solo cuando haya pasado correctamente las pruebas funcionales y el programador esté seguro de que el código se generará correctamente sin interrumpir ningún código que esté relacionado. Aplicar este modelo a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] supone las directrices siguientes:  
  
- Los proyectos de BizTalk que contengan solo esquemas de mensaje no se deberían controlar hasta que los esquemas se hayan probado y hayan dado resultados positivos con respecto a una variedad de mensajes de ejemplo.  
  
- Los proyectos de BizTalk que contengan un proceso empresarial no se deberían controlar hasta que la solución se haya probado y haya dado resultados positivos mediante los mensajes de entrada y salida correspondientes y mediante los puertos de recepción y envío correctos.  
  
- Los proyectos del servicio Web de ASP.NET no se deberían controlar hasta que el código de servicio Web se haya probado con respecto al sistema inicializado o mediante un instrumento de prueba.  
  
  Si se sigue este modelo, el repositorio de Visual SourceSafe siempre contendrá una generación que se puede probar y generar correctamente. Es principio cobra especial relevancia si hay que cumplir el enfoque de “generación nocturna”.  
  
### <a name="checking-in-intermediate-versions"></a>Controlar versiones intermedias  
 Un enfoque alternativo para controlar archivos trata de controlar las versiones “intermedias”. En este enfoque, una versión intermedia todavía no ha pasado la prueba funcional y se puede considerar “entre generaciones”. Normalmente no se recomienda este enfoque porque no cumple con el principio general de tener siempre versiones que se puedan generar en un sistema de control de fuente. Sin embargo, algunos equipos prefieren este enfoque porque permite que los programadores puedan utilizar el sistema de control de fuente para comprobar y deshacer versiones sin necesidad de cumplir los criterios de comprobación de una generación formal.  
  
 Si es necesario el enfoque de comprobar versiones intermedias, no puede suponer que el sistema de control de fuente contenga la versión “generable”. Al contrario, debe diferenciar las versiones intermedias y generar versiones. Con Visual SourceSafe puede hacerlo de muchas formas diferentes, esté basado en el proceso o sea automático. Por ejemplo:  
  
-   Los programadores siguen un proceso de notificación al administrador de la generación cuando una versión “generable” se agrega a Visual SourceSafe.  
  
-   Los programadores comprueban una versión probada, que esté lista para generase en un “área promocionada” de Visual SourceSafe. A continuación, éste área promocionada se utiliza como fuente sobre la que se basa la generación principal.  
  
-   Se pueden escribir las secuencias de comandos o códigos que utilizan las interfaces COM de Visual SourceSafe. Por ejemplo, se puede utilizar una etiqueta específica para indicar que el código está preparado para generarse, el script busca esta etiqueta y “fija” esta fuente en una rama diferente de Visual SourceSafe. Esta rama se utiliza entonces como fuete de las generaciones principales.  
  
### <a name="comparing-files"></a>Comparar archivos  
 Puede usar Visual SourceSafe para buscar las diferencias existentes entre dos versiones diferentes de un archivo de origen de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esto se puede llevar a cabo con artefactos, incluidas las asignaciones y los esquemas, archivos relacionados como mensajes de texto e incluso archivos de configuración exportados.  
  
> [!NOTE]
>  Cuando se comparan asignaciones, debe editar la asignación antes de protegerla o Visual SourceSafe realizará una comparación binaria al buscar diferencias entre esta versión y la siguiente. Esto se debe a que la información de codificación no se agrega al XML de la asignación hasta que se edita.  
  
### <a name="version-controlling-non-biztalk-server-project-files"></a>Versión que controla los archivos de proyectos que no son de BizTalk Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza archivos adicionales a los que se puede asignar una versión y los que se pueden almacenar en Visual SourceSafe de forma beneficiosa. A continuación se muestran algunos ejemplos de archivos:  
  
- Archivos de enlace (tanto de desarrollo como de prueba)  
  
- Ensamblados de canalización personalizada  
  
- Datos de prueba (por ejemplo, mensajes de prueba)  
  
- Instrumentos de prueba (que pueden variar durante el período de vida de un proyecto)  
  
- Secuencias de comandos de generación, de implementación y de inicio-apagado que puede que los equipos de desarrollo y generación tengan que compartir.  
  
  Si los archivos están relacionados con un proyecto de BizTalk específico de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], se pueden incluir en el proyecto de BizTalk y administrar mediante las funciones de control de código fuente integradas en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
##### <a name="to-include-a-file-or-folder-into-an-existing-visual-studio-project"></a>Para incluir un archivo o una carpeta en un proyecto de Visual Studio existente  
  
1.  En el Explorador de soluciones, haga clic en **mostrar todos los archivos**.  
  
2.  Seleccione la carpeta o el archivo que quiere incluir en la solución.  
  
3.  Haga clic en la carpeta o archivo y, a continuación, haga clic en **incluir en el proyecto**.  
  
> [!NOTE]
>  El Explorador de Visual SourceSafe NO se debería utilizar para administrar elementos que sean parte de un proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] bajo el control de código fuente.  
  
### <a name="checking-the-visual-sourcesafe-database"></a>Comprobar la base de datos de Visual SourceSafe  
 Cuando las bases de datos de Visual SourceSafe son grandes, se utilizan mucho o muchos usuarios obtienen acceso a ellas de forma simultánea, se recomienda que ejecute regularmente el comando "Analyze VSS DB" desde el menú de Visual SourceSafe. Si se detectan errores durante el análisis, se pueden solucionar mediante el comando “Analyze and Fix VSS DB”. Es necesario que estos dos comandos bloqueen la base de datos de Visual SourceSafe, por lo que es necesario que todos los usuarios se desconecten de Visual SourceSafe.