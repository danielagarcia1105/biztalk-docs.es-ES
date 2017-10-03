---
title: Procesamiento por lotes entrantes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98f47903-933a-4bde-b320-f7689c3d8366
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3781d9b7c1ed2190a8334f272c04d304669ace
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="processing-incoming-batches"></a><span data-ttu-id="0ef0f-102">Procesar lotes entrantes</span><span class="sxs-lookup"><span data-stu-id="0ef0f-102">Processing Incoming Batches</span></span>
<span data-ttu-id="0ef0f-103">Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un intercambio EDI de procesamiento por lotes, puede dividir el intercambio en conjuntos de transacciones, procesando cada una de forma independiente, o bien puede conservar el intercambio procesando los conjuntos de transacciones como grupo.</span><span class="sxs-lookup"><span data-stu-id="0ef0f-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a batched EDI interchange, it can either split the interchange into its transaction sets, processing each one separately, or it can preserve the interchange, processing all transaction sets as a group.</span></span>  
  
 <span data-ttu-id="0ef0f-104">Determinar el procesamiento por lotes en el **configuración de Host Local** página de las fichas de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo para acuerdos x X12 y EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="0ef0f-104">You determine batch processing in the **Local Host Settings** page of the one-way agreement tabs in the **Agreement Properties** dialog box for both X12 and EDIFACT agreements.</span></span> <span data-ttu-id="0ef0f-105">Si conserva el intercambio, tiene la opción de suspender el intercambio o los conjuntos de transacciones si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="0ef0f-105">When you preserve the interchange, you have the choice to suspend either the interchange or the transaction sets if an error occurs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ef0f-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0ef0f-106">In This Section</span></span>  
  
-   [<span data-ttu-id="0ef0f-107">Dividir un intercambio EDI por lotes</span><span class="sxs-lookup"><span data-stu-id="0ef0f-107">Splitting a Batched EDI Interchange</span></span>](../core/splitting-a-batched-edi-interchange.md)  
  
-   [<span data-ttu-id="0ef0f-108">Dividir subdocumentos HIPAA</span><span class="sxs-lookup"><span data-stu-id="0ef0f-108">Splitting HIPAA Subdocuments</span></span>](../core/splitting-hipaa-subdocuments.md)  
  
-   [<span data-ttu-id="0ef0f-109">Conservar un recibido el intercambio EDI por lotes</span><span class="sxs-lookup"><span data-stu-id="0ef0f-109">Preserving a Received Batched EDI Interchange</span></span>](../core/preserving-a-received-batched-edi-interchange.md)