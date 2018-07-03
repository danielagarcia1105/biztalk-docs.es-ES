---
title: El esquema de control debería tener segmentos en el orden siguiente ST .... SE | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f4d1c6a-7d48-413a-9ef5-a0c49773dc16
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c98bc756e4bd75a8a15111c54f433a7f9c6c0509
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015173"
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a><span data-ttu-id="eaa3c-102">El esquema de control debería tener segmentos en el orden siguiente ST .... SE</span><span class="sxs-lookup"><span data-stu-id="eaa3c-102">Schema should have segments in the following order ST .... SE</span></span>
## <a name="details"></a><span data-ttu-id="eaa3c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eaa3c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="eaa3c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="eaa3c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="eaa3c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="eaa3c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="eaa3c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="eaa3c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="eaa3c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="eaa3c-107">Event Source</span></span>   | <span data-ttu-id="eaa3c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaa3c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="eaa3c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="eaa3c-109">Component</span></span>    |                                       <span data-ttu-id="eaa3c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="eaa3c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="eaa3c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eaa3c-111">Symbolic Name</span></span>  |                    <span data-ttu-id="eaa3c-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="eaa3c-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span></span>                    |
|  <span data-ttu-id="eaa3c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eaa3c-113">Message Text</span></span>   |             <span data-ttu-id="eaa3c-114">El esquema de control debería tener segmentos en el orden siguiente ST .... SE</span><span class="sxs-lookup"><span data-stu-id="eaa3c-114">Schema should have segments in the following order ST .... SE</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="eaa3c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="eaa3c-115">Explanation</span></span>  
 <span data-ttu-id="eaa3c-116">Este evento de error,  indica que el esquema de documento personalizado no es válido porque los encabezados y finalizadores no estaban en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="eaa3c-116">This Error/Warning/Information event indicates that a custom document schema is invalid because the headers and trailers were not in the correct order.</span></span> <span data-ttu-id="eaa3c-117">BizTalk Server realiza esta validación cuando se implementa el esquema.</span><span class="sxs-lookup"><span data-stu-id="eaa3c-117">BizTalk Server performs this validation when the schema is deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eaa3c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eaa3c-118">User Action</span></span>  
 <span data-ttu-id="eaa3c-119">Para resolver este error, cambie el esquema del documento personalizado de modo que los encabezados y finalizadores se encuentren en el orden correcto y vuelva a implementar el esquema.</span><span class="sxs-lookup"><span data-stu-id="eaa3c-119">To resolve this error, change the customized document schema so that the headers and trailers are in the correct order, and then redeploy the schema.</span></span>