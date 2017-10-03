---
title: "Derivación de tipo Global complejo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fbf429d0-64f4-4c43-a5f7-e8af050803b9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee4e6235af62b2c08c08382b897632d15e34e0cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="complex-global-type-derivation"></a>Derivación de tipo global complejo
Hay dos tipos de herencia en XSD: extensión y restricción. El Editor de BizTalk proporciona acceso a esta funcionalidad XSD mediante los dos siguientes **registro** propiedades de nodo:  
  
-   **Tipo de datos base**. esta propiedad proporciona la lista de todos los tipos simples y complejos globales disponibles para usarlos como tipos de datos base. Los tipos globales complejos puede estar en el mismo esquema o en cualquier esquema importado.  
  
-   **Derivada por**. esta propiedad sirve para elegir entre la derivación por extensión o por restricción. Esta propiedad se establece automáticamente en **extensión** al establecer el **Base Data Type** propiedad a cualquier tipo de la lista. Si establece esta propiedad en **(predeterminado)**, cualquier tipo en el **Base Data Type** propiedad se quita, se deshabilita la herencia para el nodo.  
  
> [!NOTE]
>  El **tipo de contenido** propiedad también se establece automáticamente en **ComplexContent** cuando se utiliza la derivación por extensión o restricción.  
  
 En esta sección se explica con mayor detalle la derivación de tipo complejo mediante los mecanismos de extensión y restricción.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Derivación de tipo complejo mediante el mecanismo de extensión](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [Derivación de tipo complejo mediante el mecanismo de restricción](../core/complex-type-derivation-using-the-restriction-mechanism.md)