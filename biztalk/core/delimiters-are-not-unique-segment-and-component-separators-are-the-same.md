---
title: Los delimitadores no son únicos, los separadores de segmento y de componente son los mismos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13c41899-02af-4678-a4ad-f3dc48c1fdfb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6068b13502b8893fd5065957b6dd73072236126
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983781"
---
# <a name="delimiters-are-not-unique-segment-and-component-separators-are-the-same"></a><span data-ttu-id="14f34-102">Los delimitadores no son únicos. Los separadores de segmento y de componente coinciden.</span><span class="sxs-lookup"><span data-stu-id="14f34-102">Delimiters are not unique, segment and component separators are the same</span></span>
## <a name="details"></a><span data-ttu-id="14f34-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="14f34-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="14f34-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="14f34-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="14f34-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="14f34-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="14f34-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="14f34-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="14f34-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="14f34-107">Event Source</span></span>   | <span data-ttu-id="14f34-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14f34-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="14f34-109">Componente</span><span class="sxs-lookup"><span data-stu-id="14f34-109">Component</span></span>    |                                       <span data-ttu-id="14f34-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="14f34-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="14f34-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="14f34-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="14f34-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="14f34-112">Message Text</span></span>   |        <span data-ttu-id="14f34-113">Los delimitadores no son únicos. Los separadores de segmento y de componente coinciden.</span><span class="sxs-lookup"><span data-stu-id="14f34-113">Delimiters are not unique, segment and component separators are the same</span></span>        |
  
## <a name="explanation"></a><span data-ttu-id="14f34-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="14f34-114">Explanation</span></span>  
 <span data-ttu-id="14f34-115">Este evento de error,  indica que la canalización de envío EDI no pudo procesar un intercambio saliente porque el terminador de segmento o el separador de componentes eran el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="14f34-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because the segment terminator or the component separator were the same value.</span></span> <span data-ttu-id="14f34-116">En un intercambio X12, el terminador de segmento es el carácter de la última posición de carácter del segmento ISA y el separador de componente es el carácter del campo ISA16.</span><span class="sxs-lookup"><span data-stu-id="14f34-116">In an X12 interchange, the segment terminator is character in the last character position of the ISA segment and the component separator is the character in the ISA16 field.</span></span> <span data-ttu-id="14f34-117">En un intercambio EDIFACT, el terminador de segmento es el carácter del campo UNA6 y el separador de componente es el carácter del campo UNA1.</span><span class="sxs-lookup"><span data-stu-id="14f34-117">In an EDIFACT interchange, the segment terminator is the character in the UNA6 field and the component separator is the character in the UNA1 field.</span></span> <span data-ttu-id="14f34-118">Dos separadores con el mismo valor pueden tener lugar (pero provocarán una condición de error) en un escenario de lote conservado o si se recibe un intercambio mediante una transmisión de atravesar y posteriormente el puerto de envío lo recoge como archivo XML en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="14f34-118">Two separators with the same value can occur (but will cause an error condition) in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14f34-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="14f34-119">User Action</span></span>  
 <span data-ttu-id="14f34-120">Para resolver este error, cambie el valor del terminador de segmento o del separador de componentes en el intercambio y, a continuación, vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="14f34-120">To resolve this error, change the value of either the segment terminator or the component separator in the interchange, and then resubmit the interchange.</span></span>