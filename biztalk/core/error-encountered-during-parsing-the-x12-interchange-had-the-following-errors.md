---
title: "Error al analizar. El X12 intercambio contenía los errores siguientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c1085d4-75ef-4f63-84c9-287a4a61274a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94b9907667a7f99c1ecf8c2dc326fe32e134abf3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-x12-interchange-had-the-following-errors"></a><span data-ttu-id="b0b60-103">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="b0b60-103">Error encountered during parsing.</span></span> <span data-ttu-id="b0b60-104">El intercambio X12 contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="b0b60-104">The X12 interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="b0b60-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="b0b60-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b0b60-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b0b60-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b0b60-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b0b60-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b0b60-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b0b60-108">Event ID</span></span>|-|  
|<span data-ttu-id="b0b60-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b0b60-109">Event Source</span></span>|<span data-ttu-id="b0b60-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0b60-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="b0b60-111">Componente</span><span class="sxs-lookup"><span data-stu-id="b0b60-111">Component</span></span>|<span data-ttu-id="b0b60-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="b0b60-112">EDI Engine</span></span>|  
|<span data-ttu-id="b0b60-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b0b60-113">Symbolic Name</span></span>|<span data-ttu-id="b0b60-114">X12InterchangeReceiveError</span><span class="sxs-lookup"><span data-stu-id="b0b60-114">X12InterchangeReceiveError</span></span>|  
|<span data-ttu-id="b0b60-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b0b60-115">Message Text</span></span>|<span data-ttu-id="b0b60-116">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="b0b60-116">Error encountered during parsing.</span></span> <span data-ttu-id="b0b60-117">El X12 intercambio con Id. '{0}' con el remitente Id. '{1}', Id. de destinatario '{2}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0b60-117">The X12 interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b0b60-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="b0b60-118">Explanation</span></span>  
 <span data-ttu-id="b0b60-119">Este evento de error,  indica que la canalización de recepción EDI encontró un error al analizar un intercambio X12 entrante debido a los errores indicados en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="b0b60-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b0b60-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b0b60-120">User Action</span></span>  
 <span data-ttu-id="b0b60-121">Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="b0b60-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>