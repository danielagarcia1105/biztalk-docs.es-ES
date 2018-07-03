---
title: Elemento de datos demasiado corto | Microsoft Docs
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
ms.openlocfilehash: db14770404a45ddbfd3aea6ed71e9b8b22417515
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005301"
---
# <a name="data-element-too-short"></a><span data-ttu-id="0a5f8-102">Elemento de datos demasiado corto.</span><span class="sxs-lookup"><span data-stu-id="0a5f8-102">Data element too short</span></span>
## <a name="details"></a><span data-ttu-id="0a5f8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0a5f8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0a5f8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0a5f8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0a5f8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0a5f8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0a5f8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0a5f8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0a5f8-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0a5f8-107">Event Source</span></span>   | <span data-ttu-id="0a5f8-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a5f8-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="0a5f8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0a5f8-109">Component</span></span>    |                                       <span data-ttu-id="0a5f8-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="0a5f8-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0a5f8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0a5f8-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="0a5f8-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0a5f8-112">Message Text</span></span>   |                                 <span data-ttu-id="0a5f8-113">Elemento de datos demasiado corto.</span><span class="sxs-lookup"><span data-stu-id="0a5f8-113">Data element too short</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="0a5f8-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="0a5f8-114">Explanation</span></span>  
 <span data-ttu-id="0a5f8-115">Este evento de error,  indica que la canalización de recepción de EDI o la canalización de envío de EDI no pudo procesar el intercambio entrante porque un elemento de datos tenía una longitud menor que la mínima que especifica el esquema.</span><span class="sxs-lookup"><span data-stu-id="0a5f8-115">This Error/Warning/Information event indicates that the EDI receive pipeline or the EDI Send pipeline could not process the incoming interchange because a data element was shorter than the minimum length specified by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a5f8-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0a5f8-116">User Action</span></span>  
 <span data-ttu-id="0a5f8-117">Para resolver este error, aumente de tamaño el elemento de datos del intercambio que era demasiado corto de modo que supere la longitud mínima.</span><span class="sxs-lookup"><span data-stu-id="0a5f8-117">To resolve this error, lengthen the data element in the interchange that was too short so it is greater than the minimum length.</span></span> <span data-ttu-id="0a5f8-118">Para determinar la longitud mínima, abra el esquema en la carpeta \XSD_Schema, busque en el identificador del elemento de datos e identifique cuál es el valor de minLength.</span><span class="sxs-lookup"><span data-stu-id="0a5f8-118">To determine the minimum length, open the schema in the \XSD_Schema folder, search on the data element ID, and identify what the minLength value is.</span></span>