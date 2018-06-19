---
title: Control de transacciones con el adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, transaction handling
- transactions, MSMQ adapters
ms.assetid: 2e5dd0da-3852-48bf-9372-b019ecab23be
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bea79413042ec99cfd1cbc5bc6dee500aef4ac4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008749"
---
# <a name="transaction-handling-with-the-msmq-adapter"></a>Control de transacciones con el adaptador de MSMQ
En esta sección se analiza la forma en la que funcionan las transacciones en el envío y la recepción.  
  
> [!NOTE]
>  Para el adaptador MSMQ, una transacción se extiende desde la base de datos de cuadro de mensajes de BizTalk a la cola de Message Queue Server local, aun si se utiliza una cola remota.  
  
 Es posible utilizar transacciones tanto en el envío como en la recepción con el adaptador de MSMQ. En envíos de transacción, el adaptador acumula mensajes hasta que tiene un lote completo. Seguidamente, el adaptador envía el lote al servicio Message Queue Server local como una sola transacción. Si el envío no se realiza correctamente, el adaptador intenta reenviar el lote. Si el reenvío no se efectúa correctamente, el adaptador se mueve al transporte secundario.  
  
> [!NOTE]
>  El adaptador admite las lecturas transaccionales de colas remotas únicamente con Message Queue Server 4.0 o posterior. En este escenario el servidor BizTalk Server y el servidor remoto de Message Queue Server deben ejecutar Message Queue Server 4.0 o posterior.  
  
 En las recepciones de transacción, el adaptador suspende los mensajes con errores para que, de este modo, no pierda ninguno de los mensajes. Durante una recepción de transacción, el adaptador agrega mensajes a un lote hasta que éste se completa. A continuación, envía el lote:  
  
-   Si no hay ningún problema y el servidor recibe los mensajes, el adaptador confirma la transacción.  
  
-   Si hay algún problema, el adaptador crea un nuevo lote como parte de la transacción actual. Seguidamente, mueve todos los mensajes que presenten problemas al nuevo lote. A continuación, reenvía el primer lote y envía el nuevo lote como mensajes suspendidos. El adaptador confirma la transacción si no hay ningún problema durante este reenvío.  
  
 Si se ejecuta un controlador de envío de adaptador de MSMQ en una instancia agrupada de host de BizTalk, se debería agrupar el servicio MSMQ en el mismo grupo de clúster para garantizar la coherencia transaccional.  
  
 Si se deshabilita el "Acceso a DTC desde la red" en la utilidad DCOMCNFG, se producirá un error en operación de recepción remota de transacciones MSMQ y creará un mensaje de error críptico.  Para efectuar una recepción remota de transacciones con el adaptador de MSMQ, debe estar habilitado "Acceso a DTC desde la red". Puede encontrar más información en [http://go.microsoft.com/fwlink/?LinkId=124623](http://go.microsoft.com/fwlink/?LinkId=124623).  
  
 Si se ejecuta un controlador de recepción del adaptador de MSMQ en una instancia agrupada de host de BizTalk, se debería agrupar el servicio MSMQ en el mismo grupo de clúster para admitir lecturas de transacción locales, puesto que MSMQ no admite lecturas transaccionales remotas. Para obtener más información sobre la ejecución de controladores de adaptador MSMQ en una instancia en clúster de un Host de BizTalk, consulte [consideraciones para ejecutar controladores de adaptador en un Host agrupado](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).  
  
## <a name="see-also"></a>Vea también  
 [Mensajería confiable con el adaptador de MSMQ](../core/reliable-messaging-with-the-msmq-adapter.md)