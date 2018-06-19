---
title: Configurar puertos dinámicos con el adaptador de Siebel | Documentos de Microsoft
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
ms.openlocfilehash: b036bf772e3e9580c84616f74786d4908aca7515
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221916"
---
# <a name="configure-dynamic-ports-with-the-siebel-adapter"></a><span data-ttu-id="f5fc8-102">Configurar puertos dinámicos con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="f5fc8-102">Configure dynamic ports with the Siebel adapter</span></span>
<span data-ttu-id="f5fc8-103">En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5fc8-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="f5fc8-104">Dado que [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] mediante las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f5fc8-104">Because [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="f5fc8-105">Para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], el URI, acción y enlace podrían se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** forma, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5fc8-105">For the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the URI, action, and binding might be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
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
>  <span data-ttu-id="f5fc8-106">Si está usando un adaptador de WCF-Siebel en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SiebelAdapter"`, donde **SiebelAdapter** es el nombre con el que agregó el adaptador de WCF-Siebel en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="f5fc8-106">If you are using a WCF-Siebel adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SiebelAdapter"`, where **SiebelAdapter** is the name with which you added the WCF-Siebel adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="f5fc8-107">En el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="f5fc8-107">In the preceding example:</span></span>  
  
-   <span data-ttu-id="f5fc8-108">Se está creando Solicitud2 mensaje del mensaje Solicitud1.</span><span class="sxs-lookup"><span data-stu-id="f5fc8-108">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="f5fc8-109">Los mensajes se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5fc8-109">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
-   <span data-ttu-id="f5fc8-110">PuertoEnvío es el nombre del puerto de envío lógico en la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f5fc8-110">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
 <span data-ttu-id="f5fc8-111">La forma de expresión es parte de la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f5fc8-111">The Expression shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="f5fc8-112">Al implementar la orquestación, también se crea el puerto de envío WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="f5fc8-112">When you deploy the orchestration, the WCF-Custom send port is also created.</span></span>  
  
 <span data-ttu-id="f5fc8-113">Para obtener más información acerca de cómo configurar puertos dinámicos, consulte [configurar dinámica enviar puertos usando adaptadores de propiedades de contexto WCF](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f5fc8-113">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f5fc8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5fc8-114">See Also</span></span>  
[<span data-ttu-id="f5fc8-115">Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="f5fc8-115">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)