---
title: Configurar puertos dinámicos con el adaptador de Siebel | Microsoft Docs
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
ms.assetid: a3516c2c-d40e-426b-bf3f-f9dc3de105ef
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80a568880aaf8b11cc79e04c7eaee5a5c9e512a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000860"
---
# <a name="configure-dynamic-ports-with-the-siebel-adapter"></a><span data-ttu-id="9b879-102">Configurar puertos dinámicos con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="9b879-102">Configure dynamic ports with the Siebel adapter</span></span>
<span data-ttu-id="9b879-103">En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar los puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b879-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="9b879-104">Dado que [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] mediante las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b879-104">Because [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="9b879-105">Para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], el URI, acción y el enlace es posible que se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** dar forma, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b879-105">For the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the URI, action, and binding might be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert";  
Request2(WCF.BindingType)="siebelBinding";  
Request2(WCF.UserName)="YourUserName";  
Request2(WCF.Password)="YourPassword";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="siebel://mySiebelServer:1234?SiebelObjectManager=SSEObjMgr&SiebelEnterpriseServer=myEnterpriseServer&Language=enu";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="9b879-106">Si está usando un adaptador de WCF-Siebel en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SiebelAdapter"`, donde **SiebelAdapter** es el nombre con el que se ha agregado el adaptador de WCF-Siebel [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="9b879-106">If you are using a WCF-Siebel adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SiebelAdapter"`, where **SiebelAdapter** is the name with which you added the WCF-Siebel adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="9b879-107">En el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="9b879-107">In the preceding example:</span></span>  
  
- <span data-ttu-id="9b879-108">Se está creando la Solicitud2 mensaje del mensaje de la Solicitud1.</span><span class="sxs-lookup"><span data-stu-id="9b879-108">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="9b879-109">Los mensajes que se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b879-109">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
- <span data-ttu-id="9b879-110">Puerto de envío es el nombre del puerto de envío lógico en la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9b879-110">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
  <span data-ttu-id="9b879-111">La forma de expresión es parte de la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9b879-111">The Expression shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="9b879-112">Al implementar la orquestación, también se crea el puerto de envío WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="9b879-112">When you deploy the orchestration, the WCF-Custom send port is also created.</span></span>  
  
  <span data-ttu-id="9b879-113">Para obtener más información sobre cómo configurar puertos dinámicos, consulte [configuración dinámica enviar puertos utilizando propiedades adaptadores de WCF contexto](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9b879-113">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b879-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b879-114">See Also</span></span>  
[<span data-ttu-id="9b879-115">Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="9b879-115">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)