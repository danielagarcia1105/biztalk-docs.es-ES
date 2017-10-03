---
title: "Cómo agregar un Block4 de excepción Catch | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 632fa089-a1af-4126-b32b-68d4d8942387
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b409f25fc32c609bb4c1a80c0582cdb1c363e965
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>Cómo agregar un bloque Excepción de filtrado
El **excepción de filtrado** de bloqueo representa un controlador de excepciones. **Detectar excepciones** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones. Puede adjuntar tantos **excepción de filtrado** bloquea según sea necesario.  
  
 Puede configurar controladores de excepción para controlar los distintos tipos de excepciones. En cada controlador de excepción, especifique un tipo de excepción, que puede ser una excepción o un objeto derivado de la clase System. Si se origina una excepción que coincida con el tipo especificado en un controlador de excecpción, se llamará a este controlador.  
  
> [!NOTE]
>  Para agregar una **excepción de filtrado** bloquear a un **ámbito** forma, la propiedad de tipo de transacción de la **ámbito** forma debe establecerse en **ninguno** o  **Larga ejecución**.  
  
|Agregar y rellenar un bloque de excepción de filtrado|  
|---------------------------------------------------|  
|1.  Haga clic en el **ámbito** forma a la que desea agregar un **excepción de filtrado** bloquear para el acceso y haga clic en **nuevo controlador de excepción**.<br />     A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.<br />2.  En el **propiedades** ventana, especifique las propiedades. El más importante es la **tipo de objeto de excepción**; éste es el tipo de mensaje que filtrará.<br />     **Nombre del objeto de excepción**<br />     : Asigna un nombre para el objeto de excepción detectado por el controlador de excepciones.<br />     **Tipo de objeto de excepción**<br />     -Determina el tipo de objeto (derivado de System.Exception) que detectará este controlador de excepciones.<br />3.  En el **propiedades** ventana, abra el **tipo de objeto de excepción** lista. Esta lista contiene el **excepción General**.<br />4.  Dentro de la **excepción de filtrado** bloquear, agregue formas a fin de crear el proceso para controlar la excepción.<br />5.  Menú contextual que aparece a continuación el **excepción de filtrado**, seleccione **Insertar forma**y seleccione **construir mensaje**.<br />6.  Haga doble clic en **MessageAssignment** para activar el Editor de texto y escriba la asignación de mensajes.<br />     Por ejemplo, escriba Message_3 = Test.<br />     ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")|  
  
## <a name="see-also"></a>Vea también  
 [Completar el mensaje de excepción](../core/completing-the-exception-message2.md)   
 [Cómo agregar una forma ámbito](../core/how-to-add-a-scope-shape3.md)   
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling1.md)