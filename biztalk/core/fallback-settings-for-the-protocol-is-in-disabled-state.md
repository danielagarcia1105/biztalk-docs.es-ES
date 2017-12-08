---
title: "Configuración de reserva para el protocolo está en estado deshabilitado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f14a5e46-1028-4250-af7b-8137fa927d7e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9060dbe2bf3644310d862d4949d2cf944269105d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fallback-settings-for-the-protocol-is-in-disabled-state"></a><span data-ttu-id="16133-102">La configuración de reserva para el protocolo tiene el estado Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="16133-102">Fallback Settings for the Protocol is in Disabled state</span></span>
## <a name="details"></a><span data-ttu-id="16133-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="16133-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16133-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="16133-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="16133-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="16133-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="16133-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="16133-106">Event ID</span></span>|-|  
|<span data-ttu-id="16133-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="16133-107">Event Source</span></span>|<span data-ttu-id="16133-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16133-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="16133-109">Componente</span><span class="sxs-lookup"><span data-stu-id="16133-109">Component</span></span>|<span data-ttu-id="16133-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="16133-110">EDI Engine</span></span>|  
|<span data-ttu-id="16133-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="16133-111">Symbolic Name</span></span>|<span data-ttu-id="16133-112">AgreementResolutionFallbackSettingsDisabled</span><span class="sxs-lookup"><span data-stu-id="16133-112">AgreementResolutionFallbackSettingsDisabled</span></span>|  
|<span data-ttu-id="16133-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="16133-113">Message Text</span></span>|<span data-ttu-id="16133-114">La configuración de reserva para el protocolo {0} tiene el estado Deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="16133-114">Fallback Settings for the {0} Protocol is in Disabled state.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="16133-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="16133-115">Explanation</span></span>  
 <span data-ttu-id="16133-116">Este evento de error, advertencia o información indica que BizTalk Server pudo resolver en un acuerdo y que se ha redireccionado a la configuración de reserva y se ha encontrado que ésta estaba en el estado deshabilitado para el protocolo en particular.</span><span class="sxs-lookup"><span data-stu-id="16133-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement and has been redirected to Fallback settings and found that the fallback settings were in disabled state for the particular protocol.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16133-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="16133-117">User Action</span></span>  
 <span data-ttu-id="16133-118">Para resolver este error, habilite a la configuración de reserva para el protocolo en particular.</span><span class="sxs-lookup"><span data-stu-id="16133-118">To resolve this error, please enable the fallback settings for the particular protocol.</span></span>