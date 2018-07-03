---
title: Se encontró un elemento de fin al buscar el elemento de inicio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e200f4ffd8d822a5c2bb1a0bad74a60e84a408a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992437"
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a><span data-ttu-id="0f340-102">Se encontró un elemento de fin al buscar un elemento de inicio</span><span class="sxs-lookup"><span data-stu-id="0f340-102">An End Element was found while looking for Start Element</span></span>
## <a name="details"></a><span data-ttu-id="0f340-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0f340-103">Details</span></span>  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0f340-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0f340-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| <span data-ttu-id="0f340-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0f340-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    <span data-ttu-id="0f340-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0f340-106">Event ID</span></span>     |                                                 -                                                 |
|  <span data-ttu-id="0f340-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0f340-107">Event Source</span></span>   |      <span data-ttu-id="0f340-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f340-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>       |
|    <span data-ttu-id="0f340-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0f340-109">Component</span></span>    |                                            <span data-ttu-id="0f340-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="0f340-110">EDI Engine</span></span>                                             |
|  <span data-ttu-id="0f340-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0f340-111">Symbolic Name</span></span>  |                             <span data-ttu-id="0f340-112">EndElementFoundWhenLookingForStartElement</span><span class="sxs-lookup"><span data-stu-id="0f340-112">EndElementFoundWhenLookingForStartElement</span></span>                             |
|  <span data-ttu-id="0f340-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0f340-113">Message Text</span></span>   | <span data-ttu-id="0f340-114">Un elemento EndElement con nombre {0} se encontró al buscar el elemento StartElement con nombre {1}, en profundidad {2}</span><span class="sxs-lookup"><span data-stu-id="0f340-114">An EndElement with name {0} was found, while looking for StartElement with name {1}, at depth {2}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0f340-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="0f340-115">Explanation</span></span>  
 <span data-ttu-id="0f340-116">Este evento de error, advertencia o información indica que BizTalk Server no pudo procesar el mensaje XML entrante (después de analizar) o un mensaje XML saliente (antes de la serialización) debido a que no se pudo validar el mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="0f340-116">This Error/Warning/Information event indicates that BizTalk Server could not process an incoming XML message (after parsing) or an outgoing XML message (before serialization) because the XML message failed validation.</span></span> <span data-ttu-id="0f340-117">El mensaje XML no contenía una etiqueta de finalización para un encabezado o elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="0f340-117">The XML message did not contain an end tag for a header or data element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0f340-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0f340-118">User Action</span></span>  
 <span data-ttu-id="0f340-119">Para resolver este error, agregue la etiqueta de finalización o finalizador adecuados al mensaje XML y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f340-119">To resolve this error, add the appropriate end tag or trailer to the XML message, and then resend the message.</span></span>