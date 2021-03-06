---
title: Cómo configurar la jerarquía de nodos que coincidan con | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5302e194-cbc7-4d26-b25b-eb4e38abfe23
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eb785793b865e36c5b37bd6b32199ab3e34f5d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009581"
---
# <a name="how-to-configure-node-hierarchy-matching"></a>Cómo configurar coincidencia de jerarquía de nodos
Cuando se crea un vínculo en una asignación, el Asignador de BizTalk crea automáticamente vínculos de compilador para implementar el vínculo diseñado. El **vínculos de destino** propiedad de un vínculo controla cómo el asignador de BizTalk dibuja los vínculos de compilador. En este tema se proporciona información acerca de cómo establecer los vínculos de destino.  
  
 El **vínculos de origen** propiedad especifica cómo un valor se recupera desde el nodo de origen y se aplica al nodo de destino. Para obtener información sobre cómo establecer vínculos de origen, vea [cómo establecer el valor del compilador de vínculos de origen](../core/how-to-set-the-source-links-compiler-value.md).  
  
> [!NOTE]
>  Esta operación requiere que se está ejecutando el Asignador de BizTalk.  
  
### <a name="to-set-the-target-links-property"></a>Para establecer la propiedad Vínculos de destino  
  
1. En la página de cuadrícula de la asignación, haga clic en un enlace el que desee establecer la propiedad de vínculos de destino.  
  
2. En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] **propiedades** ventana, establezca el **vínculos de destino** propiedad a una de las siguientes opciones:  
  
   -   **Vínculos sin formato.** Se quita el formato de la jerarquía del nodo de registro de origen en el nodo de registro vinculado del esquema de destino.  
  
       > [!NOTE]
       >  De forma predeterminada, el asignador de BizTalk establece el **vínculos de destino** propiedad **Flatten**.  
  
   -   **Coincidir vínculos de arriba abajo.** La coincidencia de nodos se lleva a cabo nivel a nivel en orden descendente.  
  
   -   **Coincidir vínculos de abajo arriba.** La coincidencia de nodos se lleva a cabo nivel a nivel en orden ascendente.  
  
## <a name="see-also"></a>Vea también  
 [Coincidencia del nivel jerárquico de nodos](../core/node-hierarchy-level-matching.md)   
 [Vínculos y directivas de compilador](../core/compiler-directives-and-links.md)   
 [Uso de vínculos para especificar asignaciones de registros y campos](../core/using-links-to-specify-record-and-field-mappings.md)