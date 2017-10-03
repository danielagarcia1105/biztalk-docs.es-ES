---
title: 'Paso 5: Crear un acuerdo reflejado | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, mirror agreements
- loopback tutorial, creating mirror agreements
- agreements, mirror agreements
ms.assetid: 6aa70b1e-7d38-49f7-9d5f-f008cbe3df66
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ddb7c7dcad8bb278b318cdc599640b479baafa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-create-a-mirror-agreement"></a><span data-ttu-id="338dd-102">Paso 5: Crear un acuerdo de reflejo</span><span class="sxs-lookup"><span data-stu-id="338dd-102">Step 5: Create a Mirror Agreement</span></span>
<span data-ttu-id="338dd-103">En este paso, utilizará la utilidad de bucle invertido para crear un acuerdo de reflejado simular al socio comercial en el mismo equipo en el que ha configurado la organización principal.</span><span class="sxs-lookup"><span data-stu-id="338dd-103">In this step, you use the Loopback utility to create a mirror agreement simulating the trading partner on the same computer on which you configured the home organization.</span></span> <span data-ttu-id="338dd-104">La utilidad de bucle invertido es una herramienta de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="338dd-104">The Loopback utility is a command-line tool.</span></span>  
  
### <a name="to-create-a-mirror-agreement-using-the-loopback-utility"></a><span data-ttu-id="338dd-105">Para crear un acuerdo de reflejado mediante la utilidad de bucle invertido</span><span class="sxs-lookup"><span data-stu-id="338dd-105">To create a mirror agreement using the Loopback utility</span></span>  
  
1.  <span data-ttu-id="338dd-106">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="338dd-106">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="338dd-107">En el símbolo del sistema, vaya a \< *unidad*>: \Program BizTalk \<versión > Accelerator for RosettaNet\SDK.</span><span class="sxs-lookup"><span data-stu-id="338dd-107">At the command prompt, move to \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK.</span></span> <span data-ttu-id="338dd-108">Escriba el siguiente comando y, a continuación, presione **ENTRAR**:</span><span class="sxs-lookup"><span data-stu-id="338dd-108">Type the following command and then press **Enter**:</span></span>  
  
    ```  
    Loopback /enable HOME  
    ```  
  
3.  <span data-ttu-id="338dd-109">Cuando haya finalizado el comando ejecutado en el paso 2, escriba el siguiente comando en el símbolo del sistema y, a continuación, presione **ENTRAR**:</span><span class="sxs-lookup"><span data-stu-id="338dd-109">After the command executed in step 2 has completed, type the following command in the command prompt, and then press **Enter**:</span></span>  
  
    ```  
    Loopback /mirror "Trade Agreement"   
    ```  
  
 <span data-ttu-id="338dd-110">La utilidad de bucle invertido crea automáticamente un acuerdo comercial de reflejo de la organización del asociado y de puertos de envío para la organización principal (iniciador).</span><span class="sxs-lookup"><span data-stu-id="338dd-110">The Loopback utility automatically creates send ports for the home organization (initiator) and a mirror trade agreement for the partner organization.</span></span> <span data-ttu-id="338dd-111">El socio comercial utiliza los dos nuevos puertos de envío para comunicarse con la organización principal.</span><span class="sxs-lookup"><span data-stu-id="338dd-111">The partner uses the two new send ports to communicate with the home organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="338dd-112">Volver a debe reflejar el acuerdo comercial cada vez que actualice el acuerdo comercial original.</span><span class="sxs-lookup"><span data-stu-id="338dd-112">You must re-mirror the trade agreement whenever you update the original trade agreement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338dd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="338dd-113">See Also</span></span>  
 [<span data-ttu-id="338dd-114">Paso 6: Iniciar orquestaciones</span><span class="sxs-lookup"><span data-stu-id="338dd-114">Step 6: Start Orchestrations</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)