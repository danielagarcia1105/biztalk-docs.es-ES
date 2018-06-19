---
title: Error al analizar. El X12 grupo funcional del intercambio contenía los errores siguientes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2229c83-89bd-491f-9504-4afbf0084297
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4e519e8f89f00574ad2b51c1f9884889077c902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239988"
---
# <a name="error-encountered-during-parsing-the-x12-functional-group-in-the-interchange-had-the-following-errors"></a><span data-ttu-id="38c99-103">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="38c99-103">Error encountered during parsing.</span></span> <span data-ttu-id="38c99-104">El grupo funcional X12 del intercambio contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="38c99-104">The X12 functional group in the interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="38c99-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="38c99-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38c99-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="38c99-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="38c99-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="38c99-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="38c99-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="38c99-108">Event ID</span></span>|-|  
|<span data-ttu-id="38c99-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="38c99-109">Event Source</span></span>|<span data-ttu-id="38c99-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38c99-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="38c99-111">Componente</span><span class="sxs-lookup"><span data-stu-id="38c99-111">Component</span></span>|<span data-ttu-id="38c99-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="38c99-112">EDI Engine</span></span>|  
|<span data-ttu-id="38c99-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="38c99-113">Symbolic Name</span></span>|<span data-ttu-id="38c99-114">X12FunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="38c99-114">X12FunctionalGroupReceiveError</span></span>|  
|<span data-ttu-id="38c99-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="38c99-115">Message Text</span></span>|<span data-ttu-id="38c99-116">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="38c99-116">Error encountered during parsing.</span></span> <span data-ttu-id="38c99-117">El X12 funcional de grupo receptor con el identificador '{0}', en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. '{3}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="38c99-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="38c99-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="38c99-118">Explanation</span></span>  
 <span data-ttu-id="38c99-119">Este evento de error,  indica que la canalización de recepción EDI ha encontrado un error al analizar un intercambio X12 entrante debido a los errores indicados con el grupo funcional identificado.</span><span class="sxs-lookup"><span data-stu-id="38c99-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="38c99-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="38c99-120">User Action</span></span>  
 <span data-ttu-id="38c99-121">Para resolver este error, use la información del mensaje de error para identificar el error en el grupo y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="38c99-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>