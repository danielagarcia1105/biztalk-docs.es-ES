---
title: Cómo agregar un ámbito Shape2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- adding, Scope shapes
ms.assetid: 9449210f-1f29-4b86-a14b-148caa06ac6b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef67618c553702ae32cd0a88f6d2f77eb1ff053
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246804"
---
# <a name="how-to-add-a-scope-shape"></a>Cómo agregar una forma Ámbito
Utilice el procedimiento siguiente para agregar una **ámbito** forma.  
  
### <a name="to-add-a-scope-shape"></a>Para agregar una forma ámbito  
  
1.  Haga clic en la flecha situada bajo la **ReceiveFromIn** de puerto, seleccione **Insertar forma**y seleccione **ámbito**.  
  
     En el **ámbito** forma, se establecen operaciones que podrían tener errores.  
  
     Por ejemplo, se agrega un puerto de envío y uno de recepción en una orquestación SQLExecute. En este ejemplo, envía un mensaje a SERVER. SERVER da una respuesta. Ejecuta el resto de la orquestación y devuelve información al puerto OutFile.  
  
2.  En el **ámbito** forma, establezca el **tipo de transacción** a **ninguno**.  
  
3.  Pulse el botón derecho dentro de la **ámbito** forma y seleccione **nuevo controlador de excepción**.  
  
     Esto crea la **excepción de filtrado** bloque. Si se produce una excepción desde el sistema back-end, se detecta en el **excepción de filtrado** bloque.  
  
4.  En el **excepción de filtrado** bloque, debe agregar la lógica.  
  
     La lógica más importante que debe establecer es el tipo de mensaje de error que espera recibir.  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling3.md)