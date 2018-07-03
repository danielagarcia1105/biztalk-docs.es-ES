---
title: Conjunto de delimitadores no válido porque al menos uno de los delimitadores está fuera del intervalo permitido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a54467c6d611aefd58d2dfd51c21974c3a5df7c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022514"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a><span data-ttu-id="54112-102">Grupo de delimitadores no válido porque al menos uno de los delimitadores está fuera del intervalo permitido</span><span class="sxs-lookup"><span data-stu-id="54112-102">Invalid delimiter set because at least one of the delimiters is outside the allowed range</span></span>
## <a name="details"></a><span data-ttu-id="54112-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="54112-103">Details</span></span>  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="54112-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="54112-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| <span data-ttu-id="54112-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="54112-105">Product Version</span></span> |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    <span data-ttu-id="54112-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="54112-106">Event ID</span></span>     |                                                   -                                                    |
|  <span data-ttu-id="54112-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="54112-107">Event Source</span></span>   |         <span data-ttu-id="54112-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54112-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>         |
|    <span data-ttu-id="54112-109">Componente</span><span class="sxs-lookup"><span data-stu-id="54112-109">Component</span></span>    |                                               <span data-ttu-id="54112-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="54112-110">EDI Engine</span></span>                                               |
|  <span data-ttu-id="54112-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="54112-111">Symbolic Name</span></span>  |                                          <span data-ttu-id="54112-112">DelimiterOutOfRange</span><span class="sxs-lookup"><span data-stu-id="54112-112">DelimiterOutOfRange</span></span>                                           |
|  <span data-ttu-id="54112-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="54112-113">Message Text</span></span>   | <span data-ttu-id="54112-114">Conjunto de delimitadores no válido {0}, al menos uno de los delimitadores está fuera del intervalo permitido de 0 a 127</span><span class="sxs-lookup"><span data-stu-id="54112-114">Invalid delimiter set {0}, atleast one of the delimiters is outside the allowed range of 0 through 127</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="54112-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="54112-115">Explanation</span></span>  
 <span data-ttu-id="54112-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante, pues uno o varios separadores del intercambio estaban fuera del intervalo de valores del conjunto de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="54112-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because one or more separators in the interchange was outside the range of values in the ASCII character set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54112-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="54112-117">User Action</span></span>  
 <span data-ttu-id="54112-118">Para resolver este error, asegúrese de que cada separador del intercambio se encuentra en el conjunto de caracteres ASCII y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="54112-118">To resolve this error, make sure that each separator in the interchange is in the ASCII character set, and then have the interchange resent.</span></span>