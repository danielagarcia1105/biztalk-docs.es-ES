---
title: Esquema no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb3e70a-d23c-45e9-bde5-edae6731e58a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 063c60ed07d89429f14f7ed3b7c090cdc0bac033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008165"
---
# <a name="invalid-scheme"></a><span data-ttu-id="d33e0-102">Esquema no válido</span><span class="sxs-lookup"><span data-stu-id="d33e0-102">Invalid scheme</span></span>
## <a name="details"></a><span data-ttu-id="d33e0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d33e0-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="d33e0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d33e0-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="d33e0-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d33e0-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="d33e0-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d33e0-106">Event ID</span></span>     |                                         <span data-ttu-id="d33e0-107">0</span><span class="sxs-lookup"><span data-stu-id="d33e0-107">0</span></span>                                          |
|  <span data-ttu-id="d33e0-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d33e0-108">Event Source</span></span>   |                                         <span data-ttu-id="d33e0-109">0</span><span class="sxs-lookup"><span data-stu-id="d33e0-109">0</span></span>                                          |
|    <span data-ttu-id="d33e0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d33e0-110">Component</span></span>    |                                         <span data-ttu-id="d33e0-111">0</span><span class="sxs-lookup"><span data-stu-id="d33e0-111">0</span></span>                                          |
|  <span data-ttu-id="d33e0-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d33e0-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="d33e0-113">0</span><span class="sxs-lookup"><span data-stu-id="d33e0-113">0</span></span>                                          |
|  <span data-ttu-id="d33e0-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d33e0-114">Message Text</span></span>   |                  <span data-ttu-id="d33e0-115">Esquema no válido. se esperaba el esquema "{0}"o"{1}"</span><span class="sxs-lookup"><span data-stu-id="d33e0-115">Invalid scheme; expecting scheme "{0}" or "{1}"</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="d33e0-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="d33e0-116">Explanation</span></span>  
 <span data-ttu-id="d33e0-117">Se ha producido una de las situaciones siguientes: la dirección que se especifica en el campo URI (identificador uniforme de recursos) debe comenzar con http:// o https://.</span><span class="sxs-lookup"><span data-stu-id="d33e0-117">One of the following situations has occurred: the address that is specified in the URI (uniform resource identifier) field must start with either http:// or https://.</span></span> <span data-ttu-id="d33e0-118">O bien, el esquema no coincide con lo especificado en la implementación del elemento de enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="d33e0-118">Or the scheme does not match what is specified in the implementation of the transport binding element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d33e0-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d33e0-119">User Action</span></span>  
 <span data-ttu-id="d33e0-120">Escriba un URI de dirección de proxy válido que empiece por http:// o https://</span><span class="sxs-lookup"><span data-stu-id="d33e0-120">Enter a valid proxy address URI that starts with http:// or https://</span></span>