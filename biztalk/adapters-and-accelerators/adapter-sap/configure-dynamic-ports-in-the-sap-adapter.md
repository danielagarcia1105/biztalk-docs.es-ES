---
title: "Configurar puertos dinámicos en el adaptador SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
- configuring, dynamic ports
ms.assetid: 4d6569f9-e513-47f3-b2c1-4c21bafb2bf2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea1a63bf66cd798656f1303513b5200a49243138
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dynamic-ports-in-the-sap-adapter"></a><span data-ttu-id="324a3-102">Configurar puertos dinámicos en el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="324a3-102">Configure dynamic ports in the SAP adapter</span></span>
## <a name="use-message-context-properties"></a><span data-ttu-id="324a3-103">Usar propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="324a3-103">Use message context properties</span></span>
<span data-ttu-id="324a3-104">En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="324a3-104">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="324a3-105">Dado que [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="324a3-105">Because [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="324a3-106">Para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], el URI, acción y enlace podrían se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en la forma de expresión, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="324a3-106">For the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the URI, action, and binding might be determined from a property on an incoming message, and then specified in the Expression shape, as shown in the following example:</span></span>  
  
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
>  <span data-ttu-id="324a3-107">Si está usando un adaptador de WCF-SAP en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`, donde **SAPAdapter** es el nombre con el que agregó el adaptador de WCF-SAP en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="324a3-107">If you are using a WCF-SAP adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`, where **SAPAdapter** is the name with which you added the WCF-SAP adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="324a3-108">En el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="324a3-108">In the preceding example:</span></span>  
  
-   <span data-ttu-id="324a3-109">Se está creando Solicitud2 mensaje del mensaje Solicitud1.</span><span class="sxs-lookup"><span data-stu-id="324a3-109">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="324a3-110">Los mensajes se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="324a3-110">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
-   <span data-ttu-id="324a3-111">PuertoEnvío es el nombre del puerto de envío lógico en la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="324a3-111">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
 <span data-ttu-id="324a3-112">La forma de expresión es parte de la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="324a3-112">The Expression shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="324a3-113">Al implementar la orquestación, también se crea el puerto de envío WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="324a3-113">When you deploy the orchestration, the WCF-Custom send port is also created.</span></span>  
  
 <span data-ttu-id="324a3-114">Para obtener más información acerca de cómo configurar puertos dinámicos, consulte [configurar dinámica enviar puertos usando adaptadores de propiedades de contexto WCF](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span><span class="sxs-lookup"><span data-stu-id="324a3-114">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="324a3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="324a3-115">See Also</span></span>  
[<span data-ttu-id="324a3-116">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="324a3-116">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)