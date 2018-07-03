---
title: Entre la infracción de regla de validación de campos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d606a80-9046-4572-9cfb-a3434ed8073e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d590fc318e7d833a067f4275986bef88da10364
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976661"
---
# <a name="cross-field-validation-rule-violated"></a><span data-ttu-id="30707-102">Infracción de regla de validación de campos cruzados.</span><span class="sxs-lookup"><span data-stu-id="30707-102">Cross field validation rule violated</span></span>
## <a name="details"></a><span data-ttu-id="30707-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="30707-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="30707-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="30707-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="30707-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="30707-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="30707-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="30707-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="30707-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="30707-107">Event Source</span></span>   | <span data-ttu-id="30707-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30707-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="30707-109">Componente</span><span class="sxs-lookup"><span data-stu-id="30707-109">Component</span></span>    |                                       <span data-ttu-id="30707-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="30707-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="30707-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="30707-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="30707-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="30707-112">Message Text</span></span>   |                          <span data-ttu-id="30707-113">Infracción de regla de validación de campos cruzados.</span><span class="sxs-lookup"><span data-stu-id="30707-113">Cross field validation rule violated</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="30707-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="30707-114">Explanation</span></span>  
 <span data-ttu-id="30707-115">Este evento de error,  indica que el intercambio X12 tuvo un error de validación de campo cruzado en la canalización de recepción o de envío.</span><span class="sxs-lookup"><span data-stu-id="30707-115">This Error/Warning/Information event indicates that the X12 interchange failed cross-field validation in the receive pipeline or the send pipeline.</span></span> <span data-ttu-id="30707-116">Esto indica que el indicador X12ConditionDesignator_Check está configurado en "Yes" y que al menos un elemento del intercambio tuvo un error en una regla identificada por el prefijo "X12ConditionDesignatorX".</span><span class="sxs-lookup"><span data-stu-id="30707-116">This indicates that the X12ConditionDesignator_Check flag is set to "Yes", and that at least one element in the interchange failed a rule identified by the prefix "X12ConditionDesignatorX".</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="30707-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="30707-117">User Action</span></span>  
 <span data-ttu-id="30707-118">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="30707-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="30707-119">Identifique qué elemento de datos no ha superado una regla de validación de campo cruzado.</span><span class="sxs-lookup"><span data-stu-id="30707-119">Identify which data element failed a cross-field validation rule.</span></span> <span data-ttu-id="30707-120">Póngase en contacto con el remitente del intercambio e indique que debe seguirse la regla al crear el intercambio.</span><span class="sxs-lookup"><span data-stu-id="30707-120">Contact the sender of the interchange and indicate that the rule must be followed when creating the interchange.</span></span>  
  
-   <span data-ttu-id="30707-121">Abra el esquema para el intercambio y establezca en "No" el indicador X12ConditionDesignator_Check para el elemento de datos que no ha superado la validación.</span><span class="sxs-lookup"><span data-stu-id="30707-121">Open the schema for the interchange, and set the X12ConditionDesignator_Check flag for the data element that failed validation to "No".</span></span>