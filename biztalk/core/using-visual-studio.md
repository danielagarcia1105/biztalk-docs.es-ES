---
title: Con Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio
ms.assetid: 1ef68df2-5205-4d96-9e0f-0ae78800a121
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b48f5aca0bd1e5c17d942e332f7f3d223d752b67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-visual-studio"></a>Usar Visual Studio
Dentro del sistema del proyecto de BizTalk, es posible utilizar muchas de las herramientas disponibles en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], así como herramientas diseñadas específicamente para crear aplicaciones que se ejecuten en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este tema se describen algunos de los procedimientos habituales que se pueden utilizar para crear una aplicación que se ejecute en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Cuando utiliza el sistema del proyecto de BizTalk, emplea muchos de los mismos componentes de la interfaz de usuario, como el Explorador de soluciones y la ventana Propiedades, para crear la aplicación. Además, existen componentes, como el Editor de BizTalk, que están disponibles después de instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Aunque puede utilizarlos con cualquier sistema del proyecto, estos componentes de interfaz de usuario particulares de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permiten específicamente generar aplicaciones que se ejecuten en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Aunque el sistema del proyecto de BizTalk utiliza muchos de los mismos menús y comandos de menú que otros sistemas del proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], algunos comandos son nuevos, otros no están disponibles, o bien estarán expandidos o restringidos cuando utilice el sistema del proyecto de BizTalk. En este tema se describen los diferentes menús disponibles en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y cómo interactúan con el sistema del proyecto de BizTalk.  
  
> [!NOTE]
>  Los siguientes temas se centran en mostrar los menús y elementos de menú que se comportan de manera diferente que en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="file-menu"></a>Menú Archivo  
 La mayoría de los **archivo** comandos de menú funcionan del mismo modo para proyectos de BizTalk que en otros [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyectos. Algunos comandos no se admiten o no están disponibles al trabajar con proyectos de BizTalk. Por ejemplo, el **impresión** comando no se admite cuando se trabaja con canalizaciones.  
  
## <a name="view-menu"></a>Menú Ver  
 En la tabla siguiente se enumera ventanas de sistema del proyecto de BizTalk, las barras de herramientas y cuadros de herramientas disponibles en la **vista** menú.  
  
|Nombre de submenú|Nombre de submenú (si corresponde)|Description|  
|------------------|------------------------------------|-----------------|  
||||  
|**Otras ventanas**|**Vista orquestación**|La vista orquestación es una ventana disponible que permite agregar, eliminar y examinar parámetros de orquestaciones, puertos y tipos de puertos, mensajes y tipos de mensajes de varias partes, conjuntos y tipos de correlaciones, vínculos de roles y tipos de vínculos de roles, ámbitos y propiedades de orquestaciones. **Nota:** esta ventana solo está disponible en una orquestación abierta.|  
|**Otras ventanas**|**Editor de expresiones**|El Editor de expresiones es una ventana disponible que actúa como editor de texto estándar de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] con IntelliSense y que permite escribir expresiones complejas.|  
|**Cuadro de herramientas**|**Componentes de canalización de BizTalk**|Esta es una lista de los componentes de canalización que puede arrastrar a la superficie de diseño de canalización. solo puede agregar los componentes de canalización que estén disponibles a su canalización activa.|  
|**Cuadro de herramientas**|**Orquestaciones de BizTalk**|Esta es una lista de las formas de orquestación que puede arrastrar a la superficie de diseño de orquestación.|  
|**Cuadro de herramientas**|**Asignador de BizTalk**|Esta es una lista de los functoids que puede arrastrar a la superficie de cuadrícula de asignación. Los functoids se agrupan por funciones.|  
|**Barras de herramientas**|**Editor de BizTalk**|Herramienta visual que simplifica el proceso de creación de esquemas de documentos estructurados, especificado en lenguaje de definición de esquemas XML (XSD), para formatos XML y otros distintos.|  
|**Barras de herramientas**|**Asignador de BizTalk**|Herramienta gráfica de interfaz de usuario que simplifica el proceso de especificar la transformación de un documento XML, según dos esquemas creados con el Editor de BizTalk, produciendo una hoja de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT) como salida compilada.|  
  
## <a name="project-menu"></a>Menú Proyecto  
 En la tabla siguiente se enumera algunos de los comandos de la **proyecto** menú.  
  
|Nombre de submenú|Description|  
|------------------|-----------------|  
|**Agregar referencia**|Utilice este elemento de menú para hacer referencia a otros proyectos y a otros proyectos .NET o COM.|  
|**Agregar referencia de servicio**|Use este elemento de menú para agregar referencias de servicio de WCF. También usa este elemento para agregar referencias Web haciendo clic en **avanzadas** en el **Agregar referencia de servicio** cuadro de diálogo.|  
|**Agregar elementos generados**|Use este elemento de menú para agregar un archivo de esquema o un adaptador generado o para consumir un servicio WCF.|  
|**Agregar referencia de servicio de adaptador**|Utilice este elemento de menú para examinar (y buscar) metadatos y generar clases de proxy de .NET CLR usando las operaciones seleccionadas o tipos. **Nota:** este elemento aparece en solo si de menú de BizTalk al menos un adaptador (incluidos con [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]) está instalado en el equipo.|  
|**Agregar utilizar referencia de adaptador**|Utilice este elemento de menú para examinar (y buscar) metadatos de adaptador y, a continuación, generar esquemas XML para las operaciones seleccionadas. **Nota:** este elemento aparece en solo si de menú de BizTalk al menos un adaptador (incluidos con [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]) está instalado en el equipo.|  
  
 Para obtener información sobre cómo agregar referencias Web para servicios Web de BizTalk, consulte [agregar referencias Web](../core/adding-web-references.md).  
  
## <a name="build-menu"></a>Menú Generar  
 El **generar** menú contiene los comandos de compilación. También contiene el comando para ejecutar **Configuration Manager** establecer opciones de configuración de compilación e implementación. Para implementar un proyecto, haga clic en el proyecto en el Explorador de soluciones, a continuación, haga clic en el **implementar** comando. Este método de implementación debe utilizarse solamente cuando esté desarrollando la aplicación o si tiene un escenario simple. El método de implementación no **no** realizar un seguimiento de versiones y es posible sobrescribir fácilmente versiones anteriores de un ensamblado. Volver a utilizar la misma versión es útil en una fase de desarrollo o de comprobación, pero no en el entorno de producción. Para obtener información acerca de la implementación, consulte [implementación de aplicación de BizTalk de descripción y administración](../core/understanding-biztalk-application-deployment-and-management.md).  
  
 Para agregar artefactos de BizTalk a la base de datos de administración de BizTalk, ejecute el Asistente para implementar ensamblados. Para obtener más información sobre el Asistente para la implementación de ensamblados, vea [cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).  
  
> [!NOTE]
>  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]contiene una versión de Dotfuscator que tomará un ensamblado compilado y lo ofusca Renombrando los símbolos y otros identificadores en un esfuerzo para proteger los derechos de propiedad intelectual. Los ensamblados que se ejecutan mediante esta herramienta no se pueden implementar.  
  
## <a name="debug-menu"></a>Menú Depurar  
 El sistema de proyectos de BizTalk es compatible con la **depurar** comandos de menú. Para obtener información sobre la depuración en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [depurar orquestaciones](../core/debugging-orchestrations.md).  
  
## <a name="biztalk-menu"></a>Menú BizTalk  
 Cuando se trabaja con un proyecto, el **BizTalk** menú aparece al abrir el Editor de BizTalk o el asignador de BizTalk o el Diseñador de orquestaciones de BizTalk. En otras palabras, el menú BizTalk aparece cuando intenta editar un esquema o una asignación o una orquestación.  
  
> [!NOTE]
>  Quizá pueda obtener acceso al Diseñador de orquestaciones, al Editor de BizTalk y al Asignador de BizTalk desde otros sistemas del proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]; sin embargo, el comportamiento de estas herramientas de BizTalk puede ser imprevisible. Debe utilizar el Diseñador de orquestaciones, el Editor de BizTalk y el Asignador de BizTalk en el contexto de un proyecto de BizTalk.  
  
## <a name="help-menu"></a>Menú Ayuda  
 En la tabla siguiente se enumera algunos de los comandos de la **ayuda** menú relacionadas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
|Comando de menú|Description|  
|------------------|-----------------|  
|**Ayuda dinámica**|Este comando de menú abre la **Ayuda dinámica** ficha que genera dinámicamente temas en función de la tarea.|  
|**Contenido**|Este comando de menú abre la **contenido** pestaña y muestra todas las colecciones de Ayuda instaladas. Para ver el contenido debe tener instalada la documentación de los productos Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|**Acerca de Microsoft BizTalk Server**|Este comando de menú abre la **acerca de Microsoft BizTalk Server** cuadro de diálogo. Este cuadro de diálogo muestra la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] información del producto.|  
|**Index**|El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación de ayuda no es accesible a través del índice en esta versión.|  
|**Buscar**|No hay ningún filtro para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda documentación en esta versión, pero si selecciona **(sin filtro)** en el **filtrados por** la lista desplegable, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación de ayuda está disponible para realiza una búsqueda.|  
  
## <a name="property-pages"></a>Páginas de propiedades  
 Las páginas de propiedades del Diseñador de proyectos se usan para configurar las propiedades del proyecto de ensamblado y las propiedades de implementación para el proyecto de BizTalk.  
  
### <a name="procedures"></a>Procedimientos  
  
##### <a name="to-configure-assembly-project-properties"></a>Para configurar las propiedades del proyecto de ensamblado  
  
1.  En el Explorador de soluciones, seleccione el proyecto.  
  
2.  En el **proyecto** menú, haga clic en **propiedades** para activar el Diseñador de proyectos.  
  
3.  Haga clic en el **aplicación** ficha.  
  
4.  Haga clic en **información de ensamblado** y actualizar las propiedades del ensamblado que desee.  
  
    > [!NOTE]
    >  Use la **firma** ficha en el Diseñador de proyectos para especificar la ubicación de archivo de clave para el ensamblado si está utilizando certificados con la aplicación que se ejecuta en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##### <a name="to-configure-deployment-properties"></a>Para configurar propiedades de implementación  
  
1.  Seleccione el proyecto para el que desea configurar las propiedades de implementación.  
  
2.  En el **proyecto** menú, haga clic en **propiedades** para activar el Diseñador de proyectos.  
  
3.  Haga clic en el **implementación** pestaña y actualice las propiedades de implementación.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas de desarrollo](../core/developer-tools.md)