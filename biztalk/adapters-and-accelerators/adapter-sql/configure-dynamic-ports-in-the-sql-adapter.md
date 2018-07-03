---
title: Configurar puertos dinámicos en el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98b66ed-0bf7-4b24-9d16-9792d033b818
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c23bce67dbc4eaca8441e6e7d07573724225cc45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976237"
---
# <a name="configure-dynamic-ports-in-the-sql-adapter"></a><span data-ttu-id="f6e32-102">Configurar puertos dinámicos en el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="f6e32-102">Configure dynamic ports in the SQL adapter</span></span>
<span data-ttu-id="f6e32-103">En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar los puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6e32-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="f6e32-104">Dado que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f6e32-104">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] by using message context properties.</span></span>  

## <a name="use-an-expression-shape"></a><span data-ttu-id="f6e32-105">Usar una forma de expresión</span><span class="sxs-lookup"><span data-stu-id="f6e32-105">Use an expression shape</span></span>  
 <span data-ttu-id="f6e32-106">Para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], el URI, acción y el enlace es posible que se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** dar forma, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6e32-106">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], the URI, action, and binding may be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="TableOp/Insert/dbo/CustomerTable";  
Request2(WCF.BindingType)="sqlBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="mssql://sql_server/my_instance/my_database";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="f6e32-107">Si está usando un adaptador de WCF-SQL en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SQLAdapter"`, donde **SQLAdapter** es el nombre con el que se ha agregado el adaptador de WCF-SQL [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="f6e32-107">If you are using a WCF-SQL adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SQLAdapter"`, where **SQLAdapter** is the name with which you added the WCF-SQL adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="f6e32-108">En el ejemplo anterior,</span><span class="sxs-lookup"><span data-stu-id="f6e32-108">In the preceding example,</span></span>  
  
- <span data-ttu-id="f6e32-109">Se está creando la Solicitud2 mensaje del mensaje de la Solicitud1.</span><span class="sxs-lookup"><span data-stu-id="f6e32-109">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="f6e32-110">Ambos mensajes se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6e32-110">Both messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
- <span data-ttu-id="f6e32-111">Puerto de envío es el nombre del puerto de envío lógico en la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f6e32-111">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
  <span data-ttu-id="f6e32-112">El **expresión** forma es parte de la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f6e32-112">The **Expression** shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="f6e32-113">Implementación de la orquestación también crea un puerto de envío WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="f6e32-113">Deploying the orchestration also creates a WCF-Custom send port.</span></span>  
  
  <span data-ttu-id="f6e32-114">Para obtener más información acerca de cómo configurar puertos dinámicos, consulte [configuración dinámica enviar puertos utilizando propiedades adaptadores de WCF contexto](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f6e32-114">For more information about configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f6e32-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6e32-115">See Also</span></span>  
[<span data-ttu-id="f6e32-116">Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="f6e32-116">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)