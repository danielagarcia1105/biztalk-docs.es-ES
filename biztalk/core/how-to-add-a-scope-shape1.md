---
title: Cómo agregar un ámbito forma1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- Scope shapes, Catch Exception blocks
- Catch Exception blocks, Scope shapes
- adding, Scope shapes
ms.assetid: dfe039d1-4c4a-4e21-ae03-7ca534aafec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094f744f7d4d6d1c405ea50d222beb8c0a67920e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247188"
---
# <a name="how-to-add-a-scope-shape"></a>Cómo agregar una forma Ámbito
Para agregar una forma Ámbito, siga estos pasos.  
  
### <a name="to-add-a-scope-shape"></a>Para agregar una forma Ámbito  
  
1.  Haga clic en la flecha situada bajo la **ReceiveFromIn** de puerto, seleccione **Insertar forma**y, a continuación, haga clic en **ámbito**.  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     En la forma Ámbito, se establecen operaciones que podrían tener errores.  
  
     Por ejemplo, se agregan un puerto de envío y de recepción en una orquestación SQLExecute. En este ejemplo se envía un mensaje a DB2. DB2 da una respuesta. Ejecuta el resto de la orquestación y devuelve información al puerto OutFile.  
  
2.  En la forma ámbito, establezca el **transacciones** a **ninguno**.  
  
3.  Pulse el botón derecho dentro de la forma ámbito y seleccione **nuevo controlador de excepción**.  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     Se creará el bloque Excepción de filtrado. Si se produce una excepción desde el back-end, ésta se captura dentro del bloque de excepción de filtrado.  
  
4.  En el bloque Excepción de filtrado, debe agregar la lógica.  
  
     La lógica más importante que debe establecer es el tipo de mensaje de error que espera.  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling2.md)