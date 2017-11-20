---
title: "Configurar puertos dinámicos con Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a150ea-d957-4a37-81cf-c043a0a7d5cb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b02dc0cd4a4cf1d031acaf6d5a0e1c905ee225b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dynamic-ports-with-oracle-e-business-suite"></a><span data-ttu-id="9134c-102">Configurar puertos dinámicos con Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="9134c-102">Configure dynamic ports with Oracle E-Business Suite</span></span>
<span data-ttu-id="9134c-103">En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9134c-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="9134c-104">Dado que la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mediante las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9134c-104">Because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="9134c-105">Para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], el URI, la acción y el enlace pueden se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** forma, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9134c-105">For the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], the URI, action, and binding may be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="InterfaceTables/Insert/OFA/FA/FA_BOOKS";  
Request2(WCF.BindingType)="oracleEBSBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracleebs://ebs_instance";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
> [!NOTE]
>  <span data-ttu-id="9134c-106">Si está usando un adaptador de WCF-OracleEBS en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`, donde **OracleEBSAdapter** es el nombre con el que agregó el adaptador de WCF-OracleEBS [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="9134c-106">If you are using a WCF-OracleEBS adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`, where **OracleEBSAdapter** is the name with which you added the WCF-OracleEBS adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="9134c-107">En el ejemplo anterior,</span><span class="sxs-lookup"><span data-stu-id="9134c-107">In the preceding example,</span></span>  
  
-   <span data-ttu-id="9134c-108">Se está creando Solicitud2 mensaje del mensaje Solicitud1.</span><span class="sxs-lookup"><span data-stu-id="9134c-108">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="9134c-109">Los mensajes se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9134c-109">Both messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
-   <span data-ttu-id="9134c-110">PuertoEnvío es el nombre del puerto de envío lógico en la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9134c-110">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
 <span data-ttu-id="9134c-111">El **expresión** forma es parte de la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9134c-111">The **Expression** shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="9134c-112">Implementación de la orquestación, también crea un puerto de envío WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="9134c-112">Deploying the orchestration also creates a WCF-Custom send port.</span></span>  
  
 <span data-ttu-id="9134c-113">Para obtener más información acerca de cómo configurar puertos dinámicos, consulte [configurar dinámica enviar puertos usando adaptadores de propiedades de contexto WCF](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9134c-113">For more information about configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9134c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9134c-114">See Also</span></span>  
[<span data-ttu-id="9134c-115">Bloques de creación para crear aplicaciones de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="9134c-115">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)