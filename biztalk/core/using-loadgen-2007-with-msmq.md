---
title: Uso de LoadGen 2007 con MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8f23a86-0e6d-478a-87a3-5b02338c9afb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d67628b7863df3f2396cd9b45b55f42a488b8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287132"
---
# <a name="using-loadgen-2007-with-msmq"></a>Uso de LoadGen 2007 con MSMQ
La herramienta para la generación de cargas, Loadgen, le permite simular cargas pesadas en un sistema de BizTalk Server.  
  
> [!NOTE]
>  La herramienta LoadGen 2007 está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).  
  
 El uso de LoadGen es compatible con MSMQ aunque no realizamos el registro automático de los componentes COM de MSMQ durante la instalación, ya que es posible que el servicio de tiempo de ejecución de MSMQ no esté instalado en el equipo.  
  
 Para usar MSMQ y LoadGen, registre manualmente los archivos MSMQTransmitter.dll y ComMsmqMonitor.dll que se encuentran en el directorio bins:  
  
```  
regsvr32 MSMQTransmitter.dll  
```  
  
 Si no registra los componentes COM de MSMQ, aparecerán los siguientes errores de tiempo de ejecución:  
  
```  
Cannot Load Transport DLL C:\Program Files\LoadGen\Bins\MSMQTransport.dll for Section MSMQRxQTxn   
Exception has been thrown by the target of an invocation.  
```  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md)