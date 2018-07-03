---
title: Intercambio de secuencia de número de control agotada para el socio y TPA | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e77c0574-bc51-4690-a7f6-5702f6486f05
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19f1aeb79febf8bca10f46b2b5a3a5ba319f6028
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989365"
---
# <a name="interchange-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="15c85-102">Secuencia de número de control de intercambio agotada para el socio y TPA</span><span class="sxs-lookup"><span data-stu-id="15c85-102">Interchange control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="15c85-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="15c85-103">Details</span></span>  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="15c85-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="15c85-104">Product Name</span></span>   |                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| <span data-ttu-id="15c85-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="15c85-105">Product Version</span></span> |                                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    <span data-ttu-id="15c85-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="15c85-106">Event ID</span></span>     |                                                                                 -                                                                                  |
|  <span data-ttu-id="15c85-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="15c85-107">Event Source</span></span>   |                                       <span data-ttu-id="15c85-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15c85-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                       |
|    <span data-ttu-id="15c85-109">Componente</span><span class="sxs-lookup"><span data-stu-id="15c85-109">Component</span></span>    |                                                                             <span data-ttu-id="15c85-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="15c85-110">EDI Engine</span></span>                                                                             |
|  <span data-ttu-id="15c85-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="15c85-111">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="15c85-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="15c85-112">EdiControlNumberExhaustedForParty</span></span>                                                                  |
|  <span data-ttu-id="15c85-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="15c85-113">Message Text</span></span>   | <span data-ttu-id="15c85-114">Secuencia de número de control agotada de intercambio para el socio '{1}'para el TPA'{2}'.</span><span class="sxs-lookup"><span data-stu-id="15c85-114">Interchange control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="15c85-115">Restablezca la secuencia en {2} - propiedades de EDI mediante la administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="15c85-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="15c85-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="15c85-116">Explanation</span></span>  
 <span data-ttu-id="15c85-117">Este evento de error, advertencia o información indica que BizTalk Server no pudo procesar el documento debido a que el intervalo de control del intercambio se ha agotado para el acuerdo en {2}.</span><span class="sxs-lookup"><span data-stu-id="15c85-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Interchange control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15c85-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="15c85-118">User Action</span></span>  
 <span data-ttu-id="15c85-119">Para resolver este error, active la casilla para restablecer el número de control del acuerdo {2}, aumente el intervalo de números de control o pulse el botón Restablecer contra la especificación del intervalo de números de control en el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="15c85-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>