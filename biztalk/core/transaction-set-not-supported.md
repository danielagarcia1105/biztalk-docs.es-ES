---
title: Conjunto de transacciones no admitido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ffe8528-f34f-4189-8ee6-4ae1afb50c92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e767e81ba45ab711cc8c84b5f682ac0eba56b5a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001139"
---
# <a name="transaction-set-not-supported"></a><span data-ttu-id="76abe-102">Conjunto de transacciones no admitido.</span><span class="sxs-lookup"><span data-stu-id="76abe-102">Transaction Set Not Supported</span></span>
## <a name="details"></a><span data-ttu-id="76abe-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="76abe-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="76abe-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="76abe-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="76abe-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="76abe-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="76abe-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="76abe-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="76abe-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="76abe-107">Event Source</span></span>   | <span data-ttu-id="76abe-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76abe-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="76abe-109">Componente</span><span class="sxs-lookup"><span data-stu-id="76abe-109">Component</span></span>    |                                       <span data-ttu-id="76abe-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="76abe-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="76abe-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="76abe-111">Symbolic Name</span></span>  |                              <span data-ttu-id="76abe-112">X12TsNotSupportedDescription</span><span class="sxs-lookup"><span data-stu-id="76abe-112">X12TsNotSupportedDescription</span></span>                              |
|  <span data-ttu-id="76abe-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="76abe-113">Message Text</span></span>   |                             <span data-ttu-id="76abe-114">Conjunto de transacciones no admitido.</span><span class="sxs-lookup"><span data-stu-id="76abe-114">Transaction Set Not Supported</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="76abe-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="76abe-115">Explanation</span></span>  
 <span data-ttu-id="76abe-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque no se ha implementado ningún esquema de documento para el tipo de documento de dicho conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="76abe-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a document schema has not been deployed for the document type of that transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="76abe-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="76abe-117">User Action</span></span>  
 <span data-ttu-id="76abe-118">Para resolver este error, en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] implemente un esquema de documento para el tipo de documento del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="76abe-118">To resolve this error, in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] deploy a document schema for the document type of the transaction set.</span></span>