---
title: "Carácter no válido en el elemento de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db7e2c72-f2cc-4157-aa26-062d2cc1210b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc805fbede667013b56088b3d2c29913157c2fe5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-character-in-data-element"></a><span data-ttu-id="a8701-102">Carácter no válido en el elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="a8701-102">Invalid character in data element</span></span>
## <a name="details"></a><span data-ttu-id="a8701-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a8701-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8701-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a8701-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a8701-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a8701-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a8701-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a8701-106">Event ID</span></span>|-|  
|<span data-ttu-id="a8701-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a8701-107">Event Source</span></span>|<span data-ttu-id="a8701-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8701-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="a8701-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a8701-109">Component</span></span>|<span data-ttu-id="a8701-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="a8701-110">EDI Engine</span></span>|  
|<span data-ttu-id="a8701-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a8701-111">Symbolic Name</span></span>|<span data-ttu-id="a8701-112">X12DeInvalidCharacterInDataElementDescription</span><span class="sxs-lookup"><span data-stu-id="a8701-112">X12DeInvalidCharacterInDataElementDescription</span></span>|  
|<span data-ttu-id="a8701-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a8701-113">Message Text</span></span>|<span data-ttu-id="a8701-114">Carácter no válido en el elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="a8701-114">Invalid character in data element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a8701-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="a8701-115">Explanation</span></span>  
 <span data-ttu-id="a8701-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque un valor de un elemento de datos no se ajustaba al valor especificado en el esquema EDI.</span><span class="sxs-lookup"><span data-stu-id="a8701-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of a data element did not conform to the value specified in the EDI schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8701-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a8701-117">User Action</span></span>  
 <span data-ttu-id="a8701-118">Para resolver este error, asegúrese de que el valor del elemento de datos se ajusta al esquema EDI y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="a8701-118">To resolve this error, make sure that the value in the data element conforms to the EDI schema, and then have the interchange resent.</span></span>