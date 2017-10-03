---
title: "Apéndice A: métodos de interfaz de componente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, methods
- methods, component interfaces
- component interface methods
ms.assetid: c8377589-fbdf-4287-b822-53263a00381d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cb5b87cb063f22c889291b8eff3b2be50d64a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-a-component-interface-methods"></a>Apéndice A: métodos de interfaz de componente
El adaptador de Microsoft para PeopleSoft Enterprise proporciona métodos estándar para las interfaces de componentes.  
  
> [!NOTE]
>  El parámetro `interactiveMode`, de la versión Ex de los métodos, proporciona asistencia a la hora de depurar una llamada al servidor (`Create/CreateEx`, `Update/UpdateEx`, and `DeleteOnly`). La llamada al servidor de cada elemento del método *Ex se efectúa de forma independiente, de manera que es posible saber exactamente en qué elemento se ha producido un error. Hay una disminución del rendimiento cuando se usa un \*Ex método porque el elemento de la propiedad recibe una llamada independiente. Se pueden desarrollar con \*Ex método y a continuación, cambie al método main (por ejemplo, `Create`) para la producción. También puede utilizar un modificador de depuración en producción para cambiar entre usar el método y la \*Ex método.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Método CreateEx](../core/createex-method.md)  
  
-   [Método DeleteOnly](../core/deleteonly-method.md)  
  
-   [Find (método)](../core/find-method.md)  
  
-   [Get (método)](../core/get-method.md)  
  
-   [Método UpdateEx](../core/updateex-method.md)  
  
-   [Métodos de definidos por el usuario de interfaz de componente](../core/component-interface-user-defined-methods.md)  
  
-   [Propiedades de fecha efectiva](../core/effective-date-properties.md)