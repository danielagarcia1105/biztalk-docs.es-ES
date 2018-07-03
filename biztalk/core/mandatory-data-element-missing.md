---
title: Falta un elemento de datos obligatorio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510d54b3-13de-4735-92ec-04fd4b9d460e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a44e4824805a137121bf1f5bd030cb16329484d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966493"
---
# <a name="mandatory-data-element-missing"></a><span data-ttu-id="c46cf-102">Falta elemento de datos obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c46cf-102">Mandatory data element missing</span></span>
## <a name="details"></a><span data-ttu-id="c46cf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c46cf-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c46cf-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c46cf-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c46cf-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c46cf-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c46cf-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c46cf-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c46cf-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c46cf-107">Event Source</span></span>   | <span data-ttu-id="c46cf-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c46cf-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="c46cf-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c46cf-109">Component</span></span>    |                                       <span data-ttu-id="c46cf-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c46cf-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c46cf-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c46cf-111">Symbolic Name</span></span>  |                      <span data-ttu-id="c46cf-112">X12DeMandatoryDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="c46cf-112">X12DeMandatoryDataElementMissingDescription</span></span>                       |
|  <span data-ttu-id="c46cf-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c46cf-113">Message Text</span></span>   |                             <span data-ttu-id="c46cf-114">Falta elemento de datos obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c46cf-114">Mandatory data element missing</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="c46cf-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c46cf-115">Explanation</span></span>  
 <span data-ttu-id="c46cf-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante, pues el intercambio no contenía elementos de datos que requiere el esquema del mensaje (para el cual minOccurs es mayor que 0).</span><span class="sxs-lookup"><span data-stu-id="c46cf-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a data element that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c46cf-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c46cf-117">User Action</span></span>  
 <span data-ttu-id="c46cf-118">Para resolver este error, asegúrese de que el intercambio contiene todos los elementos de datos que requiere el esquema del mensaje y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c46cf-118">To resolve this error, make sure that the interchange contains all the data elements required by the message schema, and then have the message resent.</span></span>