---
title: Visualización de recuadros informativos e información sobre herramientas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5621bd0a-7028-43fc-b6e8-74a528129285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06aba645f94b87e0a7951d9c8264056262a12a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257284"
---
# <a name="how-to-view-infotip-and-tooltip"></a>Visualización de recuadros informativos e información sobre herramientas
Al mover el cursor sobre un elemento de una asignación sin hacer clic en él, aparece una sugerencia con información de utilidad sobre dicho elemento.  
  
 El Asignador de BizTalk usa dos tipos de sugerencias: recuadro informativo e información sobre herramientas.  
  
-   **Recuadros informativos** se muestran para functoids o vínculos. Al configurar etiquetas o comentarios para functoids o links, los verá como recuadro informativo en la página de cuadrícula. Además, cuando el valor de texto para las propiedades supera la visualización de la **cuadrícula de propiedades**, se muestra el recuadro informativo.  
  
-   **Información sobre herramientas** se muestran para los nodos de esquema que están parcial o completamente ocultos desde la alineación actual en la vista de cuadrícula.  
  
 Para etiquetas de vínculos, solo se conservan los primeros 256 caracteres y la información para herramientas muestra la etiqueta completa. Para functoids, la etiqueta puede contener un máximo de 256 caracteres y los comentarios tienen un límite de 1024 caracteres. El texto del comentario se trunca en consecuencia para mostrar solo los 256 primeros caracteres del comentario.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para ver la información sobre herramientas, asegúrese de que se está ejecutando el Asignador de BizTalk.  
  
## <a name="to-view-the-infotip"></a>Procedimiento para ver el recuadro informativo  
 Al mover el ratón sobre un functoid, la información sobre herramientas muestra información acerca del nombre del functoid, su etiqueta, el comentario y los parámetros de entrada (si existen). Para una **secuencias de comandos** functoid, el recuadro informativo muestra las primeras líneas de código.  
  
 El recuadro informativo a un vínculo muestra la siguiente información:  
  
-   Etiqueta del vínculo, si está definida  
  
-   **Desde: conexión de origen**. Si la conexión de origen es un elemento de esquema, muestra el nombre del elemento. Si la conexión de origen es un functoid, muestra el nombre del functoid.  
  
-   **Para: conexión de destino**. Si la conexión de destino es un elemento de esquema, muestra el nombre del elemento. Si la conexión de destino es un functoid, muestra el nombre del functoid.  
  
 Si los campos de la **cuadrícula de propiedades** tienen texto que supera la visualización, mueva el mouse en el campo. El recuadro informativo mostrará el texto completo.  
  
 En la siguiente ilustración se muestra recuadros informativos a un functoid, vínculo y el **cuadrícula de propiedades**.  
  
 ![Recuadros informativos para functoid, vínculo y etiqueta](../core/media/viewing-infotips.gif "Viewing_infotips")  
  
## <a name="to-view-the-tooltip"></a>Procedimiento para ver la información sobre herramientas  
 Si los esquemas de origen o destino son grandes, la asignación puede expandirse verticalmente; de este modo, los nodos de esquema pueden ser parcialmente visibles. En tal caso, puede ver informaciones sobre herramientas cuando mueve el ratón en dichos nodos de origen.  
  
 En la siguiente figura se muestra una información sobre herramientas a un nodo de esquema de destino parcialmente oculto.  
  
 ![Información sobre herramientas para un nodo de esquema](../core/media/viewing-tooltips.gif "Viewing_tooltips")  
  
## <a name="see-also"></a>Vea también  
 [Con el asignador de BizTalk](../core/using-biztalk-mapper.md)