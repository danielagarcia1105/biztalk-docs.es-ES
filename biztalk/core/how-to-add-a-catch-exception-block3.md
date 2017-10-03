---
title: "Cómo agregar un Block3 de excepción Catch | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], creating
- Catch Exception block [Orchestration Designer], exception handler
- Catch Exception block [Orchestration Designer], about Catch Exception blocks
- Orchestration Designer, errors
ms.assetid: 63ca4a60-b657-452a-86fd-78968ccf2933
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1040a27a5e1273d2ad80a722deb421878de36c12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>Cómo agregar un bloque Excepción de filtrado
El **excepción de filtrado** de bloqueo representa un controlador de excepciones. **Detectar excepciones** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones. Puede adjuntar tantos **excepción de filtrado** bloquea según sea necesario.  
  
 Puede configurar controladores de excepción para controlar los distintos tipos de excepciones. En cada controlador de excepción, especifique un tipo de excepción, que debe ser un mensaje de error o un objeto derivado de la clase **System.Exception**. Si no especifica un tipo de excepción, el bloque de excepción se tratará como un controlador de excepción general y puede detectar las excepciones que no se derivan de **System.Exception**.  
  
 Si se origina una excepción que coincida con el tipo especificado en un controlador de excepción, se llamará a dicho controlador. Si se origina otra excepción, la controlará el controlador de excepción predeterminado.  
  
> [!NOTE]
>  Para agregar una **excepción de filtrado** bloquear a un **ámbito** forma, el **tipo de transacción** propiedad de la **ámbito** forma debe establecerse en **Ninguno** o **de larga ejecución**.  
  
### <a name="to-add-a-catch-exception-block"></a>Para agregar un bloque Excepción de filtrado  
  
1.  Haga clic en el **ámbito** forma a la que desea agregar un **excepción de filtrado** bloquear y, a continuación, haga clic en **nuevo controlador de excepción**.  
  
     A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.  
  
2.  En la ventana Propiedades, especifique las siguientes propiedades:  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |Nombre de objeto de excepción|Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.|  
    |Tipo de objeto de excepción|Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.|  
  
3.  Dentro de la **excepción de filtrado** bloquear, agregue formas a fin de crear el proceso para controlar la excepción.  
  
> [!NOTE]
>  Si especifica una excepción General como el **excepción** tipo de objeto, el **excepción de filtrado** bloque interceptará todas las excepciones, las que no se deriva de incluidas **System.Exception** . En tal caso, no dispondrá de acceso a un objeto de excepción. Dentro de este bloque, si utiliza un **Iniciar excepción** forma con el tipo de excepción General, se estará volviendo a la excepción detectada.  
  
## <a name="see-also"></a>Vea también  
 [Excepciones](../core/exceptions.md)