---
title: Cómo agregar un ámbito forma3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
ms.assetid: 8068ce97-4409-4c88-89e8-6505b56cefc5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8231dfed1ea84ba5c11e0352f789b92cc38d0f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>Cómo agregar una forma Ámbito
Use el procedimiento siguiente para agregar una forma Ámbito  
  
### <a name="to-add-a-scope-shape"></a>Para agregar una forma Ámbito  
  
1.  Haga clic en la flecha situada bajo la **recepción** de puerto, seleccione **Insertar forma**y, a continuación, seleccione **ámbito**.  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     En el **ámbito** forma, se establecen operaciones que podrían tener errores.  
  
     Por ejemplo, se agregan un puerto de envío y de recepción en una orquestación SQLExecute. En este ejemplo, envía un mensaje a SERVER. SERVER da una respuesta. Ejecuta el resto de la orquestación y devuelve información al puerto outFile.  
  
2.  En el **ámbito** forma, establezca el **transacciones** a **ninguno**.  
  
3.  Pulse el botón derecho dentro de la **ámbito** forma y seleccione **nuevo controlador de excepción**.  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     Esto crea la **excepción de filtrado** bloque. Si se produce una excepción desde el sistema back-end, se detecta en el **excepción de filtrado** bloque.  
  
4.  En el **excepción de filtrado** bloque, debe agregar la lógica.  
  
     La lógica más importante que debe establecer es el tipo de mensaje de error que espera recibir.  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling1.md)