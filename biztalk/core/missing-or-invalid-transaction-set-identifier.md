---
title: Identificador de conjunto de transacciones falta o no válidos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 282c8128-7d23-44e2-bf44-e90e52cb5fb1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f0444468b7f7ff52b38bcd8db01a6bded5ed0a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009933"
---
# <a name="missing-or-invalid-transaction-set-identifier"></a><span data-ttu-id="1efee-102">El identificador del conjunto de transacciones falta o no es válido</span><span class="sxs-lookup"><span data-stu-id="1efee-102">Missing or invalid Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="1efee-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1efee-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="1efee-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1efee-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="1efee-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1efee-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="1efee-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1efee-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="1efee-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1efee-107">Event Source</span></span>   | <span data-ttu-id="1efee-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1efee-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="1efee-109">Componente</span><span class="sxs-lookup"><span data-stu-id="1efee-109">Component</span></span>    |                                       <span data-ttu-id="1efee-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="1efee-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="1efee-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1efee-111">Symbolic Name</span></span>  |                     <span data-ttu-id="1efee-112">EfactTsMissingOrInvalidTsIdentiferDescription</span><span class="sxs-lookup"><span data-stu-id="1efee-112">EfactTsMissingOrInvalidTsIdentiferDescription</span></span>                      |
|  <span data-ttu-id="1efee-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1efee-113">Message Text</span></span>   |                     <span data-ttu-id="1efee-114">El identificador del conjunto de transacciones falta o no es válido</span><span class="sxs-lookup"><span data-stu-id="1efee-114">Missing or invalid Transaction set identifier</span></span>                      |
  
## <a name="explanation"></a><span data-ttu-id="1efee-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="1efee-115">Explanation</span></span>  
 <span data-ttu-id="1efee-116">Este evento de error,  indica que la canalización de recepción o de envío no pudo procesar el intercambio EDIFACT porque el valor del identificador del conjunto de transacciones (en el campo UNH2.1) faltaba o contenía un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="1efee-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the EDIFACT interchange because the value of the transaction set identifier (in the UNH2.1 field) was missing or had an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1efee-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1efee-117">User Action</span></span>  
 <span data-ttu-id="1efee-118">Para resolver este error, asegúrese de que el intercambio tenga un valor para el campo UNH2.1.</span><span class="sxs-lookup"><span data-stu-id="1efee-118">To resolve this error, make sure that the interchange has a value for the UNH2.1 field.</span></span> <span data-ttu-id="1efee-119">Compruebe que el valor de UNH2.1 es un designador de tipo de documento válido de uno o seis dígitos.</span><span class="sxs-lookup"><span data-stu-id="1efee-119">Verify that the value of UNH2.1 is a valid one-digit to six-digit document-type designator.</span></span>