---
title: Requerido condicional falta de elemento de datos | Documentos de Microsoft
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
ms.openlocfilehash: 0d77a25e60af0d8287515d6fb3a7e2797d5af0b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231964"
---
# <a name="conditional-required-data-element-missing"></a><span data-ttu-id="a3a1c-102">Falta un elemento de datos requerido condicional.</span><span class="sxs-lookup"><span data-stu-id="a3a1c-102">Conditional required data element missing</span></span>
## <a name="details"></a><span data-ttu-id="a3a1c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a3a1c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3a1c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a3a1c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a3a1c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a3a1c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a3a1c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a3a1c-106">Event ID</span></span>|-|  
|<span data-ttu-id="a3a1c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a3a1c-107">Event Source</span></span>|<span data-ttu-id="a3a1c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3a1c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="a3a1c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a3a1c-109">Component</span></span>|<span data-ttu-id="a3a1c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="a3a1c-110">EDI Engine</span></span>|  
|<span data-ttu-id="a3a1c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a3a1c-111">Symbolic Name</span></span>|<span data-ttu-id="a3a1c-112">X12DeConditionalRequiredDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="a3a1c-112">X12DeConditionalRequiredDataElementMissingDescription</span></span>|  
|<span data-ttu-id="a3a1c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a3a1c-113">Message Text</span></span>|<span data-ttu-id="a3a1c-114">Falta un elemento de datos requerido condicional.</span><span class="sxs-lookup"><span data-stu-id="a3a1c-114">Conditional required data element missing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3a1c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="a3a1c-115">Explanation</span></span>  
 <span data-ttu-id="a3a1c-116">Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio entrante porque no existe en el intercambio un elemento de datos requerido por la regla X12ConditionDesignatorX.</span><span class="sxs-lookup"><span data-stu-id="a3a1c-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because a data element that is required by the X12ConditionDesignatorX rule does not exist in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3a1c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a3a1c-117">User Action</span></span>  
 <span data-ttu-id="a3a1c-118">Este error se debe probablemente a un problema del intercambio entrante y no de la configuración o el funcionamiento de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a3a1c-118">This error is likely an issue with the incoming interchange, not with the configuration or operation of BizTalk Server.</span></span> <span data-ttu-id="a3a1c-119">Para resolver este error, póngase en contacto con el remitente del intercambio e indique que debe cambiar los caracteres usados en él o bien el juego de caracteres identificado en el campo UNB1.1 para que coincidan.</span><span class="sxs-lookup"><span data-stu-id="a3a1c-119">To resolve this error, contact the sender of the interchange and indicate that they need to change either the characters used in the interchange or the character set identified in field UNB1.1 so that they match.</span></span>