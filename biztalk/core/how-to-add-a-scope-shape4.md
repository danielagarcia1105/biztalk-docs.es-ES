---
title: "Cómo agregar un ámbito forma4 | Documentos de Microsoft"
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
ms.assetid: 4ed56ada-a656-40b1-b34a-0c0803c01216
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a81bb85412784616d185b64ee39f1e777d19fea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>Cómo agregar una forma Ámbito
Siga estos pasos para agregar una **ámbito** forma.  
  
### <a name="to-add-a-scope-shape"></a>Para agregar una forma ámbito  
  
1.  Haga clic en la flecha situada bajo la **ReceiveFromIn** de puerto, seleccione **Insertar forma**y, a continuación, haga clic en **ámbito**.  
  
     En la forma Ámbito, se establecen operaciones que podrían tener errores.  
  
     Por ejemplo, se agrega un puerto de envío y uno de recepción en una orquestación SQLExecute. En este ejemplo, envía un mensaje a SERVER. SERVER da una respuesta. Ejecuta el resto de la orquestación y devuelve información al puerto OutFile.  
  
2.  En la forma ámbito, establezca el **transacciones** a **ninguno**.  
  
3.  Pulse el botón derecho dentro de la forma ámbito y seleccione **nuevo controlador de excepción**.  
  
     Esto crea la **excepción de filtrado** bloque. Si se produce una excepción desde el back-end, se detecta en el **excepción de filtrado** bloque.  
  
4.  En el **excepción de filtrado** bloque, debe agregar la lógica.  
    La lógica más importante que debe establecer es el tipo de mensaje de error que espera recibir.  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling4.md)