---
title: Elemento de datos demasiado largo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf608cc1-d482-4e19-8f56-10d9e03feb79
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbfe63fccc442c35411bfae04c7f27629ce066ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238268"
---
# <a name="data-element-too-long"></a><span data-ttu-id="2879f-102">Elemento de datos demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="2879f-102">Data element too long</span></span>
## <a name="details"></a><span data-ttu-id="2879f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2879f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2879f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2879f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2879f-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2879f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2879f-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2879f-106">Event ID</span></span>|-|  
|<span data-ttu-id="2879f-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2879f-107">Event Source</span></span>|<span data-ttu-id="2879f-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2879f-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="2879f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2879f-109">Component</span></span>|<span data-ttu-id="2879f-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="2879f-110">EDI Engine</span></span>|  
|<span data-ttu-id="2879f-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2879f-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="2879f-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2879f-112">Message Text</span></span>|<span data-ttu-id="2879f-113">Elemento de datos demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="2879f-113">Data element too long</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2879f-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="2879f-114">Explanation</span></span>  
 <span data-ttu-id="2879f-115">Este evento de error,  indica que la canalización de recepción de EDI o la canalización de envío de EDI no pudo procesar el intercambio entrante porque un elemento de datos tenía una longitud mayor que la máxima que especifica el esquema.</span><span class="sxs-lookup"><span data-stu-id="2879f-115">This Error/Warning/Information event indicates that the EDI receive pipeline or the EDI Send pipeline could not process the incoming interchange because a data element was longer than the maximum length specified by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2879f-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2879f-116">User Action</span></span>  
 <span data-ttu-id="2879f-117">Para resolver este error, disminuya de tamaño el elemento de datos del intercambio que era demasiado largo de modo que quede por debajo de la longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="2879f-117">To resolve this error, shorten the data element in the interchange that was too long so it is below the maximum limit.</span></span> <span data-ttu-id="2879f-118">Para determinar la longitud máxima, abra el esquema en la carpeta \XSD_Schema, busque en el identificador del elemento de datos e identifique cuál es el valor de maxLength.</span><span class="sxs-lookup"><span data-stu-id="2879f-118">To determine the maximum length, open the schema in the \XSD_Schema folder, search on the data element ID, and identify what the maxLength value is.</span></span>