---
title: Error durante la serialización. El intercambio de Edifact que no contenía un grupo presentaba los errores siguientes | Microsoft Docs
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
ms.openlocfilehash: f06625ad9689349b0aa47453c5aa2cc50cf9d807
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988301"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="ea6de-103">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="ea6de-103">Error encountered during serialization.</span></span> <span data-ttu-id="ea6de-104">El intercambio Edifact que no contenía un grupo presentaba los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="ea6de-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="ea6de-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="ea6de-105">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ea6de-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ea6de-106">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="ea6de-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ea6de-107">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="ea6de-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ea6de-108">Event ID</span></span>     |                                                                                              -                                                                                              |
|  <span data-ttu-id="ea6de-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ea6de-109">Event Source</span></span>   |                                                   <span data-ttu-id="ea6de-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea6de-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                    |
|    <span data-ttu-id="ea6de-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ea6de-111">Component</span></span>    |                                                                                         <span data-ttu-id="ea6de-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ea6de-112">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="ea6de-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ea6de-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="ea6de-114">EfactFunctionalGroupSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="ea6de-114">EfactFunctionalGroupSendErrorWithoutGroup</span></span>                                                                          |
|  <span data-ttu-id="ea6de-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ea6de-115">Message Text</span></span>   | <span data-ttu-id="ea6de-116">Error durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="ea6de-116">Error encountered during serialization.</span></span> <span data-ttu-id="ea6de-117">El intercambio Edifact que no contenía un grupo con el Id. de intercambio '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ea6de-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ea6de-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="ea6de-118">Explanation</span></span>  
 <span data-ttu-id="ea6de-119">Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el intercambio identificado.</span><span class="sxs-lookup"><span data-stu-id="ea6de-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span> <span data-ttu-id="ea6de-120">Tenga en cuenta que el intercambio no contiene un grupo.</span><span class="sxs-lookup"><span data-stu-id="ea6de-120">Note that the interchange does not contain a group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ea6de-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ea6de-121">User Action</span></span>  
 <span data-ttu-id="ea6de-122">Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.</span><span class="sxs-lookup"><span data-stu-id="ea6de-122">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>