---
title: Error al leer los delimitadores de los datos ISA | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cb60abd-53c8-45e1-a840-d27dc974aad7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fcde2519740adc5531363911146164f460f9b3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-in-reading-delimiters-from-isa-data"></a><span data-ttu-id="ca1bc-102">Error al leer los delimitadores de los datos ISA.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-102">Error encountered in reading delimiters from ISA data</span></span>
## <a name="details"></a><span data-ttu-id="ca1bc-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ca1bc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca1bc-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ca1bc-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ca1bc-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ca1bc-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ca1bc-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ca1bc-106">Event ID</span></span>|-|  
|<span data-ttu-id="ca1bc-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ca1bc-107">Event Source</span></span>|<span data-ttu-id="ca1bc-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca1bc-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="ca1bc-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ca1bc-109">Component</span></span>|<span data-ttu-id="ca1bc-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ca1bc-110">EDI Engine</span></span>|  
|<span data-ttu-id="ca1bc-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ca1bc-111">Symbolic Name</span></span>|<span data-ttu-id="ca1bc-112">InvalidIsaData</span><span class="sxs-lookup"><span data-stu-id="ca1bc-112">InvalidIsaData</span></span>|  
|<span data-ttu-id="ca1bc-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ca1bc-113">Message Text</span></span>|<span data-ttu-id="ca1bc-114">Error al leer los delimitadores de los datos ISA.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-114">Error encountered in reading delimiters from ISA data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ca1bc-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="ca1bc-115">Explanation</span></span>  
 <span data-ttu-id="ca1bc-116">Este evento de error,  indica que la canalización de recepción EDI encontró un error al procesar un intercambio X12 entrante porque no pudo analizar los separadores del segmento ISA.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-116">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when processing an incoming X12 interchange because it could not parse the separators from the ISA segment.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ca1bc-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ca1bc-117">User Action</span></span>  
 <span data-ttu-id="ca1bc-118">Para resolver este error, compruebe que los separadores del segmento ISA del intercambio entrante son únicos y válidos.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-118">To resolve this error, verify that the separators in the ISA segment of the incoming interchange are unique and valid.</span></span> <span data-ttu-id="ca1bc-119">Si no es así, pida al remitente del intercambio que especifique valores únicos y válidos en cada uno de los campos separadores (el segmento ISA11 para el separador de repetición y el segmento ISA16 para el separador de componente) y reenvíe el intercambio.</span><span class="sxs-lookup"><span data-stu-id="ca1bc-119">If not, have the sender of the interchange enter unique and valid values into each of the separator fields (the ISA11 segment for the repetition separator and the ISA16 segment for the component separator), and then resend the interchange.</span></span>