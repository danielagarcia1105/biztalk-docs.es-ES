---
title: El descodificador AS2 no pudo localizar el encabezado HTTP Disposition-Notification-Options | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6de4b9a6-17b2-4455-9dbd-a6bb69fac1d5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966860c7f2b7b47187b861ed6b81fb14a4753872
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240020"
---
# <a name="the-as2-decoder-was-unable-to-locate-the-disposition-notification-options-http-header"></a><span data-ttu-id="f292c-102">El descodificador AS2 no ha podido localizar el encabezado HTTP Disposition-Notification-Options</span><span class="sxs-lookup"><span data-stu-id="f292c-102">The AS2 Decoder was unable to locate the Disposition-Notification-Options HTTP header</span></span>
## <a name="details"></a><span data-ttu-id="f292c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f292c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f292c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f292c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f292c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f292c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f292c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f292c-106">Event ID</span></span>|-|  
|<span data-ttu-id="f292c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f292c-107">Event Source</span></span>|<span data-ttu-id="f292c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f292c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="f292c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f292c-109">Component</span></span>|<span data-ttu-id="f292c-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="f292c-110">AS2 Engine</span></span>|  
|<span data-ttu-id="f292c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f292c-111">Symbolic Name</span></span>|<span data-ttu-id="f292c-112">AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError</span><span class="sxs-lookup"><span data-stu-id="f292c-112">AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError</span></span>|  
|<span data-ttu-id="f292c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f292c-113">Message Text</span></span>|<span data-ttu-id="f292c-114">El descodificador AS2 no ha podido localizar el encabezado HTTP Disposition-Notification-Options necesario para la generación de MDN.</span><span class="sxs-lookup"><span data-stu-id="f292c-114">The AS2 Decoder was unable to locate the Disposition-Notification-Options HTTP header which is required for MDN generation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f292c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f292c-115">Explanation</span></span>  
 <span data-ttu-id="f292c-116">Este evento de error,  indica que la canalización de recepción no pudo generar el MDN porque el mensaje AS2 de entrada no incluyó el encabezado Disposition-Notification-Options que indica si el MDN debe firmarse o no y qué algoritmo MIC debe usarse.</span><span class="sxs-lookup"><span data-stu-id="f292c-116">This Error/Warning/Information event indicates that the receive pipeline could not generate the MDN because the incoming AS2 message did not include the Disposition-Notification-Options header that indicates whether the MDN must be signed and which MIC algorithm must be used.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f292c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f292c-117">User Action</span></span>  
 <span data-ttu-id="f292c-118">Para resolver este error, pida al remitente del mensaje AS2 que incluya el encabezado Disposition-Notification-Options en el mensaje y, a continuación, vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f292c-118">To resolve this error, have the sender of the AS2 message include the Disposition-Notification-Options header in the message and then resend the message.</span></span>