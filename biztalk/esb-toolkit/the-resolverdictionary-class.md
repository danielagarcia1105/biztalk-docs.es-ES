---
title: La clase ResolverDictionary | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46deb8a0-0523-4a5c-ac6b-45c506de7a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dfe0082ffc7f7b68c5c56811a28d5ccd20e93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295004"
---
# <a name="the-resolverdictionary-class"></a>La clase ResolverDictionary
El **ResolverDictionary** clase es un **diccionario**-según la clase que puede almacenar instancias de la **resolución** de clase como **cadena** nombre / pares de valor. Cuando se crean instancias de la **ResolverDictionary** (clase), debe proporcionar una referencia a un archivo **diccionario** instancia. El **ResolverDictionary** clase proporciona los datos que la **resolución** clase utiliza mientras se realiza la resolución de tiempo de ejecución.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] installer instala y registra el **Microsoft.Practices.ESB.Resolver.dll** ensamblado con el **ResolverDictionary** clase en la memoria caché global de ensamblados.  
  
 El **ResolverDictionary** clase expone un método y una propiedad:  
  
-   **Elemento (** clave **)**. Este método toma un valor de cadena que contiene un nombre de clave. Devuelve el valor correspondiente de la cadena o una cadena vacía si el elemento no existe en subyacente **diccionario** instancia.  
  
-   **BaseDictionary**. Esta propiedad devuelve una referencia a subyacente **diccionario** instancia.