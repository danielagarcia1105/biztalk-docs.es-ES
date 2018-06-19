---
title: Cómo agregar una transacción | Documentos de Microsoft
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
ms.openlocfilehash: 24c67a9c76ae87f2355bb0ea4638d3bd156cda6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246820"
---
# <a name="how-to-add-a-transaction"></a><span data-ttu-id="da64a-102">Cómo agregar una transacción</span><span class="sxs-lookup"><span data-stu-id="da64a-102">How to Add a Transaction</span></span>
<span data-ttu-id="da64a-103">Para agregar una transacción, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="da64a-103">Follow these steps to add a transaction.</span></span>  
  
### <a name="to-add-a-transaction"></a><span data-ttu-id="da64a-104">Para agregar una transacción</span><span class="sxs-lookup"><span data-stu-id="da64a-104">To add a transaction</span></span>  
  
1.  <span data-ttu-id="da64a-105">Haga clic en el **transacciones** ficha.</span><span class="sxs-lookup"><span data-stu-id="da64a-105">Click the **Transactions** tab.</span></span>  
  
2.  <span data-ttu-id="da64a-106">Haga clic en **Agregar transacción**.</span><span class="sxs-lookup"><span data-stu-id="da64a-106">Click **Add Transaction**.</span></span>  
  
3.  <span data-ttu-id="da64a-107">Haga clic en **agregar un nuevo valor**.</span><span class="sxs-lookup"><span data-stu-id="da64a-107">Click **Add a New Value**.</span></span> <span data-ttu-id="da64a-108">Escriba la información siguiente y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="da64a-108">Enter the following information, and then click **Add**.</span></span>  
  
    1.  <span data-ttu-id="da64a-109">**Nombre del nodo:** Compruebe que se trata de **MSEXTERNAL**.</span><span class="sxs-lookup"><span data-stu-id="da64a-109">**Node Name:** Verify that this is **MSEXTERNAL**.</span></span>  
  
    2.  <span data-ttu-id="da64a-110">**Tipo de transacción:** Compruebe que se trata de **asíncrona saliente**.</span><span class="sxs-lookup"><span data-stu-id="da64a-110">**Transaction Type:** Verify that this is **Outbound Asynchronous**.</span></span>  
  
    3.  <span data-ttu-id="da64a-111">**Mensaje de solicitud:** escriba `LOCATION_SYNC`.</span><span class="sxs-lookup"><span data-stu-id="da64a-111">**Request Message:** Enter `LOCATION_SYNC`.</span></span>  
  
    4.  <span data-ttu-id="da64a-112">**Versión de mensaje de solicitud:** escriba `VERSION_1`.</span><span class="sxs-lookup"><span data-stu-id="da64a-112">**Request Message Version:** Enter `VERSION_1`.</span></span>  
  
     ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4.  <span data-ttu-id="da64a-113">En el **detalle de la transacción** ficha, compruebe la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="da64a-113">On the **Transaction Detail** tab, verify the following settings:</span></span>  
  
    1.  <span data-ttu-id="da64a-114">**Estado:** Active.</span><span class="sxs-lookup"><span data-stu-id="da64a-114">**Status:** Active.</span></span>  
  
    2.  <span data-ttu-id="da64a-115">**Enrutamiento:** implícita.</span><span class="sxs-lookup"><span data-stu-id="da64a-115">**Routing:** Implicit.</span></span>  
  
     ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5.  <span data-ttu-id="da64a-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="da64a-116">Click **Save**.</span></span>  
  
6.  <span data-ttu-id="da64a-117">Haga clic en el **volver a la lista de transacciones** vínculo.</span><span class="sxs-lookup"><span data-stu-id="da64a-117">Click the **Return to Transaction List** link.</span></span>  
  
     <span data-ttu-id="da64a-118">La transacción aparecerá en la lista de transacciones.</span><span class="sxs-lookup"><span data-stu-id="da64a-118">The transaction appears in the list of transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da64a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="da64a-119">See Also</span></span>  
 [<span data-ttu-id="da64a-120">Crear un Host de HTTP de PeopleSoft y puerto</span><span class="sxs-lookup"><span data-stu-id="da64a-120">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)