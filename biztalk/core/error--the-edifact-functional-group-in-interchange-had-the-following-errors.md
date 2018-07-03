---
title: Error al analizar. El grupo funcional Edifact del intercambio contenía los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77ca78b3-8a1f-4da5-9c15-524ab6802457
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5be4d7270aeac605c1e476db4089ea3089296bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004501"
---
# <a name="error-encountered-during-parsing-the-edifact-functional-group-in-interchange-had-the-following-errors"></a><span data-ttu-id="ffbf8-103">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="ffbf8-103">Error encountered during parsing.</span></span> <span data-ttu-id="ffbf8-104">El grupo funcional Edifact del intercambio contenía los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="ffbf8-104">The Edifact functional group in interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="ffbf8-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="ffbf8-105">Details</span></span>  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ffbf8-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ffbf8-106">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="ffbf8-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ffbf8-107">Product Version</span></span> |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="ffbf8-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ffbf8-108">Event ID</span></span>     |                                                                                       -                                                                                       |
|  <span data-ttu-id="ffbf8-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ffbf8-109">Event Source</span></span>   |                                            <span data-ttu-id="ffbf8-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffbf8-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                             |
|    <span data-ttu-id="ffbf8-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ffbf8-111">Component</span></span>    |                                                                                  <span data-ttu-id="ffbf8-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ffbf8-112">EDI Engine</span></span>                                                                                   |
|  <span data-ttu-id="ffbf8-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ffbf8-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="ffbf8-114">EfactFunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="ffbf8-114">EfactFunctionalGroupReceiveError</span></span>                                                                        |
|  <span data-ttu-id="ffbf8-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ffbf8-115">Message Text</span></span>   | <span data-ttu-id="ffbf8-116">Error al analizar.</span><span class="sxs-lookup"><span data-stu-id="ffbf8-116">Error encountered during parsing.</span></span> <span data-ttu-id="ffbf8-117">El grupo funcional Edifact con Id. '{0}', en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ffbf8-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ffbf8-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="ffbf8-118">Explanation</span></span>  
 <span data-ttu-id="ffbf8-119">Este evento de error,  indica que la canalización de recepción EDI ha encontrado un error al analizar un intercambio EDIFACT entrante debido a los errores indicados con el grupo funcional identificado.</span><span class="sxs-lookup"><span data-stu-id="ffbf8-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ffbf8-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ffbf8-120">User Action</span></span>  
 <span data-ttu-id="ffbf8-121">Para resolver este error, use la información del mensaje de error para identificar el error en el grupo y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="ffbf8-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>