---
title: Separador de elementos de datos no válidos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c50a8b-274f-4f4a-9826-4f6f8123e9d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d83b8ce3099ebb940507d391881cfd92cde5034d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257468"
---
# <a name="invalid-data-element-separator"></a><span data-ttu-id="d756c-102">Separador de elemento de datos no válido.</span><span class="sxs-lookup"><span data-stu-id="d756c-102">Invalid Data Element Separator</span></span>
## <a name="details"></a><span data-ttu-id="d756c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d756c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d756c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d756c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d756c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d756c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d756c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d756c-106">Event ID</span></span>|-|  
|<span data-ttu-id="d756c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d756c-107">Event Source</span></span>|<span data-ttu-id="d756c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d756c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="d756c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="d756c-109">Component</span></span>|<span data-ttu-id="d756c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="d756c-110">EDI Engine</span></span>|  
|<span data-ttu-id="d756c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d756c-111">Symbolic Name</span></span>|<span data-ttu-id="d756c-112">X12Ta1InvalidDataElementSeparatorDescription</span><span class="sxs-lookup"><span data-stu-id="d756c-112">X12Ta1InvalidDataElementSeparatorDescription</span></span>|  
|<span data-ttu-id="d756c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d756c-113">Message Text</span></span>|<span data-ttu-id="d756c-114">Separador de elemento de datos no válido.</span><span class="sxs-lookup"><span data-stu-id="d756c-114">Invalid Data Element Separator</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d756c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="d756c-115">Explanation</span></span>  
 <span data-ttu-id="d756c-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del terminador de segmento del intercambio no estaba limitado a los caracteres del juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="d756c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the segment terminator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="d756c-117">En X12, el terminador de segmento se define como el cuarto carácter del segmento ISA.</span><span class="sxs-lookup"><span data-stu-id="d756c-117">In X12, the segment terminator is defined as the fourth character in the ISA segment.</span></span> <span data-ttu-id="d756c-118">En EDIFACT, el terminador de segmento es el campo UNA2.</span><span class="sxs-lookup"><span data-stu-id="d756c-118">In EDIFACT, the segment terminator is the UNA2 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d756c-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d756c-119">User Action</span></span>  
 <span data-ttu-id="d756c-120">Para resolver este error, asegúrese de que el terminador de segmento (el cuarto carácter del segmento ISA de un intercambio X12 o el campo UNA2 en un intercambio EDIFACT) está limitado a los caracteres del conjunto de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="d756c-120">To resolve this error, make sure that the segment terminator (the fourth character of the ISA segment in an X12 interchange or the UNA2 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="d756c-121">Vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="d756c-121">Have the interchange resent.</span></span>