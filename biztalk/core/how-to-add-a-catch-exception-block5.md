---
title: "Cómo agregar un Block5 de excepción Catch | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, adding Catch Exception block
- Catch Exception blocks, adding
ms.assetid: 4875060c-976c-40e7-830a-ffd1a47ba68a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c045677fb2d177377725a3f11e81a5c5c70f9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>Cómo agregar un bloque Excepción de filtrado
Para agregar una **excepción de filtrado** bloquear a un **ámbito** forma, el **tipo de transacción** propiedad de la **ámbito** forma debe establecerse en **Ninguno** o **de larga ejecución**.  
  
### <a name="to-add-a-catch-exception-block"></a>Procedimiento para agregar un bloque Excepción de filtrado  
  
1.  Haga clic en el **ámbito** forma y, a continuación, haga clic en **nuevo controlador de excepción**.  
  
     A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.  
  
2.  En el **propiedades** ventana, especifique las propiedades.  
  
     La propiedad más importante es la **tipo de objeto de excepción**; éste es el tipo de mensaje que filtrará.  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |**Nombre del objeto de excepción**|Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.|  
    |**Tipo de objeto de excepción**|Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.|  
  
3.  En el **propiedades** ventana, en la **tipo de objeto de excepción** lista, seleccione **excepción General**.  
  
4.  Dentro de la **excepción de filtrado** bloquear, agregue formas a fin de crear el proceso para controlar la excepción.  
  
    1.  Menú contextual que aparece a continuación el **CatchException** y seleccione **Insertar forma**y, a continuación, seleccione **construir mensaje**.  
  
    2.  Haga doble clic en **MessageAssignment** para abrir el Editor de texto y escriba la asignación de mensajes.  
  
         Por ejemplo, escriba `Message_3 = Test`.  
  
## <a name="see-also"></a>Vea también  
 [Completar el mensaje de excepción](../core/completing-the-exception-message1.md)   
 [Cómo agregar una forma ámbito](../core/how-to-add-a-scope-shape5.md)   
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling5.md)