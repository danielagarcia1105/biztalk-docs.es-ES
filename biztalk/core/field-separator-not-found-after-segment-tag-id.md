---
title: Separador de campos no se encuentra después de Id. de etiqueta de segmento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f6f0a74-3560-4d6d-9893-85e8426e6b17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 818a061cd723c0d8f8c58570c9e6df94a670942b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245940"
---
# <a name="field-separator-not-found-after-segment-tag-id"></a><span data-ttu-id="b290e-102">No se encontró el separador de campos después del Id. de etiqueta de segmento.</span><span class="sxs-lookup"><span data-stu-id="b290e-102">Field separator not found after segment tag id</span></span>
## <a name="details"></a><span data-ttu-id="b290e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b290e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b290e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b290e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b290e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b290e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b290e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b290e-106">Event ID</span></span>|-|  
|<span data-ttu-id="b290e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b290e-107">Event Source</span></span>|<span data-ttu-id="b290e-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b290e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="b290e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b290e-109">Component</span></span>|<span data-ttu-id="b290e-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="b290e-110">EDI Engine</span></span>|  
|<span data-ttu-id="b290e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b290e-111">Symbolic Name</span></span>|<span data-ttu-id="b290e-112">X12SeFsNotFoundAfterTagIdDescription</span><span class="sxs-lookup"><span data-stu-id="b290e-112">X12SeFsNotFoundAfterTagIdDescription</span></span>|  
|<span data-ttu-id="b290e-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b290e-113">Message Text</span></span>|<span data-ttu-id="b290e-114">No se encontró el separador de campos después del Id. de etiqueta de segmento.</span><span class="sxs-lookup"><span data-stu-id="b290e-114">Field separator not found after segment tag id</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b290e-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="b290e-115">Explanation</span></span>  
 <span data-ttu-id="b290e-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía un segmento que incluía un identificador de segmento sin separador de elementos de datos situado inmediatamente a continuación.</span><span class="sxs-lookup"><span data-stu-id="b290e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the interchange because the interchange contained a segment that had a segment identifier without a data element separator immediately following it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b290e-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b290e-117">User Action</span></span>  
 <span data-ttu-id="b290e-118">Para resolver este error, asegúrese de que todos los identificadores de segmento del intercambio tengan separadores de elementos de datos situados inmediatamente a continuación de ellos y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="b290e-118">To resolve this error, ensure that all segment identifiers in the interchange have data element separators immediately following them, and then have the interchange resent.</span></span>