---
title: Error al analizar. El X12 grupo funcional del intercambio contenía los errores siguientes | Microsoft Docs
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
ms.openlocfilehash: c4175e4057dca49a3187ebf48e333170e06a1099
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982973"
---
# <a name="error-encountered-during-parsing-the-x12-functional-group-in-the-interchange-had-the-following-errors"></a><span data-ttu-id="fa451-103">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="fa451-103">Error encountered during parsing.</span></span> <span data-ttu-id="fa451-104">El grupo funcional X12 del intercambio contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="fa451-104">The X12 functional group in the interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="fa451-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa451-105">Details</span></span>  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fa451-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fa451-106">Product Name</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| <span data-ttu-id="fa451-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fa451-107">Product Version</span></span> |                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                         |
|    <span data-ttu-id="fa451-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fa451-108">Event ID</span></span>     |                                                                                     -                                                                                     |
|  <span data-ttu-id="fa451-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fa451-109">Event Source</span></span>   |                                          <span data-ttu-id="fa451-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa451-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                           |
|    <span data-ttu-id="fa451-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fa451-111">Component</span></span>    |                                                                                <span data-ttu-id="fa451-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="fa451-112">EDI Engine</span></span>                                                                                 |
|  <span data-ttu-id="fa451-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fa451-113">Symbolic Name</span></span>  |                                                                      <span data-ttu-id="fa451-114">X12FunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="fa451-114">X12FunctionalGroupReceiveError</span></span>                                                                       |
|  <span data-ttu-id="fa451-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fa451-115">Message Text</span></span>   | <span data-ttu-id="fa451-116">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="fa451-116">Error encountered during parsing.</span></span> <span data-ttu-id="fa451-117">El X12 grupo funcional con Id. '{0}', en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa451-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fa451-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="fa451-118">Explanation</span></span>  
 <span data-ttu-id="fa451-119">Este evento de error,  indica que la canalización de recepción EDI ha encontrado un error al analizar un intercambio X12 entrante debido a los errores indicados con el grupo funcional identificado.</span><span class="sxs-lookup"><span data-stu-id="fa451-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa451-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fa451-120">User Action</span></span>  
 <span data-ttu-id="fa451-121">Para resolver este error, use la información del mensaje de error para identificar el error en el grupo y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="fa451-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>