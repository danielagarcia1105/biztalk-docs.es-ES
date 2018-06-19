---
title: Elemento de datos demasiado corto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22c0551-3262-476c-a6c6-2fd214331244
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 311c40d80f1299ce4abcf5f2e5aec5cac2681251
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238260"
---
# <a name="data-element-too-short"></a><span data-ttu-id="b3675-102">Elemento de datos demasiado corto.</span><span class="sxs-lookup"><span data-stu-id="b3675-102">Data element too short</span></span>
## <a name="details"></a><span data-ttu-id="b3675-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b3675-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b3675-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b3675-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b3675-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b3675-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b3675-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b3675-106">Event ID</span></span>|-|  
|<span data-ttu-id="b3675-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b3675-107">Event Source</span></span>|<span data-ttu-id="b3675-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3675-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="b3675-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b3675-109">Component</span></span>|<span data-ttu-id="b3675-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="b3675-110">EDI Engine</span></span>|  
|<span data-ttu-id="b3675-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b3675-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="b3675-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b3675-112">Message Text</span></span>|<span data-ttu-id="b3675-113">Elemento de datos demasiado corto.</span><span class="sxs-lookup"><span data-stu-id="b3675-113">Data element too short</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b3675-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="b3675-114">Explanation</span></span>  
 <span data-ttu-id="b3675-115">Este evento de error,  indica que la canalización de recepción de EDI o la canalización de envío de EDI no pudo procesar el intercambio entrante porque un elemento de datos tenía una longitud menor que la mínima que especifica el esquema.</span><span class="sxs-lookup"><span data-stu-id="b3675-115">This Error/Warning/Information event indicates that the EDI receive pipeline or the EDI Send pipeline could not process the incoming interchange because a data element was shorter than the minimum length specified by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b3675-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b3675-116">User Action</span></span>  
 <span data-ttu-id="b3675-117">Para resolver este error, aumente de tamaño el elemento de datos del intercambio que era demasiado corto de modo que supere la longitud mínima.</span><span class="sxs-lookup"><span data-stu-id="b3675-117">To resolve this error, lengthen the data element in the interchange that was too short so it is greater than the minimum length.</span></span> <span data-ttu-id="b3675-118">Para determinar la longitud mínima, abra el esquema en la carpeta \XSD_Schema, busque en el identificador del elemento de datos e identifique cuál es el valor de minLength.</span><span class="sxs-lookup"><span data-stu-id="b3675-118">To determine the minimum length, open the schema in the \XSD_Schema folder, search on the data element ID, and identify what the minLength value is.</span></span>