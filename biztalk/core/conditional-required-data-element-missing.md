---
title: Falta un elemento de datos requerido condicional | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5105c03-fa26-4c38-a276-c656f3076d5f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f43ebf2ba593ad5133b93400bf0e9cb1151dc45b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978445"
---
# <a name="conditional-required-data-element-missing"></a><span data-ttu-id="4e858-102">Falta un elemento de datos requerido condicional.</span><span class="sxs-lookup"><span data-stu-id="4e858-102">Conditional required data element missing</span></span>
## <a name="details"></a><span data-ttu-id="4e858-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4e858-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="4e858-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4e858-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="4e858-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4e858-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="4e858-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4e858-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="4e858-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4e858-107">Event Source</span></span>   | <span data-ttu-id="4e858-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e858-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="4e858-109">Componente</span><span class="sxs-lookup"><span data-stu-id="4e858-109">Component</span></span>    |                                       <span data-ttu-id="4e858-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="4e858-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="4e858-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4e858-111">Symbolic Name</span></span>  |                 <span data-ttu-id="4e858-112">X12DeConditionalRequiredDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="4e858-112">X12DeConditionalRequiredDataElementMissingDescription</span></span>                  |
|  <span data-ttu-id="4e858-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4e858-113">Message Text</span></span>   |                       <span data-ttu-id="4e858-114">Falta un elemento de datos requerido condicional.</span><span class="sxs-lookup"><span data-stu-id="4e858-114">Conditional required data element missing</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="4e858-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="4e858-115">Explanation</span></span>  
 <span data-ttu-id="4e858-116">Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio entrante porque no existe en el intercambio un elemento de datos requerido por la regla X12ConditionDesignatorX.</span><span class="sxs-lookup"><span data-stu-id="4e858-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because a data element that is required by the X12ConditionDesignatorX rule does not exist in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4e858-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4e858-117">User Action</span></span>  
 <span data-ttu-id="4e858-118">Este error se debe probablemente a un problema del intercambio entrante y no de la configuración o el funcionamiento de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4e858-118">This error is likely an issue with the incoming interchange, not with the configuration or operation of BizTalk Server.</span></span> <span data-ttu-id="4e858-119">Para resolver este error, póngase en contacto con el remitente del intercambio e indique que debe cambiar los caracteres usados en él o bien el juego de caracteres identificado en el campo UNB1.1 para que coincidan.</span><span class="sxs-lookup"><span data-stu-id="4e858-119">To resolve this error, contact the sender of the interchange and indicate that they need to change either the characters used in the interchange or the character set identified in field UNB1.1 so that they match.</span></span>