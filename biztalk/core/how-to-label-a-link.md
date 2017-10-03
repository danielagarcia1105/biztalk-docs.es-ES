---
title: "Cómo etiquetar un vínculo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fb81763-8b50-4334-88a8-efad1c5d82d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0e47a776fdbc8eccbc1037b3c73b069d810eee0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-label-a-link"></a>Creación de etiqueta para un vínculo
Las etiquetas resultan útiles para documentar la finalidad de un functoid o vínculo en una asignación. Puede usar el **etiqueta** propiedad para el nombre de un vínculo. Esto resulta útil si la asignación contiene estructuras de esquemas grandes y la identificación de los vínculos de entradas y salidas a un functoid resulta complicada.  
  
> [!NOTE]
>  Para obtener información sobre cómo etiquetar y comentar functoids, consulte [cómo etiquetar y comentar un Functoid](../core/how-to-label-and-comment-a-functoid.md).  
  
 La figura siguiente muestra una etiqueta de vínculo.  
  
 ![Etiquetado de un vínculo](../core/media/new-labelling-link.gif "New_Labelling_link")  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
### <a name="to-add-a-label-to-a-link"></a>Procedimiento para agregar una etiqueta a un vínculo  
  
1.  Seleccione el vínculo que desea etiquetar.  
  
2.  En el **propiedades** ventana, especifique el nuevo nombre en el **etiqueta** campo.  
  
    > [!IMPORTANT]
    >  El número máximo de caracteres permitido es 256. Si se especifica una cadena con más de 256 caracteres, se aceptan los primeros 256 caracteres y el resto se descartan.  
  
     ![Propiedades de la etiqueta de vínculo](../core/media/new-to-label-link.gif "New_To_Label_Link")  
  
## <a name="see-also"></a>Vea también  
 [Utilizar vínculos para especificar el registro y las asignaciones de campos](../core/using-links-to-specify-record-and-field-mappings.md)