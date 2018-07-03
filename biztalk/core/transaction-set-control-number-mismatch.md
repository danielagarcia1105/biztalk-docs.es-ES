---
title: Error de coincidencia de número de Control del conjunto de transacciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c4b0c3f-f3be-4c2c-8719-8e40aa7122b9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da4c20eb6853827709731c41631a38225214424d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021978"
---
# <a name="transaction-set-control-number-mismatch"></a><span data-ttu-id="0422c-102">El número de control de conjunto de transacciones no coincide.</span><span class="sxs-lookup"><span data-stu-id="0422c-102">Transaction Set Control Number Mismatch</span></span>
## <a name="details"></a><span data-ttu-id="0422c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0422c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0422c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0422c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0422c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0422c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0422c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0422c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0422c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0422c-107">Event Source</span></span>   | <span data-ttu-id="0422c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0422c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="0422c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0422c-109">Component</span></span>    |                                       <span data-ttu-id="0422c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="0422c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0422c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0422c-111">Symbolic Name</span></span>  |                         <span data-ttu-id="0422c-112">X12TsControlNumberMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="0422c-112">X12TsControlNumberMismatchDescription</span></span>                          |
|  <span data-ttu-id="0422c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0422c-113">Message Text</span></span>   |                        <span data-ttu-id="0422c-114">El número de control de conjunto de transacciones no coincide.</span><span class="sxs-lookup"><span data-stu-id="0422c-114">Transaction Set Control Number Mismatch</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="0422c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="0422c-115">Explanation</span></span>  
 <span data-ttu-id="0422c-116">Este evento de error,  indica que la canalización de recepción EDI rechazó el conjunto de transacciones entrantes porque el número de control contenido en el campo SE02 del conjunto de transacciones no coincidió con el número de control en el campo ST02.</span><span class="sxs-lookup"><span data-stu-id="0422c-116">This Error/Warning/Information event indicates that the EDI receive pipeline rejected the incoming transaction set because the control number contained in the SE02 field of the transaction set did not match the control number in the ST02 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0422c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0422c-117">User Action</span></span>  
 <span data-ttu-id="0422c-118">Para resolver este error, pida al remitente del conjunto de transacciones que cambie el número de control en el campo SE02 del conjunto de transacciones rechazado para que coincida con el número de control del campo ST02 y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="0422c-118">To resolve this error, have the sender of the transaction set change the control number in the SE02 field of the rejected transaction set to be the same as the control number in the ST02 field, and then resend the interchange.</span></span>