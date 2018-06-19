---
title: 'Paso 1: Crear un Namespace de Bus de servicio | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede1ac50-bbfb-4aeb-8217-1877ae218f89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4d7630316f72fd63bac5ce7127b5451683e2f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276764"
---
# <a name="step-1-create-a-service-bus-namespace"></a><span data-ttu-id="4964c-102">Paso 1: Crear un Namespace de Bus de servicio</span><span class="sxs-lookup"><span data-stu-id="4964c-102">Step 1: Create a Service Bus Namespace</span></span>
<span data-ttu-id="4964c-103">En este paso, creará un [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)] espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4964c-103">In this step, you create a [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)] namespace.</span></span> <span data-ttu-id="4964c-104">Usará este espacio de nombres para hospedar un extremo de retransmisión para la recepción de notificaciones de oportunidades de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="4964c-104">You will use this namespace to host a relay endpoint for receiving opportunity notifications from Salesforce.</span></span> <span data-ttu-id="4964c-105">Más adelante en el proceso de creación de esta solución, usará este extremo de retransmisión para recibir el mensaje de notificación en un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4964c-105">Later in the process of creating this solution, you will use this relay endpoint to receive the notification message into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a><span data-ttu-id="4964c-106">Para crear un espacio de nombres de [!INCLUDE[sb](../includes/sb-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4964c-106">To create a [!INCLUDE[sb](../includes/sb-md.md)] namespace</span></span>  
  
1.  <span data-ttu-id="4964c-107">Inicie sesión en [http://manage.windowsazure.com](http://manage.windowsazure.com) con su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4964c-107">Log on to [http://manage.windowsazure.com](http://manage.windowsazure.com) using your Microsoft account.</span></span>  
  
2.  <span data-ttu-id="4964c-108">En la parte inferior de la página, haga clic en **New**, **servicios de aplicaciones**, **Service Bus Relay**y, a continuación, **creación rápida**.</span><span class="sxs-lookup"><span data-stu-id="4964c-108">At the bottom of the page, click **New**, **App Services**, **Service Bus Relay**, and then **Quick Create**.</span></span>  
  
3.  <span data-ttu-id="4964c-109">Escriba el espacio de nombres como `BtsSalesforce` y seleccione la región más cercana a su ubicación geográfica actual.</span><span class="sxs-lookup"><span data-stu-id="4964c-109">Enter the namespace as `BtsSalesforce` and select a region closest to your current geographical location.</span></span> <span data-ttu-id="4964c-110">Haga clic en **crear una retransmisión**.</span><span class="sxs-lookup"><span data-stu-id="4964c-110">Click **Create a Relay**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="4964c-111">Este espacio de nombres debe ser único global.</span><span class="sxs-lookup"><span data-stu-id="4964c-111">This namespace must be globally unique.</span></span> <span data-ttu-id="4964c-112">Por tanto, debe usar un espacio de nombres que no se mencione en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="4964c-112">So, you must use a namespace other than one mentioned in this tutorial.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4964c-113">Tenga en cuenta que la retransmisión no se crea como parte de la operación, solo el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4964c-113">Note that the relay is not created as part of the operation, only the namespace is.</span></span> <span data-ttu-id="4964c-114">El extremo de retransmisión se crea más adelante en este tutorial, cuando se configura una ubicación de recepción para el **SB-Messaging** adaptador.</span><span class="sxs-lookup"><span data-stu-id="4964c-114">The relay endpoint is created later in this tutorial when we configure a receive location for the **SB-Messaging** adapter.</span></span>  
  
4.  <span data-ttu-id="4964c-115">Después de crea el espacio de nombres, el estado se establece en **Active**.</span><span class="sxs-lookup"><span data-stu-id="4964c-115">After the namespace is created, the status is set to **Active**.</span></span> <span data-ttu-id="4964c-116">Una vez que el estado está activo, puede seleccionar el espacio de nombres y haga clic en **clave de acceso** en la parte inferior de la página para obtener detalles sobre cómo conectarse a la **BtsSalesforce** espacio de nombres, incluidos los valores de **Usuario predeterminado** y **clave predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="4964c-116">Once the status is active, you can select the namespace and click **Access Key** at the bottom of the page to get details on how to connect to the **BtsSalesforce** namespace, including the values for **Default User** and **Default Key**.</span></span> <span data-ttu-id="4964c-117">Necesitará estos detalles más adelante en el tutorial.</span><span class="sxs-lookup"><span data-stu-id="4964c-117">You will need these details later in the tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4964c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4964c-118">See Also</span></span>  
 [<span data-ttu-id="4964c-119">Tutorial: 6: Integración de BizTalk Server 2013 con Salesforce</span><span class="sxs-lookup"><span data-stu-id="4964c-119">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)