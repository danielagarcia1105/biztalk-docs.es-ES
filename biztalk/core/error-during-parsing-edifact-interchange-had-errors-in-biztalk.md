---
title: Error al analizar. El intercambio Edifact contenía los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fa8f9d5-5b7c-47c9-96d3-77be280b78e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d891abe7ca75dbbe9052f221970e235b390269
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988213"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="8812f-103">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="8812f-103">Error encountered during parsing.</span></span> <span data-ttu-id="8812f-104">El intercambio Edifact contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="8812f-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="8812f-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="8812f-105">Details</span></span>  
  
|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8812f-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8812f-106">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| <span data-ttu-id="8812f-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8812f-107">Product Version</span></span> |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                         |
|    <span data-ttu-id="8812f-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8812f-108">Event ID</span></span>     |                                                                     -                                                                      |
|  <span data-ttu-id="8812f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8812f-109">Event Source</span></span>   |                           <span data-ttu-id="8812f-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8812f-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                           |
|    <span data-ttu-id="8812f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8812f-111">Component</span></span>    |                                                                 <span data-ttu-id="8812f-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="8812f-112">EDI Engine</span></span>                                                                 |
|  <span data-ttu-id="8812f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8812f-113">Symbolic Name</span></span>  |                                                        <span data-ttu-id="8812f-114">EfactInterchangeReceiveError</span><span class="sxs-lookup"><span data-stu-id="8812f-114">EfactInterchangeReceiveError</span></span>                                                        |
|  <span data-ttu-id="8812f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8812f-115">Message Text</span></span>   | <span data-ttu-id="8812f-116">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="8812f-116">Error encountered during parsing.</span></span> <span data-ttu-id="8812f-117">El intercambio Edifact con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="8812f-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8812f-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="8812f-118">Explanation</span></span>  
 <span data-ttu-id="8812f-119">Este evento de error,  indica que la canalización de recepción EDI encontró un error al analizar un intercambio EDIFACT entrante debido a los errores indicados en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="8812f-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8812f-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8812f-120">User Action</span></span>  
 <span data-ttu-id="8812f-121">Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="8812f-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>