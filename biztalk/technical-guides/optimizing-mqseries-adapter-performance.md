---
title: Optimizar el rendimiento del adaptador de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a46455c-a8d2-4427-99bb-4e3c6dbd9566
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d4a2bd1f2cfa338d31fd574879d73249d74d08b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299132"
---
# <a name="optimizing-mqseries-adapter-performance"></a><span data-ttu-id="cf92b-102">Optimizar el rendimiento del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="cf92b-102">Optimizing MQSeries Adapter Performance</span></span>
<span data-ttu-id="cf92b-103">Configurar el adaptador de MQSeries mediante las siguientes opciones cuando sea posible para aumentar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cf92b-103">Configure the MQSeries adapter by using the following settings when possible to increase performance.</span></span>  
  
## <a name="adjust-the-value-for-the-mqseries-receive-adapter-polling-threads"></a><span data-ttu-id="cf92b-104">Ajustar el valor de subprocesos de sondeo del adaptador de recepción de MQSeries</span><span class="sxs-lookup"><span data-stu-id="cf92b-104">Adjust the value for the MQSeries receive adapter polling threads</span></span>  
 <span data-ttu-id="cf92b-105">Aumentar el valor especificado para **subprocesos** en el **propiedades de transporte MQSeries** al configurar el adaptador de MQSeries ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="cf92b-105">Increase the value specified for **Threads** in the **MQSeries Transport Properties** when configuring MQSeries adapter receive locations.</span></span> <span data-ttu-id="cf92b-106">Al aumentar el valor predeterminado de 2 a un valor de 5 mejorará significativamente la velocidad a la que se pueden recibir mensajes mediante el adaptador de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="cf92b-106">Increasing this property from the default value of 2 to a value of 5 will significantly improve the rate at which messages can be received using the MQSeries adapter.</span></span>  
  
## <a name="disable-transaction-support-on-mqseries-receive-locations-where-not-required"></a><span data-ttu-id="cf92b-107">Deshabilitar compatibilidad con las transacciones en MQSeries ubicaciones de recepción no sea necesario</span><span class="sxs-lookup"><span data-stu-id="cf92b-107">Disable transaction support on MQSeries receive locations where not required</span></span>  
 <span data-ttu-id="cf92b-108">Compatibilidad con transacciones de adaptador de MQSeries supone una sobrecarga significativa.</span><span class="sxs-lookup"><span data-stu-id="cf92b-108">MQSeries adapter transaction support incurs significant overhead.</span></span> <span data-ttu-id="cf92b-109">Si la compatibilidad con transacciones no es un requisito empresarial, establezca el **admite transacción** valor en el **propiedades de transporte MQSeries** cuadro de diálogo en el valor predeterminado de **Sí**a **No**.</span><span class="sxs-lookup"><span data-stu-id="cf92b-109">If transaction support is not a business requirement, set the **Transaction Supported** value in the **MQSeries Transport Properties** dialog box from the default value of **Yes** to **No**.</span></span>  
  
## <a name="disable-ordered-delivery-of-messages-on-the-mqseries-adapter-when-not-required"></a><span data-ttu-id="cf92b-110">Deshabilitar la entrega ordenada de mensajes en el adaptador de MQSeries cuando no sea necesario</span><span class="sxs-lookup"><span data-stu-id="cf92b-110">Disable Ordered delivery of messages on the MQSeries Adapter when not required</span></span>  
 <span data-ttu-id="cf92b-111">Esta propiedad está habilitada, aplicará la entrega ordenada de mensajes tal y como se reciben desde o envía a la cola de MQSeries pero afectará al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cf92b-111">Enabling this property will enforce ordered delivery of messages as they are received from or sent to the MQSeries queue but will affect performance.</span></span> <span data-ttu-id="cf92b-112">Cuando se habilita la entrega ordenada, el runtime de mensajería usará un único subproceso para recibir mensajes de una cola de MQSeries determinada.</span><span class="sxs-lookup"><span data-stu-id="cf92b-112">When ordered delivery is enabled, the messaging runtime will use a single thread to receive messages from a given MQSeries queue.</span></span> <span data-ttu-id="cf92b-113">Si ordena la entrega de mensajes no es un requisito empresarial, no cambie el valor predeterminado de **ordenados** propiedad en el **propiedades de transporte MQSeries** cuadro de diálogo que se ha establecido como **n Orden**.</span><span class="sxs-lookup"><span data-stu-id="cf92b-113">If ordered delivery of messages is not a business requirement, then do not change the default value of **Ordered** property in the **MQSeries Transport Properties** dialog box which is set as **No Ordering**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf92b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf92b-114">See Also</span></span>  
 [<span data-ttu-id="cf92b-115">Optimizar el rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="cf92b-115">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)