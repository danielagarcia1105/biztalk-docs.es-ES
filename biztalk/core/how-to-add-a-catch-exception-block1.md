---
title: Cómo agregar un 1 de excepción Catch | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding Catch Exception block
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 8e4b264b-b3b0-4d83-81df-a14dc2ddeea2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7922a1527e0f6359427be992c4cc9963f8c7d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247028"
---
# <a name="how-to-add-a-catch-exception-block"></a>Cómo agregar un bloque Excepción de filtrado
El **excepción de filtrado** de bloqueo representa un controlador de excepciones. **Detectar excepciones** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones. Puede adjuntar tantos **excepción de filtrado** bloquea según sea necesario.  
  
 Puede configurar controladores de excepción para controlar los distintos tipos de excepciones. En cada controlador de excepción, especifique un tipo de excepción, que puede ser una excepción o un objeto derivado de la clase `System`. Si se origina una excepción que coincida con el tipo especificado en un controlador de excepción, se llamará a dicho controlador.  
  
> [!NOTE]
>  Para agregar una **excepción de filtrado** bloquear a un **ámbito** forma, la propiedad de tipo de transacción de la **ámbito** forma debe establecerse en **ninguno** o  **Larga ejecución**.  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a>Para agregar y rellenar un bloque de excepción de filtrado  
  
1.  Haga clic en el **ámbito** forma a la que desea agregar un **excepción de filtrado** bloquear y, a continuación, haga clic en **nuevo controlador de excepción**.  
  
     A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.  
  
2.  En el **propiedades** ventana, especifique las propiedades.  
  
     La propiedad más importante es el Tipo de objeto de excepción, ya que es el tipo de mensaje que detectará.  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |Nombre de objeto de excepción|Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.|  
    |Tipo de objeto de excepción|Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.|  
  
3.  En el **propiedades** ventana, en la **tipo de objeto de excepción** lista, seleccione la **excepción General**.  
  
4.  Dentro de la **excepción de filtrado** bloquear, agregue formas a fin de crear el proceso para controlar la excepción.  
  
5.  Menú contextual que aparece a continuación el **excepción de filtrado** bloquear, seleccione **Insertar forma**y, a continuación, seleccione **construir mensaje**.  
  
6.  Haga doble clic en **MessageAssignment** para activar el Editor de texto y escriba la asignación de mensajes.  
  
     Por ejemplo, escriba `Message_3 = Test`.  
  
## <a name="see-also"></a>Vea también  
 [Completar el mensaje de excepción](../core/completing-the-exception-message5.md)   
 [Cómo agregar una forma ámbito](../core/how-to-add-a-scope-shape2.md)   
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling3.md)