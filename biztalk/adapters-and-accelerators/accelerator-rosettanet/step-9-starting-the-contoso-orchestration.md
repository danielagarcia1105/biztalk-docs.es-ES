---
title: 'Paso 9: Iniciar la orquestación de Contoso | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, starting orchestrations
ms.assetid: df3ff90b-5a9f-4ae7-819a-11cb36d64ccd
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 994355b67c19a7411c62f8858033e44cb8bdf3f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990831"
---
# <a name="step-9-starting-the-contoso-orchestration"></a><span data-ttu-id="cec89-102">Paso 9: Iniciar la orquestación de Contoso</span><span class="sxs-lookup"><span data-stu-id="cec89-102">Step 9: Starting the Contoso Orchestration</span></span>
<span data-ttu-id="cec89-103">En este paso completará el proceso de configuración de los puertos mediante la definición de las ubicaciones físicas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="cec89-103">In this step, you complete the port configuration process by defining the physical source and destination locations.</span></span> <span data-ttu-id="cec89-104">Enlazar los puertos físicos a los puertos lógicos que creó en [paso 7: crear y configurar puertos](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md).</span><span class="sxs-lookup"><span data-stu-id="cec89-104">You bind the physical ports to the logical ports you created in [Step 7: Creating and Configuring Ports](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md).</span></span> <span data-ttu-id="cec89-105">A continuación, dará de alta el servicio para asociar el proceso de negocio que ha diseñado en la orquestación con el entorno físico en el que se ejecutará la orquestación.</span><span class="sxs-lookup"><span data-stu-id="cec89-105">You then enlist the service to associate the business process that you designed in the orchestration with the physical environment that the orchestration will run in.</span></span> <span data-ttu-id="cec89-106">Por último, iniciará la orquestación para que pueda participar en transacciones de negocio con Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="cec89-106">Finally, you start the orchestration so that it can participate in business transactions with Fabrikam.</span></span>  
  
### <a name="to-bind-the-orchestration-ports"></a><span data-ttu-id="cec89-107">Para enlazar los puertos de orquestación</span><span class="sxs-lookup"><span data-stu-id="cec89-107">To bind the orchestration ports</span></span>  
  
1.  <span data-ttu-id="cec89-108">Abra el **Explorador de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="cec89-108">Open **BizTalk Explorer**.</span></span>  
  
2.  <span data-ttu-id="cec89-109">En el Explorador de BizTalk, expanda **Base de datos de configuración de BizTalk**y **Orquestaciones**, haga clic con el botón derecho en **ContosoPriceAndAvailability.PrivateResponderProcess**y, a continuación, haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="cec89-109">In BizTalk Explorer, expand **BizTalk Configuration Database**, expand **Orchestrations**, right-click **ContosoPriceAndAvailability.PrivateResponderProcess**, and then click **Bind**.</span></span>  
  
3.  <span data-ttu-id="cec89-110">En la página de propiedades de enlaces de puertos, seleccione **LOB_To_PrivateResponder** en la propiedad **FromLOB** .</span><span class="sxs-lookup"><span data-stu-id="cec89-110">On the Port Bindings Properties page, select **LOB_To_PrivateResponder** in the **FromLOB** property.</span></span>  
  
4.  <span data-ttu-id="cec89-111">En el cuadro **ContosoSQLReqResponsePort** , seleccione **3A2SQLReqResponseSendPort**.</span><span class="sxs-lookup"><span data-stu-id="cec89-111">In the **ContosoSQLReqResponsePort** box, select **3A2SQLReqResponseSendPort**.</span></span>  
  
5.  <span data-ttu-id="cec89-112">En la propiedad **ToLOB** , expanda **Puertos de envío** y seleccione **PrivateResponder_To_LOB**.</span><span class="sxs-lookup"><span data-stu-id="cec89-112">In the **ToLOB** property, expand **Send Ports** and select **PrivateResponder_To_LOB**.</span></span>  
  
6.  <span data-ttu-id="cec89-113">En la ventana de configuración en el panel izquierdo, seleccione **Host**.</span><span class="sxs-lookup"><span data-stu-id="cec89-113">In the Configuration window in the left pane, select **Host**.</span></span>  
  
7.  <span data-ttu-id="cec89-114">En la propiedad **Host** , en la categoría **Host de BizTalk** , seleccione **BizTalkServerApplication** en la lista desplegable y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cec89-114">In the **Host** property, in the **BizTalk Host** category, select **BizTalkServerApplication** from the drop-down list, and then click **OK**.</span></span>  
  
### <a name="to-start-the-biztalk-runtime-process"></a><span data-ttu-id="cec89-115">Para iniciar el proceso de tiempo de ejecución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="cec89-115">To start the BizTalk runtime process</span></span>  
  
1. <span data-ttu-id="cec89-116">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="cec89-116">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cec89-117">En la consola de administración de BizTalk, en el panel izquierdo, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, Expanda **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="cec89-117">In the BizTalk Administration Console, in the left pane, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Host Instances**.</span></span>  
  
3. <span data-ttu-id="cec89-118">Compruebe que el estado del servicio **BizTalkServerApplication** es **En ejecución**.</span><span class="sxs-lookup"><span data-stu-id="cec89-118">Verify that the status of the **BizTalkServerApplication** service is **Running**.</span></span>  
  
### <a name="to-enlist-and-start-the-orchestration"></a><span data-ttu-id="cec89-119">Para dar de alta e iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="cec89-119">To enlist and start the orchestration</span></span>  
  
1.  <span data-ttu-id="cec89-120">En el panel izquierdo de la consola de administración de BizTalk, expanda **Aplicaciones**y **Aplicación de BizTalk 1**, y haga clic en **Orquestaciones**.</span><span class="sxs-lookup"><span data-stu-id="cec89-120">In the left pane of the BizTalk Administration Console, expand **Applications**, expand **BizTalk Application 1**, and then click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="cec89-121">En el panel derecho, haga clic con el botón derecho en la orquestación **ContosoPriceAndAvailability.PrivateResponderProcess** y, a continuación, haga clic en **Dar de alta**.</span><span class="sxs-lookup"><span data-stu-id="cec89-121">In the right pane, right-click the **ContosoPriceAndAvailability.PrivateResponderProcess** orchestration, and then click **Enlist**.</span></span>  
  
3.  <span data-ttu-id="cec89-122">Haga clic con el botón derecho en la orquestación **ContosoPriceAndAvailability.PrivateResponderProcess** y, a continuación, haga clic en **Iniciar** para iniciar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="cec89-122">Right-click the **ContosoPriceAndAvailability.PrivateResponderProcess** orchestration, and then click **Start** to start the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec89-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="cec89-123">See Also</span></span>  
 [<span data-ttu-id="cec89-124">Creación de la solución de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="cec89-124">Creating the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)