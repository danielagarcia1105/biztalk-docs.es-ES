---
title: "Cómo depurar mapas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e40964b267ad0788308a92490a106f940a6cb33e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-debug-maps"></a>Depuración de asignaciones
El **depurar asignación** característica es útil para identificar y solucionar problemas de asignación complejos. Este tema proporciona instrucciones paso a paso para la depuración de asignaciones mediante el depurador XSLT en línea.  
  
> [!NOTE]
>  Al depurar la asignación, el **depurar asignación** característica usa las propiedades de archivo de asignación **instancia de entrada de comprobar asignación** y **instancia de salida de comprobar asignación**. Por lo tanto, antes de depurar la asignación, se recomienda que configure la entrada y propiedades de instancia en el archivo de asignación de salida.  
  
### <a name="to-debug-a-biztalk-map"></a>Para depurar un asignación de BizTalk  
  
1.  En el Explorador de soluciones, haga clic en la asignación que desea probar y, a continuación, haga clic en **depurar asignación**. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Muestra la asignación en formato XSLT en su editor.  
  
2.  Presione F10 o F11 para depurar el código XSL. Al presionar F11 en una llamada de functoid, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] pasa al código C# del functoid. Los valores de las variables usadas en el código fuente del functoid se pueden ver en el Depurador local de Windows.