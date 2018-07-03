---
title: Cómo depurar asignaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f30d26b7c722ea4e4896bc7d19130e41eec5c719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989725"
---
# <a name="how-to-debug-maps"></a>Depuración de asignaciones
El **depurar asignación** característica es útil para identificar y corregir problemas de asignación complejos. Este tema proporciona instrucciones paso a paso para la depuración de asignaciones mediante el depurador XSLT en línea.  

> [!NOTE]
>  Al depurar la asignación, el **depurar asignación** característica usa las propiedades de archivo de asignación **instancia de entrada de comprobar asignación** y **instancia de salida de comprobar asignación**. Por lo tanto, antes de depurar la asignación, se recomienda que configure la entrada y propiedades de instancia en el archivo de asignación de salida.  

### <a name="to-debug-a-biztalk-map"></a>Para depurar un asignación de BizTalk  

1. En el Explorador de soluciones, haga clic en el mapa que desee probar y, a continuación, haga clic en **depurar asignación**. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Muestra la asignación en formato XSLT en su editor.  

2. Presione F10 o F11 para depurar el código XSL. Al presionar F11 en una llamada de functoid, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] pasa al código C# del functoid. Los valores de las variables usadas en el código fuente del functoid se pueden ver en el Depurador local de Windows.
