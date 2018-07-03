---
title: Disposition-Notification-Option no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b807a8-eec9-45a5-83cc-075c91b4bc9e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50831c03bc7dc0412cdb6fcd40ca981e87cf43f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023194"
---
# <a name="disposition-notification-option-is-invalid"></a><span data-ttu-id="83876-102">Disposition-Notification-Option no es válido</span><span class="sxs-lookup"><span data-stu-id="83876-102">Disposition-Notification-Option is invalid</span></span>
## <a name="details"></a><span data-ttu-id="83876-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="83876-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="83876-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="83876-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="83876-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="83876-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="83876-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="83876-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="83876-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="83876-107">Event Source</span></span>   | <span data-ttu-id="83876-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83876-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="83876-109">Componente</span><span class="sxs-lookup"><span data-stu-id="83876-109">Component</span></span>    |                                       <span data-ttu-id="83876-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="83876-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="83876-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="83876-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="83876-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="83876-112">Message Text</span></span>   |              <span data-ttu-id="83876-113">Valor disposition-Notification-Option: "{0}" no es válido.</span><span class="sxs-lookup"><span data-stu-id="83876-113">Disposition-Notification-Option value: "{0}" is invalid.</span></span> <span data-ttu-id="83876-114">{1}</span><span class="sxs-lookup"><span data-stu-id="83876-114">{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="83876-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="83876-115">Explanation</span></span>  
 <span data-ttu-id="83876-116">Este evento de error,  indica que la canalización de recepción AS2 no pudo generar el MDN debido a que el encabezado Disposition-Notification-Option no era válido.</span><span class="sxs-lookup"><span data-stu-id="83876-116">This Error/Warning/Information event indicates that the AS2 receive pipeline could not generate the MDN because the Disposition-Notification-Option header was invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="83876-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="83876-117">User Action</span></span>  
 <span data-ttu-id="83876-118">Para resolver este error, asegúrese de que el encabezado Disposition-Notification-Option en el mensaje AS2 se ajusta a la sintaxis descrita en RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2").</span><span class="sxs-lookup"><span data-stu-id="83876-118">To resolve this error, make sure that the Disposition-Notification-Option header in the AS2 message conforms to the syntax described in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2").</span></span> <span data-ttu-id="83876-119">Asegúrese de que el encabezado Signed-Receipt-Protocol se ha establecido en "optional" o "pcks7-signature" y que el encabezado Signed-Receipt-MICAlg se ha establecido en "optional", "MD5" o "SHA1".</span><span class="sxs-lookup"><span data-stu-id="83876-119">Ensure that the Signed-Receipt-Protocol header is set to "optional" or "pcks7-signature", and that the Signed-Receipt-MICAlg header is set to "optional", "MD5", or "SHA1".</span></span> <span data-ttu-id="83876-120">(Los dos encabezados se incluyen en el encabezado Disposition-Notification-Option).</span><span class="sxs-lookup"><span data-stu-id="83876-120">(Both of these headers are included in the Disposition-Notification-Option header.)</span></span>