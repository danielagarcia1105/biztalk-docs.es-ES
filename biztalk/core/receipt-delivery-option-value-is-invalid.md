---
title: No es válido el valor Receipt-Delivery-Option | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eed306b-0912-4694-a55c-976128117c02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8966e3d95e89aff023300a9834ab1bca2915421f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994853"
---
# <a name="receipt-delivery-option-value-is-invalid"></a><span data-ttu-id="283bc-102">El valor Receipt-Delivery-Option no es válido</span><span class="sxs-lookup"><span data-stu-id="283bc-102">Receipt-Delivery-Option value is invalid</span></span>
## <a name="details"></a><span data-ttu-id="283bc-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="283bc-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="283bc-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="283bc-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="283bc-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="283bc-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="283bc-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="283bc-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="283bc-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="283bc-107">Event Source</span></span>   | <span data-ttu-id="283bc-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="283bc-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="283bc-109">Componente</span><span class="sxs-lookup"><span data-stu-id="283bc-109">Component</span></span>    |                                       <span data-ttu-id="283bc-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="283bc-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="283bc-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="283bc-111">Symbolic Name</span></span>  |                           <span data-ttu-id="283bc-112">InvalidReceiptDeliveryOptionError</span><span class="sxs-lookup"><span data-stu-id="283bc-112">InvalidReceiptDeliveryOptionError</span></span>                            |
|  <span data-ttu-id="283bc-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="283bc-113">Message Text</span></span>   |                 <span data-ttu-id="283bc-114">Valor de Receipt-Delivery-Option: "{0}" no es válido.</span><span class="sxs-lookup"><span data-stu-id="283bc-114">Receipt-Delivery-Option value: "{0}" is invalid.</span></span>  <span data-ttu-id="283bc-115">{1}</span><span class="sxs-lookup"><span data-stu-id="283bc-115">{1}</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="283bc-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="283bc-116">Explanation</span></span>  
 <span data-ttu-id="283bc-117">Este evento de error,  indica que Receipt-Delivery-Option en el mensaje AS2 recibido no es una dirección URL válida y no se ajusta a las especificaciones de AS2 RFC 4130.</span><span class="sxs-lookup"><span data-stu-id="283bc-117">This Error/Warning/Information event indicates that the Receipt-Delivery-Option in the received AS2 message is not a valid URL and does not conform to the specifications in the AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="283bc-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="283bc-118">User Action</span></span>  
 <span data-ttu-id="283bc-119">Para resolver este error, cambie Receipt-Delivery-Option en el mensaje AS2 para que incluya una dirección URL válida y se ajuste a las especificaciones del apartado 7.3 de AS2 RFC 4130; a continuación, vuelva a enviar el mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="283bc-119">To resolve this error, have the Receipt-Delivery-Option in the AS2 message changed to include a valid URL and conform to the specifications in section 7.3 of the AS2 RFC 4130, and then resend the AS2 message.</span></span>