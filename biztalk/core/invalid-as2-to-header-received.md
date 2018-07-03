---
title: AS2 no válido-al encabezado recibido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56cd16b3-511b-4716-8806-817f174f0b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bc9fd8043205920f69aec2ca7efbfcc9478724
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010357"
---
# <a name="invalid-as2-to-header-received"></a><span data-ttu-id="7a4fe-102">Encabezado AS2-To recibido</span><span class="sxs-lookup"><span data-stu-id="7a4fe-102">Invalid AS2-To header received</span></span>
## <a name="details"></a><span data-ttu-id="7a4fe-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7a4fe-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7a4fe-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7a4fe-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7a4fe-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7a4fe-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7a4fe-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7a4fe-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7a4fe-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7a4fe-107">Event Source</span></span>   | <span data-ttu-id="7a4fe-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a4fe-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="7a4fe-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7a4fe-109">Component</span></span>    |                                       <span data-ttu-id="7a4fe-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="7a4fe-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="7a4fe-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7a4fe-111">Symbolic Name</span></span>  |                          <span data-ttu-id="7a4fe-112">InvalidAS2ToNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="7a4fe-112">InvalidAS2ToNameHeaderReceivedError</span></span>                           |
|  <span data-ttu-id="7a4fe-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7a4fe-113">Message Text</span></span>   |                      <span data-ttu-id="7a4fe-114">Encabezado AS2-To recibido.</span><span class="sxs-lookup"><span data-stu-id="7a4fe-114">Invalid AS2-To header received.</span></span>  <span data-ttu-id="7a4fe-115">Valor: {0}</span><span class="sxs-lookup"><span data-stu-id="7a4fe-115">Value: {0}</span></span>                       |
  
## <a name="explanation"></a><span data-ttu-id="7a4fe-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="7a4fe-116">Explanation</span></span>  
 <span data-ttu-id="7a4fe-117">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del encabezado AS2-To en el mensaje no se ajustaba a las especificaciones de AS2 RFC 4130.</span><span class="sxs-lookup"><span data-stu-id="7a4fe-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-To header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a4fe-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7a4fe-118">User Action</span></span>  
 <span data-ttu-id="7a4fe-119">Para resolver este error, asegúrese de que el valor del encabezado AS2-To del mensaje se ajusta a las especificaciones de la sección 6.2 de AS2 RFC 4130.</span><span class="sxs-lookup"><span data-stu-id="7a4fe-119">To resolve this error, make sure that the value in the AS2-To header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>