---
title: Utilizar el sistema del proyecto de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, opening
- BizTalk Mapper, opening
- Orchestration Designer, opening
- Pipeline Designer, opening
ms.assetid: a28c715e-128c-463a-b421-9b3efe76a530
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e55e1280f4054c431f53aa21fa16123f11509f7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-biztalk-project-system"></a>Utilizar el sistema del proyecto de BizTalk
Puede usar el sistema del proyectos de BizTalk para crear, organizar y configurar soluciones de BizTalk en el entorno de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Los temas y procedimientos de esta sección describen como realizar varias tareas mediante el sistema del proyecto de BizTalk.  
  
 El sistema de proyectos de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] usa los mismos principios y procedimientos de administración del proyecto que se usan con otros proyectos de Microsoft Build Engine (MSBuild) en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Esta sección detalla procedimientos comunes que puede usar al crear una aplicación que ejecuta Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Para obtener más información acerca de MSBuild, vea la sección de referencia de MSBuild en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection en [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).  
  
 Para obtener más información sobre el uso de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] entorno, vea "Administrar soluciones, proyectos y archivos" en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection en [http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx).  
  
 La siguiente ilustración muestra el entorno de diseño del sistema de proyecto de BizTalk con el **nuevo proyecto** cuadro de diálogo abierto.  
  
 ![Sistemas del proyecto](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")  
Representación del entorno de diseño del sistema del proyecto  
  
### <a name="to-open-biztalk-editor"></a>Para abrir el Editor de BizTalk  
  
1.  En el Explorador de soluciones, haga clic en un esquema.  
  
    > [!NOTE]
    >  Para abrir el Editor de BizTalk, en primer lugar debe crear un esquema o abrir uno previamente creado. Para obtener información acerca de cómo crear un esquema, vea [cómo crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md). Consulte también [agregar elementos de proyecto](../core/adding-project-items.md).  
  
2.  En el **vista** menú, haga clic en **abiertos**.  
  
     : "O":  
  
     Haga clic en el esquema y, a continuación, haga clic en **abiertos**.  
  
     : "O":  
  
     Haga doble clic en el esquema.  
  
     El esquema seleccionado se abre en el Editor de BizTalk.  
  
    > [!NOTE]
    >  Para crear un esquema, debe tener abierto un proyecto. Para obtener información sobre cómo crear un proyecto, vea [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md). Para obtener información sobre cómo agregar elementos a un proyecto, vea [cómo crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md). Consulte también [agregar elementos de proyecto](../core/adding-project-items.md).  
  
### <a name="to-open-biztalk-mapper"></a>Para abrir el Asignador de BizTalk  
  
1.  En el Explorador de soluciones, haga clic en una asignación.  
  
    > [!NOTE]
    >  Para abrir el Asignador de BizTalk, en primer lugar debe crear una asignación o abrir una previamente creada. Para obtener información acerca de cómo crear un mapa, consulte [cómo crear nuevas asignaciones](../core/how-to-create-new-maps.md). Consulte también [agregar elementos de proyecto](../core/adding-project-items.md).  
  
2.  En el **vista** menú, haga clic en **abiertos**.  
  
     : "O":  
  
     Haga clic en el mapa y, a continuación, haga clic en **abiertos**.  
  
     : "O":  
  
     Haga doble clic en la asignación.  
  
     Se abre la asignación seleccionada en el Asignador de BizTalk.  
  
    > [!NOTE]
    >  Para crear una asignación, debe tener abierto un proyecto. Para obtener información sobre cómo crear un proyecto, vea [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md). Para obtener información sobre cómo agregar elementos a un proyecto, vea [agregar elementos de proyecto](../core/adding-project-items.md). Consulte también [cómo crear nuevas asignaciones](../core/how-to-create-new-maps.md).  
  
### <a name="to-open-orchestration-designer"></a>Para abrir el Diseñador de orquestaciones  
  
1.  En el Explorador de soluciones, haga clic en una orquestación (.odx).  
  
    > [!NOTE]
    >  Para abrir el Diseñador de orquestaciones, en primer lugar debe crear una orquestación o abrir una previamente creada. Para obtener información sobre cómo crear una orquestación, consulte [trabaja en el Diseñador de orquestaciones](../core/working-in-orchestration-designer.md).  
  
2.  En el **vista** menú, haga clic en **abiertos**.  
  
     : "O":  
  
     Haga clic en la orquestación y, a continuación, haga clic en **abiertos**.  
  
     : "O":  
  
     Haga doble clic en la orquestación.  
  
     Se abre el Diseñador de orquestaciones.  
  
    > [!NOTE]
    >  Para crear una orquestación, debe tener abierto un proyecto. Para obtener información sobre cómo crear un proyecto, vea [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md). Para obtener información sobre cómo agregar elementos a un proyecto, vea [agregar elementos de proyecto](../core/adding-project-items.md). Consulte también [trabaja en el Diseñador de orquestaciones](../core/working-in-orchestration-designer.md).  
  
### <a name="to-open-pipeline-designer"></a>Para abrir el Diseñador de canalizaciones  
  
1.  En el Explorador de soluciones, haga clic en una canalización.  
  
    > [!NOTE]
    >  Para abrir el Diseñador de canalizaciones, en primer lugar debe crear una canalización o abrir una previamente creada. Para obtener información sobre cómo crear una canalización, consulte [cómo crear una nueva canalización](../core/how-to-create-a-new-pipeline.md).  
  
2.  En el **vista** menú, haga clic en **abiertos**.  
  
     : "O":  
  
     Haga clic en la canalización y, a continuación, haga clic en **abiertos**.  
  
     : "O":  
  
     Haga doble clic en la canalización.  
  
     Se abre el Diseñador de canalizaciones.  
  
    > [!NOTE]
    >  Para crear una canalización, debe tener abierto un proyecto. Para obtener información sobre cómo crear un proyecto, vea [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md). Para obtener información sobre cómo agregar elementos a un proyecto, vea [agregar elementos de proyecto](../core/adding-project-items.md). Consulte también [trabaja en el Diseñador de orquestaciones](../core/working-in-orchestration-designer.md).  
  
## <a name="see-also"></a>Vea también  
 [Crear orquestaciones mediante el Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md)   
 [Utilizando el Diseñador de canalizaciones](../core/using-pipeline-designer.md)   
 [Ventanas del compositor de reglas de negocios](../core/windows-of-the-business-rule-composer.md)   
 [Usar el Editor de BizTalk](../core/using-biztalk-editor.md)   
 [Con el asignador de BizTalk](../core/using-biztalk-mapper.md)   
 [Herramientas de desarrollo](../core/developer-tools.md)