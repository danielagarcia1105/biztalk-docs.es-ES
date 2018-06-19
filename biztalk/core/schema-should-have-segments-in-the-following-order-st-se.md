---
title: El esquema de control debería tener segmentos en el orden siguiente ST .... SE | Documentos de Microsoft
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
ms.openlocfilehash: 2563247dc6fc4c092fe2867c6b4d03239c4be7e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269100"
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a><span data-ttu-id="f0cfc-102">El esquema de control debería tener segmentos en el orden siguiente ST .... SE</span><span class="sxs-lookup"><span data-stu-id="f0cfc-102">Schema should have segments in the following order ST .... SE</span></span>
## <a name="details"></a><span data-ttu-id="f0cfc-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f0cfc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0cfc-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f0cfc-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f0cfc-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f0cfc-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f0cfc-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f0cfc-106">Event ID</span></span>|-|  
|<span data-ttu-id="f0cfc-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f0cfc-107">Event Source</span></span>|<span data-ttu-id="f0cfc-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0cfc-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="f0cfc-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f0cfc-109">Component</span></span>|<span data-ttu-id="f0cfc-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f0cfc-110">EDI Engine</span></span>|  
|<span data-ttu-id="f0cfc-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f0cfc-111">Symbolic Name</span></span>|<span data-ttu-id="f0cfc-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="f0cfc-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span></span>|  
|<span data-ttu-id="f0cfc-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f0cfc-113">Message Text</span></span>|<span data-ttu-id="f0cfc-114">El esquema de control debería tener segmentos en el orden siguiente ST .... SE</span><span class="sxs-lookup"><span data-stu-id="f0cfc-114">Schema should have segments in the following order ST .... SE</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f0cfc-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f0cfc-115">Explanation</span></span>  
 <span data-ttu-id="f0cfc-116">Este evento de error,  indica que el esquema de documento personalizado no es válido porque los encabezados y finalizadores no estaban en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="f0cfc-116">This Error/Warning/Information event indicates that a custom document schema is invalid because the headers and trailers were not in the correct order.</span></span> <span data-ttu-id="f0cfc-117">BizTalk Server realiza esta validación cuando se implementa el esquema.</span><span class="sxs-lookup"><span data-stu-id="f0cfc-117">BizTalk Server performs this validation when the schema is deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0cfc-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f0cfc-118">User Action</span></span>  
 <span data-ttu-id="f0cfc-119">Para resolver este error, cambie el esquema del documento personalizado de modo que los encabezados y finalizadores se encuentren en el orden correcto y vuelva a implementar el esquema.</span><span class="sxs-lookup"><span data-stu-id="f0cfc-119">To resolve this error, change the customized document schema so that the headers and trailers are in the correct order, and then redeploy the schema.</span></span>