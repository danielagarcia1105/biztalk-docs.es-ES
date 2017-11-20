---
title: Uso de LoadGen 2007 con MSMQ | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8f23a86-0e6d-478a-87a3-5b02338c9afb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d67628b7863df3f2396cd9b45b55f42a488b8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-loadgen-2007-with-msmq"></a><span data-ttu-id="8f277-102">Uso de LoadGen 2007 con MSMQ</span><span class="sxs-lookup"><span data-stu-id="8f277-102">Using LoadGen 2007 with MSMQ</span></span>
<span data-ttu-id="8f277-103">La herramienta para la generación de cargas, Loadgen, le permite simular cargas pesadas en un sistema de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8f277-103">The Load Generation tool, Loadgen, enables you to simulate heavy loads on a BizTalk Server system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f277-104">La herramienta LoadGen 2007 está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span><span class="sxs-lookup"><span data-stu-id="8f277-104">The LoadGen 2007 tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span></span>  
  
 <span data-ttu-id="8f277-105">El uso de LoadGen es compatible con MSMQ aunque no realizamos el registro automático de los componentes COM de MSMQ durante la instalación, ya que es posible que el servicio de tiempo de ejecución de MSMQ no esté instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8f277-105">Using LoadGen with MSMQ is supported, but we do not auto-register the MSMQ COM components during installation since the MSMQ runtime service may not be installed on your computer.</span></span>  
  
 <span data-ttu-id="8f277-106">Para usar MSMQ y LoadGen, registre manualmente los archivos MSMQTransmitter.dll y ComMsmqMonitor.dll que se encuentran en el directorio bins:</span><span class="sxs-lookup"><span data-stu-id="8f277-106">To use MSMQ and LoadGen, manually register the MSMQTransmitter.dll and ComMsmqMonitor.dll files located in the bins directory:</span></span>  
  
```  
regsvr32 MSMQTransmitter.dll  
```  
  
 <span data-ttu-id="8f277-107">Si no registra los componentes COM de MSMQ, aparecerán los siguientes errores de tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="8f277-107">If you do not register the MSMQ COM components, you will receive the following runtime errors:</span></span>  
  
```  
Cannot Load Transport DLL C:\Program Files\LoadGen\Bins\MSMQTransport.dll for Section MSMQRxQTxn   
Exception has been thrown by the target of an invocation.  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f277-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f277-108">See Also</span></span>  
 [<span data-ttu-id="8f277-109">Escenarios de prueba para medir MST del motor de</span><span class="sxs-lookup"><span data-stu-id="8f277-109">Test Scenarios for Measuring MST of the Engine</span></span>](../core/test-scenarios-for-measuring-mst-of-the-engine.md)