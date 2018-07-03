---
title: Referencias de BizTalk Namespace incluidos en proyectos de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 608f3ebf9a80553749fe5de558c2db05e3c7673d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016372"
---
# <a name="about-biztalk-namespace-references-included-in-biztalk-projects"></a>Referencias de espacio de nombres de BizTalk incluidos en proyectos de BizTalk
Cuando agrega un proyecto nuevo de BizTalk, los siguientes espacios de nombres se incluyen de forma predeterminada:  
  
- **Microsoft.BizTalk.DefaultPipelines**  
  
- **Microsoft.BizTalk.GlobalPropertySchemas**  
  
- **Sistema**  
  
- **System.Xml**  
  
  También puede agregar nuevas referencias y referencias Web a su proyecto. Para obtener más información acerca de cómo agregar referencias mediante el **proyecto** menú, vea [con Visual Studio](../core/using-visual-studio.md). Para obtener información acerca de cómo agregar referencias Web, vea [agregar referencias Web](../core/adding-web-references.md).  
  
> [!CAUTION]
>  No quite las referencias predeterminadas. Si quita las referencias predeterminadas, podría tener problemas al hacer referencia a los elementos de BizTalk en su proyecto. Puede restaurar referencias predeterminadas en el Explorador de soluciones.  
  
> [!CAUTION]
>  Si el ensamblado al que hace referencia su proyecto de BizTalk se actualiza, las actualizaciones o cambios no se recogen automáticamente en el proyecto. Debería quitar las referencias obsoletas del Explorador de soluciones y, a continuación, volver a agregar la referencia (hacer una nueva referencia al ensamblado). También, puede cerrar la solución y volver a abrirla. En cualquier caso, las últimas actualizaciones del ensamblado al que se hace referencia están disponibles en su proyecto.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Referencia de Microsoft.BizTalk.DefaultPipelines](../core/microsoft-biztalk-defaultpipelines-reference.md)  
  
-   [Referencia de Microsoft.BizTalk.GlobalPropertySchemas](../core/microsoft-biztalk-globalpropertyschemas-reference.md)  
  
-   [Referencia de System](../core/system-reference.md)  
  
-   [Referencia de System.Xml](../core/system-xml-reference.md)