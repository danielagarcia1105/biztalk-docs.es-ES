---
title: Tipos de errores de mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transformation stage
- assembly stage
- errors, disassembly stage
- errors, assembly stage
- routing, errors
- errors, transformation stage
- errors, messages [HAT]
- errors, routing
- disassembly stage, errors
- messages, errors [HAT]
ms.assetid: 3a8e1c58-4b53-4439-837d-aaa233eb9158
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 466c7c21fd1a00e192307dd82384dc613b6697a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286756"
---
# <a name="types-of-message-failures"></a>Tipos de errores de mensaje
En este tema se enumeran los distintos puntos en los que puede producirse un error de mensaje.  
  
 **Errores en la fase de desensamblado**  
  
 Puede producirse un error de procesamiento en la fase de desensamblado, es decir, en uno de los componentes de canalización. Por ejemplo, se puede producir un error de descifrado debido a la ausencia del certificado de descifrado en el servidor de procesamiento, o bien un error de análisis a causa de problemas en el esquema o en el mensaje.  
  
 **Errores de enrutamiento**  
  
 Cuando un mensaje se ha desensamblado correctamente, el siguiente punto posible de error es el enrutamiento; por ejemplo, si los usuarios habilitan la ubicación de recepción apropiada en una orquestación pero olvidan dar de alta dicha orquestación. En este caso, se produce un error de enrutamiento del mensaje recogido desde la ubicación de recepción, y la base de datos de cuadro de mensajes genera un informe Error de enrutamiento.  
  
 Los informes Error de enrutamiento se muestran en la consola de administración de BizTalk Server como mensajes suspendidos no reanudables. Cada informe Error de enrutamiento contiene una instantánea de la propiedad de mensaje, tomada en el momento en que se produjo el error. Puede utilizar la información de cada informe para determinar por qué se ha producido un error de enrutamiento en el mensaje asociado. Si el mensaje asociado es reanudable, puede corregir el problema de enrutamiento, y seguidamente reanudar el mensaje para continuar con su procesamiento. Los informes Error de enrutamiento se enumeran en la lista de resultados, con el nombre de servicio y tipo de servicio en blanco. Cuando se finaliza una instancia suspendida, el informe Error de enrutamiento asociado a la instancia suspendida es eliminado automáticamente por el trabajo Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb, que se ejecuta cada minuto de forma predeterminada. Para obtener más información acerca del trabajo Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb, consulte [estructura de base de datos y trabajos](../core/database-structure-and-jobs.md).  
  
 **Errores durante la fase de transformación**  
  
-   **Mensajes recibidos**. Cuando se recibe un mensaje procedente de una ubicación de recepción, se efectúa el desensamblado del mensaje (por ejemplo, se descifra y se analiza) y, de forma opcional, puede transformarse a un formato distinto mediante una asignación de entrada especificada en un puerto de envío, además de publicarse en el cuadro de mensajes para su enrutamiento a una orquestación o a un puerto de envío. En este caso, puede producirse un error de procesamiento durante la fase de transformación debido a una asignación de entrada incorrecta, o a problemas en el esquema o en el mensaje recibido.  
  
-   **Los mensajes enviados**. Cuando un mensaje debe enviarse a una ubicación de envío, una asignación de entrada configurada en el puerto de envío puede, de forma opcional, transformar el mensaje. A continuación, el mensaje transformado se ensambla y se entrega al adaptador para su transmisión definitiva a la ubicación de envío. En este caso, puede producirse un error de procesamiento en la fase de transformación debido a una asignación de salida incorrecta, o a problemas en el esquema o en el mensaje de origen.  
  
 **Errores en la fase de ensamblado de mensaje**  
  
 También puede producirse un error de procesamiento durante la fase de ensamblado del mensaje, es decir, en el componente de canalización. Cuando el mensaje se ha ensamblado correctamente, el siguiente punto posible de error es la transmisión a la ubicación de envío; por ejemplo, cuando la ubicación de envío (que pertenece a un socio comercial) no funciona o no existe.  
  
## <a name="see-also"></a>Vea también  
 [Investigación de orquestación, puerto y errores de mensaje](../core/investigating-orchestration-port-and-message-failures.md)