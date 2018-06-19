---
title: Cómo agregar un Block6 de excepción Catch | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exception handling, Catch Exception block
- Catch Exception blocks
- exceptions, Catch Exception block
ms.assetid: 404312dd-773b-44fe-8b65-7de3d0af2f79
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4be60ddbe45ef4b4f293d7959dc774254e7cd3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248724"
---
# <a name="how-to-add-a-catch-exception-block"></a>Cómo agregar un bloque Excepción de filtrado
El **excepción de filtrado** de bloqueo representa un controlador de excepciones. **Detectar excepciones** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones. En BizTalk Server, puede adjuntar tantos **excepción de filtrado** bloquea según sea necesario.  
  
 Puede configurar controladores de excepción para controlar los distintos tipos de excepciones. En cada controlador de excepción, especifique un tipo de excepción, que puede ser un mensaje de error o un objeto derivado de la clase `System.Exception`. Si no especifica ningún tipo de excepción, el bloque de excepción se tratará como un controlador de excepción general y podrá filtrar las excepciones que no procedan de `System.Exception`.  
  
 Si se origina una excepción que coincida con el tipo especificado en un controlador de excecpción, se llamará a este controlador. Si se produce otra excepción, se controla por el controlador de excepción predeterminado.  
  
> [!NOTE]
>  Para agregar una **excepción de filtrado** bloquear a un **ámbito** forma, el **tipo de transacción** propiedad de la **ámbito** forma debe establecerse en None o Long En ejecución.  
  
## <a name="adding-and-populating-a-catch-exception-block"></a>Agregar y rellenar un bloque Excepción de filtrado  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a>Para agregar y rellenar un bloque Excepción de filtrado  
  
1.  Haga clic en el **ámbito** forma a la que desea agregar un **excepción de filtrado** bloquear a y, a continuación, haga clic en **nuevo controlador de excepción**.  
  
     A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.  
  
2.  En el **propiedades** ventana, especifique las propiedades. La propiedad más importante es la **tipo de objeto de excepción** porque éste es el tipo de mensaje que filtrará.  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |Nombre de objeto de excepción|Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.|  
    |Tipo de objeto de excepción|Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.|  
  
3.  En el **propiedades** ventana, haga clic en el **tipo de objeto de excepción** lista. Esta lista contiene la excepción general que inicia el adaptador.  
  
     El nombre aparecerá como el error establecido en el puerto al sistema de servidor, por ejemplo, PS.SQLExecute.Fault.  
  
4.  Agregar un nombre para el **nombre de objeto de excepción**, por ejemplo, una prueba.  
  
     Dentro de la **excepción de filtrado** bloquear, agregue formas a fin de crear el proceso para controlar la excepción.  
  
    1.  Menú contextual que aparece a continuación el **excepción de filtrado**, seleccione **Insertar forma**y seleccione **construir mensaje**.  
  
         ![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")  
  
    2.  Haga doble clic en **MessageAssignment** para abrir el Editor de texto y escriba la asignación de mensajes.  
  
         Escriba el nombre que se establece en los **nombre de objeto de excepción** desde el **excepción de filtrado**y el nuevo mensaje creado para el error.  
  
         Por ejemplo, escriba `Message_3 = Test`.  
  
         ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar una forma ámbito](../core/how-to-add-a-scope-shape1.md)   
 [Completar el mensaje de excepción](../core/completing-the-exception-message3.md)   
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling2.md)