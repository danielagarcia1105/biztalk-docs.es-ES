---
title: Error durante la serialización. El intercambio de Edifact que no contenía un grupo presentaba los errores siguientes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af693139-e4cd-4bcb-922c-79caa148d3b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72108104b359d4d06233cf9a623097bfd046a0ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241764"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="67219-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="67219-103">Error encountered during serialization.</span></span> <span data-ttu-id="67219-104">El intercambio Edifact que no contenía un grupo presentaba los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="67219-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="67219-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="67219-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67219-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="67219-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="67219-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="67219-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="67219-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="67219-108">Event ID</span></span>|-|  
|<span data-ttu-id="67219-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="67219-109">Event Source</span></span>|<span data-ttu-id="67219-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67219-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="67219-111">Componente</span><span class="sxs-lookup"><span data-stu-id="67219-111">Component</span></span>|<span data-ttu-id="67219-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="67219-112">EDI Engine</span></span>|  
|<span data-ttu-id="67219-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="67219-113">Symbolic Name</span></span>|<span data-ttu-id="67219-114">EfactFunctionalGroupSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="67219-114">EfactFunctionalGroupSendErrorWithoutGroup</span></span>|  
|<span data-ttu-id="67219-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="67219-115">Message Text</span></span>|<span data-ttu-id="67219-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="67219-116">Error encountered during serialization.</span></span> <span data-ttu-id="67219-117">El intercambio de Edifact que no contenía un grupo, con el Id. de intercambio '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="67219-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67219-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="67219-118">Explanation</span></span>  
 <span data-ttu-id="67219-119">Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el intercambio identificado.</span><span class="sxs-lookup"><span data-stu-id="67219-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span> <span data-ttu-id="67219-120">Tenga en cuenta que el intercambio no contiene un grupo.</span><span class="sxs-lookup"><span data-stu-id="67219-120">Note that the interchange does not contain a group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67219-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="67219-121">User Action</span></span>  
 <span data-ttu-id="67219-122">Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="67219-122">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>