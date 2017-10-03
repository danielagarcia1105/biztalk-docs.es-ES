---
title: "Cómo agregar un Block2 de excepción Catch | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks
- exceptions, Catch Exception blocks
ms.assetid: 7c8b6024-e8dc-4417-83f9-bf4032644b91
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e48ce1e6f0646acdf63ed33582f382f1baed797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>Cómo agregar un bloque Excepción de filtrado
El **excepción de filtrado** de bloqueo representa un controlador de excepciones. **Detectar excepciones** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones. Puede adjuntar tantos **excepción de filtrado** bloquea según sea necesario.  
  
 Puede configurar controladores de excepción para controlar los distintos tipos de excepciones. En cada controlador de excepciones, debe especificar un tipo de excepción. Debe ser una excepción o un objeto derivado de la clase `System`. Si se origina una excepción que coincida con el tipo especificado en un controlador de excepción, se llamará a dicho controlador.  
  
> [!NOTE]
>  Para agregar un bloque de excepción de filtrado a una forma ámbito, la propiedad de tipo de transacción de la forma ámbito debe establecerse en **ninguno** o **larga ejecución**.  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a>Para agregar y rellenar un bloque de excepción de filtrado  
  
1.  Haga clic en el **ámbito** forma a la que desea agregar un **excepción de filtrado** bloquear y, a continuación, haga clic en **nuevo controlador de excepción**.  
  
     A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.  
  
2.  En el **propiedades** ventana, especifique las propiedades.  
  
     La propiedad más importante es la **tipo de objeto de excepción**; éste es el tipo de mensaje que filtrará.  
  
3.  En el **propiedades** windows, en la **tipo de objeto de excepción** lista, seleccione **excepción General**.  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |**Nombre del objeto de excepción**|Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.|  
    |**Tipo de objeto de excepción**|Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.|  
  
4.  Dentro del bloque Excepción de filtrado, agregue formas a fin de crear el proceso para controlar la excepción.  
  
    1.  Menú contextual que aparece a continuación el **CatchException** y seleccione **Insertar forma**y, a continuación, seleccione **construir mensaje**.  
  
    2.  Haga doble clic en **MessageAssignment** para abrir el Editor de texto y escriba la asignación de mensajes.  
  
         Por ejemplo, escriba `Message_3 = Test`.  
  
## <a name="see-also"></a>Vea también  
 [Completar el mensaje de excepción](../core/completing-the-exception-message4.md)   
 [Cómo agregar una forma ámbito](../core/how-to-add-a-scope-shape4.md)   
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling4.md)