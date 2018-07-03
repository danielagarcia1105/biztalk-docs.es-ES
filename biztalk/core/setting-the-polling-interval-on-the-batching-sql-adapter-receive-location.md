---
title: Establecer el intervalo de sondeo en el adaptador de SQL por lotes de ubicación de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- polling interval [receive adapters]
- SQL adapters, polling interval
- receive locations, polling interval
- SQL adapters, receive locations
- receive locations, SQL adapters
ms.assetid: 9053b20d-145a-4445-b414-c0482cf975a0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caa2c97170ff374e9acf8c1d3d4ebc7258ad69ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005053"
---
# <a name="setting-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a><span data-ttu-id="72e7c-102">Definir el intervalo de sondeo en la ubicación de recepción del adaptador de SQL de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="72e7c-102">Setting the Polling Interval on the Batching SQL Adapter Receive Location</span></span>
<span data-ttu-id="72e7c-103">Puede establecer el intervalo de sondeo en el procesamiento por lotes de recepción del adaptador SQL ubicación (**BatchControlMessageRecvLoc**) diferente en los equipos de desarrollo y producción.</span><span class="sxs-lookup"><span data-stu-id="72e7c-103">You can set the polling interval on the batching SQL adapter receive location (**BatchControlMessageRecvLoc**) differently on development and production computers.</span></span> <span data-ttu-id="72e7c-104">En un servidor de desarrollo, Microsoft recomienda que mantenga el intervalo de sondeo en el valor predeterminado de 30 segundos para una rápida activación de la orquestación de procesamiento por lotes de un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="72e7c-104">On a development server, Microsoft recommends that you keep the polling interval at the default of 30 seconds, for quick activation of the batching orchestration for an agreement.</span></span> <span data-ttu-id="72e7c-105">Sin embargo, en un servidor de producción, un valor de 30 segundos puede afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="72e7c-105">However, on a production server, a setting of 30 seconds may affect performance.</span></span> <span data-ttu-id="72e7c-106">Una vez activado un lote, puede que desee definir el intervalo de sondeo a un valor mayor, como cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="72e7c-106">Once you have activated a batch, you may want to set the polling interval to a higher value, such as five minutes.</span></span>  
  
 <span data-ttu-id="72e7c-107">Para obtener más información acerca de las entidades, consulte [administrar entidades](../core/managing-parties.md).</span><span class="sxs-lookup"><span data-stu-id="72e7c-107">For more information about parties, see [Managing Parties](../core/managing-parties.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="72e7c-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="72e7c-108">Prerequisites</span></span>  
 <span data-ttu-id="72e7c-109">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72e7c-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-set-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a><span data-ttu-id="72e7c-110">Para definir el intervalo de sondeo en la ubicación de recepción del adaptador de SQL de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="72e7c-110">To set the Polling Interval on the Batching SQL Adapter Receive Location</span></span>  
  
1. <span data-ttu-id="72e7c-111">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **aplicación EDI de BizTalk**y, a continuación, haga clic en **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="72e7c-111">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **BizTalk EDI Application**, and then click **Receive Locations**.</span></span> <span data-ttu-id="72e7c-112">Haga clic en **BatchControlMessageRecvLoc**y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="72e7c-112">Right-click **BatchControlMessageRecvLoc**, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="72e7c-113">En el **propiedades de ubicación de recepción** cuadro de diálogo el **transporte** sección, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="72e7c-113">In the **Receive Location Properties** dialog box, in the **Transport** section, click **Configure**.</span></span>  
  
3. <span data-ttu-id="72e7c-114">En el **propiedades de transporte SQL** diálogo cuadro, cambie el valor de **intervalo de sondeo** desde el valor predeterminado de "30" al valor deseado.</span><span class="sxs-lookup"><span data-stu-id="72e7c-114">In the **SQL Transport Properties** dialog box, change the value for **Polling Interval** from the default value of "30" to the desired value.</span></span> <span data-ttu-id="72e7c-115">El valor recomendado para el servidor de producción es "5".</span><span class="sxs-lookup"><span data-stu-id="72e7c-115">The recommended value for a production server is "5".</span></span>  
  
4. <span data-ttu-id="72e7c-116">Cambie el valor de **unidad de sondeo de medida** desde el valor predeterminado de **segundos** a **minutos**.</span><span class="sxs-lookup"><span data-stu-id="72e7c-116">Change the value of **Polling Unit of Measure** from the default value of **Seconds** to **Minutes**.</span></span>  
  
5. <span data-ttu-id="72e7c-117">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo</span><span class="sxs-lookup"><span data-stu-id="72e7c-117">Click **OK**, and then click **OK** again</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e7c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="72e7c-118">See Also</span></span>  
 [<span data-ttu-id="72e7c-119">Administrar soluciones EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="72e7c-119">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)