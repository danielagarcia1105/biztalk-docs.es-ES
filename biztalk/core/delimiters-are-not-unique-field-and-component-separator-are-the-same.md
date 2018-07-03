---
title: Los delimitadores no son únicos, campo y el separador de componentes son los mismos | Microsoft Docs
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
ms.openlocfilehash: fd6439bd307ec922b9dbdd5761f61e9e3ad557f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979421"
---
# <a name="delimiters-are-not-unique-field-and-component-separator-are-the-same"></a><span data-ttu-id="7912d-102">Los delimitadores no son únicos. Los separadores de campo y de componente coinciden.</span><span class="sxs-lookup"><span data-stu-id="7912d-102">Delimiters are not unique, field and component separator are the same</span></span>
## <a name="details"></a><span data-ttu-id="7912d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7912d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7912d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7912d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7912d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7912d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7912d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7912d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7912d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7912d-107">Event Source</span></span>   | <span data-ttu-id="7912d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7912d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="7912d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7912d-109">Component</span></span>    |                                       <span data-ttu-id="7912d-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="7912d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7912d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7912d-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="7912d-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7912d-112">Message Text</span></span>   |         <span data-ttu-id="7912d-113">Los delimitadores no son únicos. Los separadores de campo y de componente coinciden.</span><span class="sxs-lookup"><span data-stu-id="7912d-113">Delimiters are not unique, field and component separator are the same</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="7912d-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="7912d-114">Explanation</span></span>  
 <span data-ttu-id="7912d-115">Este evento de error,  indica que la canalización de envío EDI no pudo procesar un intercambio saliente porque el elemento de datos y los separadores de componentes tenían el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="7912d-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because the data element and component separators were the same value.</span></span> <span data-ttu-id="7912d-116">En un intercambio X12, el separador del elemento de datos es el carácter de la cuarta posición de carácter del segmento ISA y el separador de componente es el carácter del campo ISA16.</span><span class="sxs-lookup"><span data-stu-id="7912d-116">In an X12 interchange, the data element separator is the character in the fourth character position of the ISA segment and the component separator is the character in the ISA16 field.</span></span> <span data-ttu-id="7912d-117">En un intercambio EDIFACT, el separador del elemento de datos es el carácter del campo UNA2 y el separador de componente es el carácter del campo UNA1.</span><span class="sxs-lookup"><span data-stu-id="7912d-117">In an EDIFACT interchange, the data element separator is the character in the UNA2 field and the component separator is the character in the UNA1 field.</span></span> <span data-ttu-id="7912d-118">Dos separadores con el mismo valor pueden tener lugar (pero provocarán una condición de error) en un escenario de lote conservado o si se recibe un intercambio mediante una transmisión de atravesar y posteriormente el puerto de envío lo recoge como archivo XML en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="7912d-118">Two separators with the same value can occur (but will cause an error condition) in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7912d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7912d-119">User Action</span></span>  
 <span data-ttu-id="7912d-120">Para resolver este error, cambie el valor del elemento de datos o de los separadores de componentes y, a continuación, vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="7912d-120">To resolve this error, change the value of either the data element or component separators, and then resubmit the interchange.</span></span>