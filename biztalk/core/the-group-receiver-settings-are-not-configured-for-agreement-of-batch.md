---
title: La configuración del receptor de grupo no está configurada para el acuerdo del lote | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57b205e9-aaab-43d1-b373-17d206957814
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ea41ad5c8de88e446a86745b57ff282d5b90af5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279076"
---
# <a name="the-group-receiver-settings-are-not-configured-for-agreement-of-batch"></a><span data-ttu-id="3e864-102">La configuración de receptor de grupo no está configurada para el acuerdo del lote</span><span class="sxs-lookup"><span data-stu-id="3e864-102">The group receiver settings are not configured for agreement of batch</span></span>
## <a name="details"></a><span data-ttu-id="3e864-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3e864-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e864-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3e864-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3e864-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3e864-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3e864-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3e864-106">Event ID</span></span>|-|  
|<span data-ttu-id="3e864-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3e864-107">Event Source</span></span>|<span data-ttu-id="3e864-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e864-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="3e864-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3e864-109">Component</span></span>|<span data-ttu-id="3e864-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="3e864-110">Batching Engine</span></span>|  
|<span data-ttu-id="3e864-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3e864-111">Symbolic Name</span></span>|<span data-ttu-id="3e864-112">GroupReceiverNotSelected</span><span class="sxs-lookup"><span data-stu-id="3e864-112">GroupReceiverNotSelected</span></span>|  
|<span data-ttu-id="3e864-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3e864-113">Message Text</span></span>|<span data-ttu-id="3e864-114">Los valores de destinatario de grupo no se han configurado para el acuerdo del lote {0}.</span><span class="sxs-lookup"><span data-stu-id="3e864-114">The group receiver settings are not configured for agreement of batch {0}.</span></span> <span data-ttu-id="3e864-115">Debe configurarlos antes de que el procesamiento por lotes pueda continuar.</span><span class="sxs-lookup"><span data-stu-id="3e864-115">This needs to be configured before batching can proceed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3e864-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="3e864-116">Explanation</span></span>  
 <span data-ttu-id="3e864-117">Este evento de error,  indica que ha tenido lugar una de estas dos condiciones:</span><span class="sxs-lookup"><span data-stu-id="3e864-117">This Error/Warning/Information event indicates that one of two conditions has occurred:</span></span>  
  
-   <span data-ttu-id="3e864-118">La orquestación por lotes no pudo validar un elemento de lote que ha recibido porque no se ha configurado el campo UNB1.1 (para un intercambio con la codificación EDIFACT) que contiene la sintaxis de codificación.</span><span class="sxs-lookup"><span data-stu-id="3e864-118">The batching orchestration could not validate a batch element that it has received because the UNB1.1 field (for an EDIFACT-encoded interchange) that contains the encoding syntax was not set.</span></span>  
  
-   <span data-ttu-id="3e864-119">La orquestación de lote no pudo crear la configuración de sobre para el elemento de lote porque las propiedades del encabezado no estaban completas (propiedades ISA, GS y ST para un intercambio X12 o propiedades UNA, UNB, UNG y UNH para un intercambio EDIFACT).</span><span class="sxs-lookup"><span data-stu-id="3e864-119">The batching orchestration could not create the envelope settings for the batch element because the header properties were not complete (ISA, GS, and ST properties for an X12 interchange or UNA, UNB, UNG, and UNH properties for an EDIFACT interchange).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e864-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3e864-120">User Action</span></span>  
 <span data-ttu-id="3e864-121">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3e864-121">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="3e864-122">Si la orquestación por lotes no pudo validar un elemento de lote recibido porque la sintaxis de codificación no estaba configurada, configúrela para el campo UNB1.1 de la página Definición de segmento UNB del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="3e864-122">If the batching orchestration could not validate a batch element that it has received because the encoding syntax was not set, set the encoding syntax for the UNB1.1 field in the UNB Segment Definition page of the EDI Properties dialog box.</span></span>  
  
-   <span data-ttu-id="3e864-123">Si la orquestación de lote no pudo crear la configuración de sobre para el elemento de lote porque las propiedades del encabezado no estaban completas, asegúrese de que estén configuradas las propiedades ISA, GS y ST para un intercambio X12 o las propiedades UNA, UNB, UNG y UNH para un intercambio EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="3e864-123">If the batching orchestration could not create the envelope settings for the batch element because the header properties were not complete, ensure that the ISA, GS, and ST properties for an X12 interchange are set or that the UNA, UNB, UNG, and UNH properties for an EDIFACT interchange are set.</span></span>