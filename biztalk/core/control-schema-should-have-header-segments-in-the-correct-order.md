---
title: Esquema de control debería tener segmentos de encabezado en el orden correcto | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f38e8f-243a-467f-84bd-a232ef148b4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c86b8d66526c0406faedeac0aedbbe0e1b270ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967925"
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a><span data-ttu-id="6ca70-102">El esquema de control debería tener segmentos de encabezado en el orden correcto</span><span class="sxs-lookup"><span data-stu-id="6ca70-102">Control schema should have header segments in the correct order</span></span>
## <a name="details"></a><span data-ttu-id="6ca70-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6ca70-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6ca70-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6ca70-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6ca70-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6ca70-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6ca70-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6ca70-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6ca70-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6ca70-107">Event Source</span></span>   | <span data-ttu-id="6ca70-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ca70-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="6ca70-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6ca70-109">Component</span></span>    |                                       <span data-ttu-id="6ca70-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="6ca70-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6ca70-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6ca70-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="6ca70-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6ca70-112">Message Text</span></span>   |  <span data-ttu-id="6ca70-113">Esquema de control debería tener segmentos en el orden siguiente: ISA GS ST... SE GE IEA</span><span class="sxs-lookup"><span data-stu-id="6ca70-113">Control schema should have segments in the following order: ISA GS ST .... SE GE IEA</span></span>  |
  
## <a name="explanation"></a><span data-ttu-id="6ca70-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="6ca70-114">Explanation</span></span>  
 <span data-ttu-id="6ca70-115">Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio entrante porque los encabezados y finalizadores del intercambio, de los grupos y de los conjuntos de transacciones no se encontraban en el orden correcto en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="6ca70-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because the headers and trailers for the interchange, groups, and transaction sets were not in the correct order in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6ca70-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6ca70-116">User Action</span></span>  
 <span data-ttu-id="6ca70-117">Para resolver este error, asegúrese de que los encabezados ISA, GS y ST, y que los finalizadores SE, GE e IEA, se encuentran en el orden correcto en el intercambio y, a continuación, vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="6ca70-117">To resolve this error, ensure that the ISA, GS, and ST headers, and the SE, GE, and IEA trailers, are in the correct order in the interchange, and then resend the interchange.</span></span>