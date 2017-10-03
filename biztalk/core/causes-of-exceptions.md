---
title: Causas de excepciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, errors
- errors, orchestrations
- errors, causes
ms.assetid: b0422382-d034-4c58-87c6-fc269dbbfe43
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9006234d71751078269e5a88559839fdadd91e91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="causes-of-exceptions"></a>Causas de excepciones
Las excepciones se pueden generar en una orquestación de las siguientes formas:  
  
-   Por un **Iniciar excepción** forma, que produce una excepción inmediatamente y de forma incondicional. El control se transfiere desde el **Iniciar excepción** forma directamente al controlador de excepciones adecuado.  
  
-   Superación del tiempo de espera en una transacción que se ejecute durante mucho tiempo. Una excepción predefinida del sistema:**Microsoft.XLANG.BaseTypes.TimeOutException**: se produce en este caso.  
  
-   Otros errores de transacción. El motor de tiempo de ejecución inicia un mensaje definido por el sistema, por ejemplo, Microsoft.XLANG.BaseTypes.PersistenceException, para estos errores.  
  
-   Excepción de código de usuario. Cuando se realizan llamadas a un código de usuario externo en una orquestación, las clases de Common language runtime a las que se llama pueden iniciar excepciones. Si estas excepciones no se controlan en el código de usuario, terminan propagándose en el ámbito en que se realiza la llamada al código de usuario.  
  
-   Otras excepciones del sistema (un error de persistencia, una excepción .NET o del sistema, como una excepción de cargador de tipo, o un error de conversión de datos).  
  
> [!NOTE]
>  Cuando se produce una excepción de cargador de tipo, no se puede detectar la excepción en el **excepción de filtrado** bloquear en el mismo **ámbito** forma. Esto se debe a que la excepción es del cargador de tipo, no del proceso de orquestación de BizTalk. Por tanto, no sigue las reglas de control de flujo de BizTalk.  
  
-   Rama hermana del ámbito circundante que detiene la ejecución. En este caso, se inicia la excepción Microsoft.XLANG.BaseTypes.ForcedTerminationException para cada rama, en cuyo caso puede que desee agregar un controlador de excepciones a cada una de ellas. Un controlador de excepciones de este tipo no puede volver a iniciar la excepción ni debe intentar iniciar ningún otro tipo de excepción.  
  
-   Recepción de un mensaje externo que indica un error.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes de error](../core/fault-messages.md)   
 [Excepciones](../core/exceptions.md)