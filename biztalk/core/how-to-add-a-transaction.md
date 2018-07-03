---
title: Cómo agregar una transacción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, transactions
- transactions, adding
ms.assetid: 25385c20-3025-4cf1-bc1f-ef266e081bad
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3a4fcb1116e5b4a0cd3a8b62dc1283abc3215c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009973"
---
# <a name="how-to-add-a-transaction"></a><span data-ttu-id="e0828-102">Cómo agregar una transacción</span><span class="sxs-lookup"><span data-stu-id="e0828-102">How to Add a Transaction</span></span>
<span data-ttu-id="e0828-103">Para agregar una transacción, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e0828-103">Follow these steps to add a transaction.</span></span>  
  
### <a name="to-add-a-transaction"></a><span data-ttu-id="e0828-104">Para agregar una transacción</span><span class="sxs-lookup"><span data-stu-id="e0828-104">To add a transaction</span></span>  
  
1. <span data-ttu-id="e0828-105">Haga clic en el **transacciones** ficha.</span><span class="sxs-lookup"><span data-stu-id="e0828-105">Click the **Transactions** tab.</span></span>  
  
2. <span data-ttu-id="e0828-106">Haga clic en **Agregar transacción**.</span><span class="sxs-lookup"><span data-stu-id="e0828-106">Click **Add Transaction**.</span></span>  
  
3. <span data-ttu-id="e0828-107">Haga clic en **agregar un nuevo valor**.</span><span class="sxs-lookup"><span data-stu-id="e0828-107">Click **Add a New Value**.</span></span> <span data-ttu-id="e0828-108">Escriba la información siguiente y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e0828-108">Enter the following information, and then click **Add**.</span></span>  
  
   1. <span data-ttu-id="e0828-109">**Nombre del nodo:** Compruebe que se trata **MSEXTERNAL**.</span><span class="sxs-lookup"><span data-stu-id="e0828-109">**Node Name:** Verify that this is **MSEXTERNAL**.</span></span>  
  
   2. <span data-ttu-id="e0828-110">**Tipo de transacción:** Compruebe que se trata **asíncrona saliente**.</span><span class="sxs-lookup"><span data-stu-id="e0828-110">**Transaction Type:** Verify that this is **Outbound Asynchronous**.</span></span>  
  
   3. <span data-ttu-id="e0828-111">**Mensaje de solicitud:** escriba `LOCATION_SYNC`.</span><span class="sxs-lookup"><span data-stu-id="e0828-111">**Request Message:** Enter `LOCATION_SYNC`.</span></span>  
  
   4. <span data-ttu-id="e0828-112">**Versión de mensaje de solicitud:** escriba `VERSION_1`.</span><span class="sxs-lookup"><span data-stu-id="e0828-112">**Request Message Version:** Enter `VERSION_1`.</span></span>  
  
      <span data-ttu-id="e0828-113">![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")</span><span class="sxs-lookup"><span data-stu-id="e0828-113">![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")</span></span>  
  
4. <span data-ttu-id="e0828-114">En el **detalles de transacción** , compruebe la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0828-114">On the **Transaction Detail** tab, verify the following settings:</span></span>  
  
   1. <span data-ttu-id="e0828-115">**Estado:** activo.</span><span class="sxs-lookup"><span data-stu-id="e0828-115">**Status:** Active.</span></span>  
  
   2. <span data-ttu-id="e0828-116">**Enrutamiento:** implícita.</span><span class="sxs-lookup"><span data-stu-id="e0828-116">**Routing:** Implicit.</span></span>  
  
      <span data-ttu-id="e0828-117">![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")</span><span class="sxs-lookup"><span data-stu-id="e0828-117">![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")</span></span>  
  
5. <span data-ttu-id="e0828-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e0828-118">Click **Save**.</span></span>  
  
6. <span data-ttu-id="e0828-119">Haga clic en el **volver a la lista de transacciones** vínculo.</span><span class="sxs-lookup"><span data-stu-id="e0828-119">Click the **Return to Transaction List** link.</span></span>  
  
    <span data-ttu-id="e0828-120">La transacción aparecerá en la lista de transacciones.</span><span class="sxs-lookup"><span data-stu-id="e0828-120">The transaction appears in the list of transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0828-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0828-121">See Also</span></span>  
 [<span data-ttu-id="e0828-122">Creación de puertos y hosts HTTP de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="e0828-122">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)