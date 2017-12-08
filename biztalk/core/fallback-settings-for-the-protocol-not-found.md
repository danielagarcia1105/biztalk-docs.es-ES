---
title: "Configuración de reserva para el protocolo no se encontró | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d93e5db1-16a3-4796-8fa2-fef934508034
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5b3f8ea35f4f29859f5156ff254137ea7a8f8db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fallback-settings-for-the-protocol-not-found"></a><span data-ttu-id="23983-102">No se encuentra la configuración de reserva para el protocolo</span><span class="sxs-lookup"><span data-stu-id="23983-102">Fallback Settings for the Protocol not found</span></span>
## <a name="details"></a><span data-ttu-id="23983-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="23983-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23983-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="23983-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="23983-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="23983-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="23983-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="23983-106">Event ID</span></span>|-|  
|<span data-ttu-id="23983-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="23983-107">Event Source</span></span>|<span data-ttu-id="23983-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23983-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="23983-109">Componente</span><span class="sxs-lookup"><span data-stu-id="23983-109">Component</span></span>|<span data-ttu-id="23983-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="23983-110">EDI Engine</span></span>|  
|<span data-ttu-id="23983-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="23983-111">Symbolic Name</span></span>|<span data-ttu-id="23983-112">AgreementResolutionFallbackSettingsNotFound</span><span class="sxs-lookup"><span data-stu-id="23983-112">AgreementResolutionFallbackSettingsNotFound</span></span>|  
|<span data-ttu-id="23983-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="23983-113">Message Text</span></span>|<span data-ttu-id="23983-114">No se encuentra la configuración de reserva para el protocolo {0}.</span><span class="sxs-lookup"><span data-stu-id="23983-114">Fallback Settings for the {0} Protocol not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="23983-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="23983-115">Explanation</span></span>  
 <span data-ttu-id="23983-116">Este evento de error,  indica que BizTalk Server pudo resolver en un acuerdo y que se ha redireccionado a la configuración de reserva y se ha encontrado que ésta no se encontraba allí para el protocolo en particular.</span><span class="sxs-lookup"><span data-stu-id="23983-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement and has been redirected to Fallback settings and found that the fallback settings were not there for the particular protocol.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="23983-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="23983-117">User Action</span></span>  
 <span data-ttu-id="23983-118">Para resolver este error, configure la configuración de reserva para el protocolo en particular.</span><span class="sxs-lookup"><span data-stu-id="23983-118">To resolve this error, please configure the fallback settings for the particular protocol.</span></span>