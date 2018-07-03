---
title: Configurar puertos dinámicos en el adaptador de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
- configuring, dynamic ports
ms.assetid: 4d6569f9-e513-47f3-b2c1-4c21bafb2bf2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de45553cfad2db19cfe16bbcd55420019b4971e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971509"
---
# <a name="configure-dynamic-ports-in-the-sap-adapter"></a><span data-ttu-id="9d2fb-102">Configurar puertos dinámicos en el adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="9d2fb-102">Configure dynamic ports in the SAP adapter</span></span>
## <a name="use-message-context-properties"></a><span data-ttu-id="9d2fb-103">Usar propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="9d2fb-103">Use message context properties</span></span>
<span data-ttu-id="9d2fb-104">En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar los puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d2fb-104">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="9d2fb-105">Dado que [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9d2fb-105">Because [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="9d2fb-106">Para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], el URI, acción y el enlace es posible que se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en la forma de expresión, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d2fb-106">For the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the URI, action, and binding might be determined from a property on an incoming message, and then specified in the Expression shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET";  
Request2(WCF.BindingType)="sapBinding";  
Request2(WCF.UserName)="YourUserName";  
Request2(WCF.Password)="YourPassword";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="sap://CLIENT=800;LANG=EN;@A/YourSAPHost/00";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="9d2fb-107">Si está usando un adaptador de SAP de WCF en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`, donde **SAPAdapter** es el nombre con el que se ha agregado el adaptador SAP de WCF en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="9d2fb-107">If you are using a WCF-SAP adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`, where **SAPAdapter** is the name with which you added the WCF-SAP adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="9d2fb-108">En el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="9d2fb-108">In the preceding example:</span></span>  
  
- <span data-ttu-id="9d2fb-109">Se está creando la Solicitud2 mensaje del mensaje de la Solicitud1.</span><span class="sxs-lookup"><span data-stu-id="9d2fb-109">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="9d2fb-110">Los mensajes que se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d2fb-110">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
- <span data-ttu-id="9d2fb-111">Puerto de envío es el nombre del puerto de envío lógico en la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9d2fb-111">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
  <span data-ttu-id="9d2fb-112">La forma de expresión es parte de la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9d2fb-112">The Expression shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="9d2fb-113">Al implementar la orquestación, también se crea el puerto de envío WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="9d2fb-113">When you deploy the orchestration, the WCF-Custom send port is also created.</span></span>  
  
  <span data-ttu-id="9d2fb-114">Para obtener más información sobre cómo configurar puertos dinámicos, consulte [configuración dinámica enviar puertos utilizando propiedades adaptadores de WCF contexto](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9d2fb-114">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d2fb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d2fb-115">See Also</span></span>  
[<span data-ttu-id="9d2fb-116">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="9d2fb-116">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)