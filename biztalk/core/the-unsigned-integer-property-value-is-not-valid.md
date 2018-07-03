---
title: El valor de propiedad unsigned integer no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63b0398f-7848-4971-8c08-95923d80cbe3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de6af46fc5719e8ccbe52dbfb419e104915d051e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973941"
---
# <a name="the-unsigned-integer-property-value-is-not-valid"></a><span data-ttu-id="3b532-102">El valor de propiedad unsigned integer no es válido</span><span class="sxs-lookup"><span data-stu-id="3b532-102">The unsigned integer property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="3b532-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3b532-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="3b532-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3b532-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3b532-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3b532-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="3b532-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3b532-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="3b532-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3b532-107">Event Source</span></span>   | <span data-ttu-id="3b532-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b532-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="3b532-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3b532-109">Component</span></span>    |                                       <span data-ttu-id="3b532-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="3b532-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="3b532-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3b532-111">Symbolic Name</span></span>  |                               <span data-ttu-id="3b532-112">Err_InvalidUnsignedInteger</span><span class="sxs-lookup"><span data-stu-id="3b532-112">Err_InvalidUnsignedInteger</span></span>                               |
|  <span data-ttu-id="3b532-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3b532-113">Message Text</span></span>   |                   <span data-ttu-id="3b532-114">El valor de propiedad unsigned integer no es válido.</span><span class="sxs-lookup"><span data-stu-id="3b532-114">The unsigned integer property value is not valid.</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="3b532-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="3b532-115">Explanation</span></span>  
 <span data-ttu-id="3b532-116">Este evento de error indica que BizTalk Server no ha podido comparar una propiedad de contexto mientras intenta decidir si procesar un mensaje por lotes o no.</span><span class="sxs-lookup"><span data-stu-id="3b532-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3b532-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3b532-117">User Action</span></span>  
 <span data-ttu-id="3b532-118">Para resolver este error, asegúrese de que el filtro proporcionado en los lotes activos no especifica una propiedad de contexto que tenga el tipo XSD unsigned integer con un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="3b532-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of unsigned integer with an invalid value.</span></span>