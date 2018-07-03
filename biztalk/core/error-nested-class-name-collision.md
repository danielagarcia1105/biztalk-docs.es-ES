---
title: 'Error: colisión de nombre de clase anidada | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.nestedClassNameCollision
ms.assetid: dd636d25-d0c1-41be-a2ba-b38ea97b973d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856841093c37848924dc6e9b6d160186e03ad304
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003333"
---
# <a name="error---nested-class-name-collision"></a>Error: colisión de nombre de clase anidada
**Código de error**  

 BEC2017  

 **Explicación**  

 El **nombre de tipo** se encontró la propiedad de este esquema para ser el mismo que el **RootNode TypeName** propiedad de uno de los nodos raíz en el esquema. C# no permite clases anidadas con el mismo nombre; por tanto, esta condición produce un error.  

 **Acción del usuario**  

 Debe cambiar uno o ambos valores de la propiedad correspondiente para evitar la colisión de nombres. Realice una de las acciones siguientes:  

- Seleccione el archivo de esquema correspondiente en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] , el Explorador de soluciones y, a continuación, en la ventana Propiedades, cambie la **nombre de tipo** propiedad a un valor válido único.  

   \- O bien  

- Seleccione el nodo raíz indicado y, a continuación, en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, cambie la **RootNode TypeName** propiedad a un valor válido único.
