---
title: Referencias de Namespace de BizTalk incluidos en los proyectos de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- System.Xml namespace
- Microsoft.BizTalk.GlobalPropertySchemas namespace
- namespaces, System.Xml namespace
- System namespace
- namespaces, System namespace
- namespaces, Microsoft.BizTalk.GlobalPropertySchemas namespace
- Microsoft.BizTalk.DefaultPipelines namespace
- projects, namespaces
- namespaces, warnings
- namespaces, Microsoft.BIzTalk.DefaultPipelines namespace
- namespaces
ms.assetid: cb642eac-7307-44f8-bbba-3ae364e11ea2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 820e15eb3524713dfd7d3f86311ca262fde191d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-biztalk-namespace-references-included-in-biztalk-projects"></a>Referencias de espacio de nombres de BizTalk incluidos en proyectos de BizTalk
Cuando agrega un proyecto nuevo de BizTalk, los siguientes espacios de nombres se incluyen de forma predeterminada:  
  
-   **Microsoft.BizTalk.DefaultPipelines**  
  
-   **Microsoft.BizTalk.GlobalPropertySchemas**  
  
-   **Sistema**  
  
-   **System.Xml**  
  
 También puede agregar nuevas referencias y referencias Web a su proyecto. Para obtener más información acerca de cómo agregar referencias con el **proyecto** menú, vea [en Visual Studio](../core/using-visual-studio.md). Para obtener información acerca de cómo agregar referencias Web, vea [agregar referencias Web](../core/adding-web-references.md).  
  
> [!CAUTION]
>  No quite las referencias predeterminadas. Si quita las referencias predeterminadas, podría tener problemas al hacer referencia a los elementos de BizTalk en su proyecto. Puede restaurar referencias predeterminadas en el Explorador de soluciones.  
  
> [!CAUTION]
>  Si el ensamblado al que hace referencia su proyecto de BizTalk se actualiza, las actualizaciones o cambios no se recogen automáticamente en el proyecto. Debería quitar las referencias obsoletas del Explorador de soluciones y, a continuación, volver a agregar la referencia (hacer una nueva referencia al ensamblado). También, puede cerrar la solución y volver a abrirla. En cualquier caso, las últimas actualizaciones del ensamblado al que se hace referencia están disponibles en su proyecto.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Referencia de Microsoft.BizTalk.DefaultPipelines](../core/microsoft-biztalk-defaultpipelines-reference.md)  
  
-   [Referencia de Microsoft.BizTalk.GlobalPropertySchemas](../core/microsoft-biztalk-globalpropertyschemas-reference.md)  
  
-   [Referencia del sistema](../core/system-reference.md)  
  
-   [Referencia de System.Xml](../core/system-xml-reference.md)