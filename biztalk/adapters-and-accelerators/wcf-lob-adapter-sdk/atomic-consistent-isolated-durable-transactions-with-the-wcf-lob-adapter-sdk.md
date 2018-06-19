---
title: Configurar las transacciones atómicas, coherentes, aisladas y duraderas con el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20d2613-c77d-4b0d-b2e2-3ed28a8fb36c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58cf80a70b04e20aeb25b27210d88dfd861d7539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224244"
---
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="f5b3e-102">Configurar las transacciones atómicas, coherentes, aisladas y duraderas con el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="f5b3e-102">Configure atomic, consistent, isolated, and durable transactions using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="f5b3e-103">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] admite las transacciones al basarse en la funcionalidad expuesta por el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5b3e-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports transactions by relying on functionality exposed by the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span> <span data-ttu-id="f5b3e-104">Mediante la API expuesta por [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], el adaptador puede admitir las transacciones y las operaciones que son:</span><span class="sxs-lookup"><span data-stu-id="f5b3e-104">By using the API exposed by [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], your adapter can support transactions and operations that are:</span></span>  
  
-   <span data-ttu-id="f5b3e-105">**Atomic**, asegurándose de que todas las actualizaciones pendientes se confirman o ninguno se confirman y se revierte a su estado anterior.</span><span class="sxs-lookup"><span data-stu-id="f5b3e-105">**Atomic**, ensuring that either all pending updates are committed or none are committed and are rolled back to their previous state.</span></span>  
  
-   <span data-ttu-id="f5b3e-106">**Coherente**, asegurarse de que los cambios realizados desde un estado coherente a otro.</span><span class="sxs-lookup"><span data-stu-id="f5b3e-106">**Consistent**, ensuring that changes made are from one consistent state to another.</span></span>  
  
-   <span data-ttu-id="f5b3e-107">**Aislado**, evitar que una transacción para tener acceso a los cambios no confirmados en otras transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="f5b3e-107">**Isolated**, preventing a transaction to access uncommitted changes in other pending transactions.</span></span>  
  
-   <span data-ttu-id="f5b3e-108">**Duradero**, lo que significa que una vez confirmado, las actualizaciones serán persistentes frente a errores.</span><span class="sxs-lookup"><span data-stu-id="f5b3e-108">**Durable**, meaning that once committed, updates will be persistent in the face of failures.</span></span>  
  
 <span data-ttu-id="f5b3e-109">Sistemas de base de datos de los programadores del adaptador de destino relacional u otros sistemas de línea de negocio que admiten transacciones (o esperan) será necesario identificar cómo el sistema de destino es compatible con y expone la compatibilidad con transacciones y, a continuación, identificar un adecuado[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]modelo de transacción que se utilizará.</span><span class="sxs-lookup"><span data-stu-id="f5b3e-109">Adapter developers targeting relational database systems or other line-of-business systems that support (or expect) transactions will need to identify how the target system supports and exposes transaction support and then identify an appropriate [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transaction model to use.</span></span>  
  
 <span data-ttu-id="f5b3e-110">Para obtener más información acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transacciones, vea [información general de las transacciones de Windows Communication Foundation](https://msdn.microsoft.com/library/ms733904.aspx).</span><span class="sxs-lookup"><span data-stu-id="f5b3e-110">For more information about [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transactions, see [Windows Communication Foundation Transactions Overview](https://msdn.microsoft.com/library/ms733904.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f5b3e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5b3e-111">See Also</span></span>  
 [<span data-ttu-id="f5b3e-112">Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="f5b3e-112">Plan and Design your Adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)