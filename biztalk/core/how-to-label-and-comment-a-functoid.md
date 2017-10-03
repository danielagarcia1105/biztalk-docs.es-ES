---
title: "Cómo etiquetar y comentar un Functoid | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.functiod.general
ms.assetid: 58ff3a07-cbb6-4817-b301-d2b434ed2ad9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fccdeefa35f9abb5a0c3158dba518d524811c611
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-label-and-comment-a-functoid"></a>Agregación de etiquetas y comentarios en un functoid
Las etiquetas y comentarios resultan útiles para documentar la finalidad de un functoid o vínculo en una asignación. Puede usar el **etiqueta** propiedad para proporcionar un nombre para un functoid. El **comentarios** propiedad le permite proporcionar información adicional acerca del functoid, normalmente información relevante sobre la operación que se va a realizar en él.  
  
 En la siguiente ilustración se muestran la etiqueta y los comentarios de un functoid. El functoid agrega dos entradas (Field1 y Field3) desde el esquema de origen y envía el resultado al Field4 en el esquema de destino. En este ejemplo, la etiqueta del functoid es “Add Field1 and Field3” y el comentario es “The addition is an output to Field4”.  
  
 ![Insertar etiquetas de functoid y comentarios](../core/media/label.gif "Label_")  
  
 Como un functoid puede formar parte de una asignación muy compleja, es importarle etiquetarlo debidamente y proporcionar además comentarios relevantes. Puede etiquetar tanto functoids como vínculos. Para obtener información sobre cómo etiquetar un vínculo, vea [cómo etiquetar un vínculo](../core/how-to-label-a-link.md).  
  
 Puede etiquetar y comentar un functoid de las siguientes maneras:  
  
-   Mediante el uso de la **configurar \<Functoid > Functoid** cuadro de diálogo.  
  
-   Mediante el uso de la **propiedades** ventana.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a>Para etiquetar y comentar un functoid desde el cuadro de diálogo Configurar  
  
1.  Haga clic en el functoid que desea etiquetar y comentar y, a continuación, haga clic en **configurar entradas de Functoid**.  
  
2.  En el **configurar \<Functoid > Functoid** cuadro de diálogo, haga clic en el **etiqueta y comentarios** ficha.  
  
3.  Escriba la información siguiente y, a continuación, haga clic en **Aceptar**.  
  
    -   **Etiqueta:** escriba el nuevo nombre.  
  
        > [!IMPORTANT]
        >  El número máximo de caracteres permitido es 256. Si se especifica una cadena con más de 256 caracteres, se aceptan los primeros 256 caracteres y el resto se descartan.  
  
    -   **Comentarios:** introduzca comentarios para el functoid.  
  
        > [!IMPORTANT]
        >  El número máximo de caracteres permitido es 1024. Si se especifica una cadena con más de 1024 caracteres, se aceptan los primeros 1024 caracteres y el resto se descartan.  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a>Procedimiento para etiquetar y comentar un functoid desde la ventana Propiedades  
  
1.  Seleccione el functoid que desea etiquetar y comentar.  
  
2.  En el **propiedades** ventana, escriba la información siguiente y, a continuación, haga clic en **Aceptar**.  
  
    -   **Etiqueta:** escriba el nuevo nombre.  
  
        > [!IMPORTANT]
        >  El número máximo de caracteres permitido es 256. Si se especifica una cadena con más de 256 caracteres, se aceptan los primeros 256 caracteres y el resto se descartan.  
  
    -   **Comentarios:** introduzca comentarios para el functoid.  
  
        > [!IMPORTANT]
        >  El número máximo de caracteres permitido es 1024. Si se especifica una cadena con más de 1024 caracteres, se aceptan los primeros 1024 caracteres y el resto se descartan.  
  
## <a name="see-also"></a>Vea también  
 [Editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md)