---
title: Se detectó un error de BTS MIME al intentar descodificar un mensaje AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 629e09e950a6c49263230f23725002eee9be905b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985925"
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a><span data-ttu-id="469b7-102">Error de BTS MIME al intentar descodificar un mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="469b7-102">A BTS MIME error was encountered when attempting to decode an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="469b7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="469b7-103">Details</span></span>  
  
|                 |                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="469b7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="469b7-104">Product Name</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                         |
| <span data-ttu-id="469b7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="469b7-105">Product Version</span></span> |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                     |
|    <span data-ttu-id="469b7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="469b7-106">Event ID</span></span>     |                                                                 -                                                                  |
|  <span data-ttu-id="469b7-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="469b7-107">Event Source</span></span>   |                                                         <span data-ttu-id="469b7-108">EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="469b7-108">BizTalk Server EDI</span></span>                                                         |
|    <span data-ttu-id="469b7-109">Componente</span><span class="sxs-lookup"><span data-stu-id="469b7-109">Component</span></span>    |                                                             <span data-ttu-id="469b7-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="469b7-110">AS2 Engine</span></span>                                                             |
|  <span data-ttu-id="469b7-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="469b7-111">Symbolic Name</span></span>  |                                                                 -                                                                  |
|  <span data-ttu-id="469b7-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="469b7-112">Message Text</span></span>   | <span data-ttu-id="469b7-113">Error de BTS MIME al intentar descodificar un mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="469b7-113">A BTS MIME error was encountered when attempting to decode an AS2 message.</span></span>  <span data-ttu-id="469b7-114">AS2-de: {0}, AS2-a: {1}, MessageId: {2}, Error: {3}</span><span class="sxs-lookup"><span data-stu-id="469b7-114">AS2-From: {0}, AS2-To: {1}, MessageId: {2}, Error: {3}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="469b7-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="469b7-115">Explanation</span></span>  
 <span data-ttu-id="469b7-116">Este error aparece al usar el componente MIME de BizTalk para gestionar parte del procesamiento de MIME.</span><span class="sxs-lookup"><span data-stu-id="469b7-116">This error is encountered when using the BizTalk MIME component to handle part of the MIME processing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="469b7-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="469b7-117">User Action</span></span>  
 <span data-ttu-id="469b7-118">El mensaje de error completo proporciona la información sobre el problema detectado por el componente MIME.</span><span class="sxs-lookup"><span data-stu-id="469b7-118">The full error message provides the information about the problem encountered by the MIME component.</span></span> <span data-ttu-id="469b7-119">Consulte la información de error de BTS MIME para el diagnóstico del problema (Esto es porque los componentes de AS2 usan los componentes MIME de BizTalk para parte del procesamiento de MIME).</span><span class="sxs-lookup"><span data-stu-id="469b7-119">Refer to the BTS MIME error information for diagnosis of the problem (this is because the AS2 components use the BizTalk MIME components for part of the MIME processing).</span></span>