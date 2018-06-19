---
title: Los delimitadores no son únicos, campo y el separador de componentes son los mismos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cba15b30-b07d-4caa-8c43-6b4d8c4ca81c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f803612a905f0be196afcfc0b43af23501ccdf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238556"
---
# <a name="delimiters-are-not-unique-field-and-component-separator-are-the-same"></a><span data-ttu-id="9f545-102">Los delimitadores no son únicos. Los separadores de campo y de componente coinciden.</span><span class="sxs-lookup"><span data-stu-id="9f545-102">Delimiters are not unique, field and component separator are the same</span></span>
## <a name="details"></a><span data-ttu-id="9f545-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9f545-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f545-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9f545-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9f545-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9f545-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9f545-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9f545-106">Event ID</span></span>|-|  
|<span data-ttu-id="9f545-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9f545-107">Event Source</span></span>|<span data-ttu-id="9f545-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f545-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="9f545-109">Componente</span><span class="sxs-lookup"><span data-stu-id="9f545-109">Component</span></span>|<span data-ttu-id="9f545-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="9f545-110">EDI Engine</span></span>|  
|<span data-ttu-id="9f545-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9f545-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="9f545-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9f545-112">Message Text</span></span>|<span data-ttu-id="9f545-113">Los delimitadores no son únicos. Los separadores de campo y de componente coinciden.</span><span class="sxs-lookup"><span data-stu-id="9f545-113">Delimiters are not unique, field and component separator are the same</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9f545-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="9f545-114">Explanation</span></span>  
 <span data-ttu-id="9f545-115">Este evento de error,  indica que la canalización de envío EDI no pudo procesar un intercambio saliente porque el elemento de datos y los separadores de componentes tenían el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="9f545-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because the data element and component separators were the same value.</span></span> <span data-ttu-id="9f545-116">En un intercambio X12, el separador del elemento de datos es el carácter de la cuarta posición de carácter del segmento ISA y el separador de componente es el carácter del campo ISA16.</span><span class="sxs-lookup"><span data-stu-id="9f545-116">In an X12 interchange, the data element separator is the character in the fourth character position of the ISA segment and the component separator is the character in the ISA16 field.</span></span> <span data-ttu-id="9f545-117">En un intercambio EDIFACT, el separador del elemento de datos es el carácter del campo UNA2 y el separador de componente es el carácter del campo UNA1.</span><span class="sxs-lookup"><span data-stu-id="9f545-117">In an EDIFACT interchange, the data element separator is the character in the UNA2 field and the component separator is the character in the UNA1 field.</span></span> <span data-ttu-id="9f545-118">Dos separadores con el mismo valor pueden tener lugar (pero provocarán una condición de error) en un escenario de lote conservado o si se recibe un intercambio mediante una transmisión de atravesar y posteriormente el puerto de envío lo recoge como archivo XML en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="9f545-118">Two separators with the same value can occur (but will cause an error condition) in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f545-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9f545-119">User Action</span></span>  
 <span data-ttu-id="9f545-120">Para resolver este error, cambie el valor del elemento de datos o de los separadores de componentes y, a continuación, vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="9f545-120">To resolve this error, change the value of either the data element or component separators, and then resubmit the interchange.</span></span>