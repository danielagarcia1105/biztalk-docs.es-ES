---
title: "Cómo agregar un ámbito Shape5 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 1e16eda1-c4bd-4428-a477-78c453aeb1aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7bbe3f5fbb267fee618ac7f0b91c35ad33e1758
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>Cómo agregar una forma Ámbito
Siga estos pasos para agregar una **ámbito**forma.  
  
### <a name="to-add-a-scope-shape"></a>Procedimiento para agregar una forma Ámbito  
  
1.  Haga clic en la flecha situada bajo la **ReceiveFromIn** de puerto, seleccione **Insertar forma**y, a continuación, haga clic en **ámbito**.  
  
     En el **ámbito** forma, se establecen operaciones que podrían tener errores.  
  
     Por ejemplo, se agrega un puerto de envío y uno de recepción en una orquestación SQLExecute. En este ejemplo, envía un mensaje a SERVER. SERVER da una respuesta. Ejecuta el resto de la orquestación y devuelve información al puerto OutFile.  
  
2.  En el **ámbito** forma, establezca el **tipo de transacción** a **ninguno**.  
  
3.  Pulse el botón derecho dentro de la **ámbito** forma y seleccione **nuevo controlador de excepción**.  
  
     Esto crea el `Catch Exception`bloque. Si se produce una excepción desde el back-end, se detecta en el `Catch Exception`bloque.  
  
4.  En el bloque `Catch Exception`, debe agregar la lógica.  
  
     La lógica más importante que debe establecer es el tipo de mensaje de error que espera recibir.  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling5.md)