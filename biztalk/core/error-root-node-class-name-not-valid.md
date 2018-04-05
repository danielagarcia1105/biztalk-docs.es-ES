---
title: 'Error: nombre de clase de nodo raíz no válido | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.rootNodeClassNameNotValid
ms.assetid: 48b4f7e4-8c20-4e94-86be-1425ea62f8c5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff170609ef37b1d7f2b00a4d4ca3952b89eef9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---root-node-class-name-not-valid"></a>Error: nombre de clase de nodo raíz no válido
**Código de error**  
  
 BEC2012  
  
 **Explicación**  
  
 El **RootNode TypeName** propiedad de uno de los nodos raíz de este esquema no es válido. Dado que el valor de la **RootNode TypeName** propiedad se utiliza como el nombre de un nombre de clase de C# generado automáticamente, debe ser un identificador C# válido y no puede ser una palabra clave de BizTalk reservada.  
  
 **Acción del usuario**  
  
 Seleccione el nodo raíz indicado y, a continuación, en la Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de propiedades, cambiar la **RootNode TypeName** propiedad en un valor que es un identificador válido de C# y no es una palabra clave de BizTalk reservada.