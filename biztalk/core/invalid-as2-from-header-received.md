---
title: "AS2 no válido: encabezado recibido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d773e09-8526-4533-9066-8e743e65a688
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f20a74e60a6365c0c16e139e8b2caca1bc33646
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-from-header-received"></a><span data-ttu-id="571a5-102">Encabezado AS2-From no válido recibido</span><span class="sxs-lookup"><span data-stu-id="571a5-102">Invalid AS2-From header received</span></span>
## <a name="details"></a><span data-ttu-id="571a5-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="571a5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="571a5-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="571a5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="571a5-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="571a5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="571a5-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="571a5-106">Event ID</span></span>|-|  
|<span data-ttu-id="571a5-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="571a5-107">Event Source</span></span>|<span data-ttu-id="571a5-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="571a5-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="571a5-109">Componente</span><span class="sxs-lookup"><span data-stu-id="571a5-109">Component</span></span>|<span data-ttu-id="571a5-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="571a5-110">AS2 Engine</span></span>|  
|<span data-ttu-id="571a5-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="571a5-111">Symbolic Name</span></span>|<span data-ttu-id="571a5-112">InvalidAS2FromNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="571a5-112">InvalidAS2FromNameHeaderReceivedError</span></span>|  
|<span data-ttu-id="571a5-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="571a5-113">Message Text</span></span>|<span data-ttu-id="571a5-114">Encabezado AS2-From no válido recibido.</span><span class="sxs-lookup"><span data-stu-id="571a5-114">Invalid AS2-From header received.</span></span>  <span data-ttu-id="571a5-115">Valor: {0}</span><span class="sxs-lookup"><span data-stu-id="571a5-115">Value: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="571a5-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="571a5-116">Explanation</span></span>  
 <span data-ttu-id="571a5-117">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante, pues el valor del encabezado AS2-From en el mensaje no se ajustaba a las especificaciones de AS2 RFC 4130.</span><span class="sxs-lookup"><span data-stu-id="571a5-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-From header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="571a5-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="571a5-118">User Action</span></span>  
 <span data-ttu-id="571a5-119">Para resolver este error, asegúrese de que el valor del encabezado AS2-From del mensaje se ajusta a las especificaciones de la sección 6.2 de AS2 RFC 4130 y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="571a5-119">To resolve this error, make sure that the value in the AS2-From header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>