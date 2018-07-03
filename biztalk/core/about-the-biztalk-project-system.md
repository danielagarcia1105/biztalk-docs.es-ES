---
title: Acerca del sistema de proyecto de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, about projects
- applications, creating
- creating, applications
- creating, business solutions
- business solutions, creating
ms.assetid: 69807e57-356e-451d-b803-4253b891b617
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43bfc47725defe70c11d0d839fb7985b91403c91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019891"
---
# <a name="about-the-biztalk-project-system"></a>Acerca del sistema de proyecto de BizTalk
El sistema del proyecto de BizTalk se usa para crear una parte o toda una aplicación o solución empresarial de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El elemento principal de una solución de este tipo es un proyecto de BizTalk, es decir, una colección de elementos como, por ejemplo, esquemas, orquestaciones, tipos de mensajes Web, clases, canalizaciones, asignaciones y referencias, que se pueden crear y generar en un ensamblado antes de implementarlo.  
  
 Una solución empresarial relativamente sencilla podría consistir en un único proyecto de BizTalk generado en un único ensamblado. Si la solución empresarial es más compleja (por ejemplo, tiene una solución que integra diversos procesos y sistemas) una posible solución de BizTalk podría contener muchos ensamblados generados a partir de otros muchos proyectos de BizTalk y que estuvieran implementados en varios equipos de servidores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!IMPORTANT]
>  No es posible utilizar comas en nombres de ensamblados.  
  
 Cuando se crea un proyecto de BizTalk, generalmente se incluye uno o más de los tipos de archivos de la siguiente lista. Estos tipos de archivos desempeñan funciones específicas en la creación de una solución; el sistema del proyecto de BizTalk proporciona una herramienta de diseño gráfico para cada una de ellas.  
  
- **Orquestaciones.** Una orquestación representa el flujo de trabajo de un proceso empresarial. El Diseñador de orquestaciones se utiliza para diseñar orquestaciones. Para obtener más información sobre el Diseñador de orquestaciones, consulte [crear orquestaciones usar diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md).  
  
- **Esquemas.** Un esquema describe la estructura de un documento XML. Los esquemas intercambian información entre aplicaciones dentro de una organización o entre socios comerciales. El Editor de BizTalk simplifica el proceso de definición de esquemas. Para obtener más información acerca del Editor de BizTalk, consulte [crear esquemas utilizando BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).  
  
- **Se asigna.** Una asignación transforma datos de un formato a otro. El Asignador de BizTalk presenta los esquemas de origen y de destino de forma adyacente, y permite definir conversiones entre los elementos de datos de diferentes mensajes. Para obtener más información sobre el asignador de BizTalk, consulte [crear mapas de uso del asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md).  
  
- **Canalizaciones.** Una canalización realiza una serie de operaciones que preparan los mensajes entrantes y salientes para su posterior procesamiento. El Diseñador de canalizaciones permite implementar operaciones tales como cifrado, descifrado, compresión, cambio de formato y validación. Para obtener más información sobre el Diseñador de canalizaciones, consulte [crear canalizaciones utilizando Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md).  
  
  Los proyectos de BizTalk son compatibles con Team Foundation Server (TFS). Para obtener más información sobre el diseño, desarrollo e implementación de soluciones en BizTalk Server junto con TFS, consulte [desarrollar soluciones de integración con BizTalk Server y Team Foundation Server](http://www.microsoft.com/downloads/details.aspx?FamilyID=ed7bd0ee-1385-4041-8f2a-354594ee88f3&DisplayLang=en).  
  
> [!IMPORTANT]
>  TFS Build expone una propiedad denominada “MSBuild Platform” que puede tener 3 valores: “Auto”, “x86” y “x64”. Para garantizar una compilación correcta, el valor de la propiedad anterior debe definirse como x86.  
  
 Los proyectos de BizTalk pueden coexistir con otros proyectos de Visual Studio. Al igual que ocurre con todos los sistemas del proyecto de Visual Studio, los proyectos de BizTalk pueden incluir otros archivos, como páginas de ASP.NET, y pueden hacer referencia a otros proyectos y ensamblados que haya creado. Para obtener más información acerca de la plantilla de proyecto de BizTalk, consulte [plantillas de proyecto de BizTalk Server](../core/biztalk-server-project-templates.md). Para obtener más información sobre cómo crear proyectos de BizTalk, consulte [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md).  
  
> [!WARNING]
>  Es posible obtener acceso a las herramientas de diseño de BizTalk desde otros sistemas del proyecto que pueda utilizar en Visual Studio, pero su comportamiento es imprevisible. Utilice el Diseñador de orquestaciones, el Diseñador de canalizaciones, el Editor de BizTalk y el Asignador de BizTalk únicamente en el contexto de un proyecto de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Crear orquestaciones mediante el Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md)   
 [Creación de esquemas con el Editor de BizTalk](../core/creating-schemas-using-biztalk-editor.md)   
 [Creación de mapas con el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)   
 [Crear canalizaciones mediante el Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md)   
 [Herramientas de desarrollo](../core/developer-tools.md)