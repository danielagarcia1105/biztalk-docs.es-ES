---
title: Identificador de conjunto de transacciones falta o no válido o duplicado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8580aab2-9fa4-43fb-b643-10621926591e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75251d0210be4ed34a74ba0f3f5cadf84d9941b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263508"
---
# <a name="missing-or-invalid-or-duplicate-transaction-set-identifier"></a><span data-ttu-id="2cf0b-102">El identificador de conjunto de transacciones falta, no es válido o está duplicado</span><span class="sxs-lookup"><span data-stu-id="2cf0b-102">Missing or invalid or duplicate Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="2cf0b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2cf0b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2cf0b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2cf0b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2cf0b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2cf0b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2cf0b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2cf0b-106">Event ID</span></span>|-|  
|<span data-ttu-id="2cf0b-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2cf0b-107">Event Source</span></span>|<span data-ttu-id="2cf0b-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf0b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="2cf0b-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2cf0b-109">Component</span></span>|<span data-ttu-id="2cf0b-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="2cf0b-110">EDI Engine</span></span>|  
|<span data-ttu-id="2cf0b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2cf0b-111">Symbolic Name</span></span>|<span data-ttu-id="2cf0b-112">X12TsMissingOrInvalidTsIdentiferDescription2</span><span class="sxs-lookup"><span data-stu-id="2cf0b-112">X12TsMissingOrInvalidTsIdentiferDescription2</span></span>|  
|<span data-ttu-id="2cf0b-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2cf0b-113">Message Text</span></span>|<span data-ttu-id="2cf0b-114">El identificador de conjunto de transacciones '{0}' falta, no es válido o está duplicado.</span><span class="sxs-lookup"><span data-stu-id="2cf0b-114">Missing or invalid or duplicate Transaction set identifier '{0}'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2cf0b-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="2cf0b-115">Explanation</span></span>  
 <span data-ttu-id="2cf0b-116">Este evento de error,  indica que la canalización de recepción o de envío no pudo procesar el intercambio X12 porque el valor del identificador del conjunto de transacciones (en el campo ST01) faltaba, estaba duplicado o contenía un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="2cf0b-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the X12 interchange because the value of the transaction set identifier (in the ST01 field) was missing, a duplicate, or had an invalid value.</span></span> <span data-ttu-id="2cf0b-117">Esto puede producirse si el esquema del documento no tiene un encabezado ST y un finalizador SE.</span><span class="sxs-lookup"><span data-stu-id="2cf0b-117">This can occur if the document schema does not have an ST header and an SE trailer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2cf0b-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2cf0b-118">User Action</span></span>  
 <span data-ttu-id="2cf0b-119">Para resolver este error, asegúrese de que el intercambio tenga un valor para el campo ST01 y que el esquema tenga una entrada para el encabezado ST y el finalizador SE.</span><span class="sxs-lookup"><span data-stu-id="2cf0b-119">To resolve this error, make sure that the interchange has a value for the ST01 field and that the schema has an entry for the ST header and SE trailer.</span></span> <span data-ttu-id="2cf0b-120">Compruebe que el valor de ST01 es un designador de tipo de documento válido de tres dígitos.</span><span class="sxs-lookup"><span data-stu-id="2cf0b-120">Verify that the value of ST01 is a valid three-digit document-type designator.</span></span> <span data-ttu-id="2cf0b-121">Compruebe que el campo ST01 no sea un duplicado del campo ST01 de otro conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="2cf0b-121">Verify that the ST01 field is not a duplicate with the ST01 field of another transaction set.</span></span>