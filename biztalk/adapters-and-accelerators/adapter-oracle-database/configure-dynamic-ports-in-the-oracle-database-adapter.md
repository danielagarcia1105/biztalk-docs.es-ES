---
title: Configurar puertos dinámicos en el adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
ms.assetid: c4f67707-76a0-4d72-913f-03219b412e2a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b6a0dc67f764ad8e87d1a2c0d6965f5f5b437c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999061"
---
# <a name="configure-dynamic-ports-in-the-oracle-database-adapter"></a><span data-ttu-id="d9a56-102">Configurar puertos dinámicos en el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="d9a56-102">Configure dynamic ports in the Oracle Database Adapter</span></span>
<span data-ttu-id="d9a56-103">En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar los puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9a56-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="d9a56-104">Dado que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d9a56-104">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="d9a56-105">Para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], el URI, acción y el enlace es posible que se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** dar forma, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9a56-105">For the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], the URI, action, and binding may be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select";  
Request2(WCF.BindingType)="oracleDBBinding";  
Request2(WCF.UserName)="SCOTT";  
Request2(WCF.Password)="TIGER";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracledb://adapdoc/";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="d9a56-106">Si está usando un adaptador de WCF-OracleDB de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleDatabaseAdapter"`, donde **OracleDatabaseAdapter** es el nombre con el que se ha agregado el adaptador de WCF-OracleDB [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="d9a56-106">If you are using a WCF-OracleDB adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleDatabaseAdapter"`, where **OracleDatabaseAdapter** is the name with which you added the WCF-OracleDB adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="d9a56-107">En el ejemplo anterior,</span><span class="sxs-lookup"><span data-stu-id="d9a56-107">In the above example,</span></span>  
  
- <span data-ttu-id="d9a56-108">Se está creando la Solicitud2 mensaje del mensaje de la Solicitud1.</span><span class="sxs-lookup"><span data-stu-id="d9a56-108">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="d9a56-109">Los mensajes que se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9a56-109">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
- <span data-ttu-id="d9a56-110">Puerto de envío es el nombre del puerto de envío lógico en la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d9a56-110">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
  <span data-ttu-id="d9a56-111">El **expresión** forma es parte de la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d9a56-111">The **Expression** shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="d9a56-112">Al implementar la orquestación, también se crea el puerto de envío WCF-custom.</span><span class="sxs-lookup"><span data-stu-id="d9a56-112">When you deploy the orchestration, the WCF-custom send port is also created.</span></span>  
  
  <span data-ttu-id="d9a56-113">Para obtener más información sobre cómo configurar puertos dinámicos, consulte [configuración dinámica enviar puertos utilizando propiedades adaptadores de WCF contexto](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d9a56-113">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9a56-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9a56-114">See Also</span></span>  
[<span data-ttu-id="d9a56-115">Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="d9a56-115">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)