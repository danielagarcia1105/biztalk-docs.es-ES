---
title: No se permite el tipo de mensaje como parte del acuerdo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ed9c1e4891a3365484b60e51848a998f2d152b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982373"
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a><span data-ttu-id="95083-102">No se permite el tipo de mensaje como parte del acuerdo</span><span class="sxs-lookup"><span data-stu-id="95083-102">Message Type is not allowed as part of the Agreement</span></span>
## <a name="details"></a><span data-ttu-id="95083-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="95083-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="95083-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="95083-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="95083-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="95083-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="95083-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="95083-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="95083-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="95083-107">Event Source</span></span>   | <span data-ttu-id="95083-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95083-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="95083-109">Componente</span><span class="sxs-lookup"><span data-stu-id="95083-109">Component</span></span>    |                                       <span data-ttu-id="95083-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="95083-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="95083-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="95083-111">Symbolic Name</span></span>  |                          <span data-ttu-id="95083-112">TransactionSetNotAllowedDescription</span><span class="sxs-lookup"><span data-stu-id="95083-112">TransactionSetNotAllowedDescription</span></span>                           |
|  <span data-ttu-id="95083-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="95083-113">Message Text</span></span>   |               <span data-ttu-id="95083-114">Tipo de mensaje {0} no se permite como parte del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="95083-114">Message Type {0} is not allowed as part of the Agreement.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="95083-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="95083-115">Explanation</span></span>  
 <span data-ttu-id="95083-116">Este evento de error,  indica que BizTalk Server no pudo procesar el documento porque el tipo de mensaje del documento no se permite como parte del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="95083-116">This Error/Warning/Information event indicates BizTalk Server was able to process the document because the message type of the document is not allowed as part of the agreement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95083-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="95083-117">User Action</span></span>  
 <span data-ttu-id="95083-118">Para resolver este error, mire los tipos de mensaje permitidos y no permitidos como parte del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="95083-118">To resolve this error, please look at the message types that are allowed and not allowed as part of the agreement.</span></span>