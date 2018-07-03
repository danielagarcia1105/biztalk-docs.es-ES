---
title: Pestaña de la definición de batch | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchdefinition
helpviewer_keywords:
- Batch Definition tab [Configuration Explorer]
- batching, configuring
- configuring, batching
ms.assetid: fe8685ef-5de5-4337-8691-8e4094056ace
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8eb06321fc5025efa17796a79cddcbe2d14ef9e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970821"
---
# <a name="batch-definition-tab"></a><span data-ttu-id="cfd7b-102">Pestaña definición de lote</span><span class="sxs-lookup"><span data-stu-id="cfd7b-102">Batch Definition Tab</span></span>
<span data-ttu-id="cfd7b-103">Usa el **definición de lote** tab para habilitar la entrada por lotes de procesamiento por lotes, en o salida de procesamiento por lotes y seleccione los esquemas disponibles para el procesamiento por lotes saliente.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-103">You use the **Batch Definition** tab to enable inbound batching, batch in/batch out batching, and select available schemas for outbound batching.</span></span>  

 <span data-ttu-id="cfd7b-104">En el **Explorador de configuración de BTAHL7** cuadro de diálogo el **definición de lote** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfd7b-104">In the **BTAHL7 Configuration Explorer** dialog box, on the **Batch Definition** tab, do the following:</span></span>  


|                   <span data-ttu-id="cfd7b-105">Use</span><span class="sxs-lookup"><span data-stu-id="cfd7b-105">Use this</span></span>                   |                                                                                                                                                            <span data-ttu-id="cfd7b-106">Para</span><span class="sxs-lookup"><span data-stu-id="cfd7b-106">To do this</span></span>                                                                                                                                                            |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          <span data-ttu-id="cfd7b-107">**Fragmentación necesaria**</span><span class="sxs-lookup"><span data-stu-id="cfd7b-107">**Fragmentation required**</span></span>          |                                                           <span data-ttu-id="cfd7b-108">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="cfd7b-108">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="cfd7b-109">-   **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-109">-   **Yes**.</span></span> <span data-ttu-id="cfd7b-110">Para habilitar la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-110">To enable fragmentation.</span></span><br /><span data-ttu-id="cfd7b-111">-   **No**.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-111">-   **No**.</span></span> <span data-ttu-id="cfd7b-112">Para deshabilitar la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-112">To disable fragmentation.</span></span> <span data-ttu-id="cfd7b-113">**Nota:** para una entidad nueva, **requerida fragmentación** el valor predeterminado es **No**.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-113">**Note:**  For a new party, **Fragmentation Required** defaults to **No**.</span></span>                                                           |
| <span data-ttu-id="cfd7b-114">**Soporte técnico de intercambio recuperable requerido**</span><span class="sxs-lookup"><span data-stu-id="cfd7b-114">**Recoverable interchange support required**</span></span> | <span data-ttu-id="cfd7b-115">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="cfd7b-115">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="cfd7b-116">-   **True**.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-116">-   **True**.</span></span> <span data-ttu-id="cfd7b-117">Para habilitar la compatibilidad de intercambio recuperable.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-117">To enable recoverable interchange support.</span></span><br /><span data-ttu-id="cfd7b-118">-   **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-118">-   **FALSE**.</span></span> <span data-ttu-id="cfd7b-119">Para deshabilitar la compatibilidad de intercambio recuperable.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-119">To disable recoverable interchange support.</span></span> <span data-ttu-id="cfd7b-120">**Nota:** para una entidad nueva, **requerida fragmentación** el valor predeterminado es **FALSE** y solo se habilita si el valor de **requerida fragmentación** es **No**.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-120">**Note:**  For a new party, **Fragmentation Required** defaults to **FALSE** and is enabled only if the value of **Fragmentation Required** is **No**.</span></span> |
|             <span data-ttu-id="cfd7b-121">**Seleccionar los mensajes**</span><span class="sxs-lookup"><span data-stu-id="cfd7b-121">**Select Messages**</span></span>              |                              <span data-ttu-id="cfd7b-122">Seleccione los tipos de mensaje que desea enviar como un lote desde la ventana de mensajes disponibles y, a continuación, haga clic en la migración a la flecha derecha (**>>**).</span><span class="sxs-lookup"><span data-stu-id="cfd7b-122">Select the message types you want to send as a batch from the Available Messages window and then click the Move to right arrow (**>>**).</span></span><br /><br /> <span data-ttu-id="cfd7b-123">Para procesar por lotes los mensajes de confirmación entrantes, debe agregar el tipo de mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-123">To batch incoming ACK messages, you must add the ACK message type.</span></span> <span data-ttu-id="cfd7b-124">Hacerlo mediante la implementación del esquema de mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="cfd7b-124">You do so by deploying the ACK message schema.</span></span>                              |
|      <span data-ttu-id="cfd7b-125">**Seleccione las confirmaciones de mensajes**</span><span class="sxs-lookup"><span data-stu-id="cfd7b-125">**Select Message Acknowledgments**</span></span>      |                               <span data-ttu-id="cfd7b-126">Seleccione los tipos de mensaje que desea [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] para enviar las confirmaciones como un lote desde la ventana de mensajes de confirmación de mensaje disponibles y, a continuación, haga clic en la migración a la flecha derecha (**>>**).</span><span class="sxs-lookup"><span data-stu-id="cfd7b-126">Select the message types for which you want [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] to send the acknowledgments as a batch from the Available Message Acks window, and then click the Move to right arrow (**>>**).</span></span>                                |

