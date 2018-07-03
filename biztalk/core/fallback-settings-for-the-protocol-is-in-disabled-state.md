---
title: Configuración de reserva para el protocolo está en estado deshabilitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f14a5e46-1028-4250-af7b-8137fa927d7e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1661aed16d2a63b158f3e1ae886b7dde381da14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983445"
---
# <a name="fallback-settings-for-the-protocol-is-in-disabled-state"></a><span data-ttu-id="65d8d-102">La configuración de reserva para el protocolo tiene el estado Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="65d8d-102">Fallback Settings for the Protocol is in Disabled state</span></span>
## <a name="details"></a><span data-ttu-id="65d8d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="65d8d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="65d8d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="65d8d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="65d8d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="65d8d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="65d8d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="65d8d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="65d8d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="65d8d-107">Event Source</span></span>   | <span data-ttu-id="65d8d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65d8d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="65d8d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="65d8d-109">Component</span></span>    |                                       <span data-ttu-id="65d8d-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="65d8d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="65d8d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="65d8d-111">Symbolic Name</span></span>  |                      <span data-ttu-id="65d8d-112">AgreementResolutionFallbackSettingsDisabled</span><span class="sxs-lookup"><span data-stu-id="65d8d-112">AgreementResolutionFallbackSettingsDisabled</span></span>                       |
|  <span data-ttu-id="65d8d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="65d8d-113">Message Text</span></span>   |              <span data-ttu-id="65d8d-114">Configuración de reserva para el {0} protocolo está en estado deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="65d8d-114">Fallback Settings for the {0} Protocol is in Disabled state.</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="65d8d-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="65d8d-115">Explanation</span></span>  
 <span data-ttu-id="65d8d-116">Este evento de error, advertencia o información indica que BizTalk Server pudo resolver en un acuerdo y que se ha redireccionado a la configuración de reserva y se ha encontrado que ésta estaba en el estado deshabilitado para el protocolo en particular.</span><span class="sxs-lookup"><span data-stu-id="65d8d-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement and has been redirected to Fallback settings and found that the fallback settings were in disabled state for the particular protocol.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="65d8d-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="65d8d-117">User Action</span></span>  
 <span data-ttu-id="65d8d-118">Para resolver este error, habilite a la configuración de reserva para el protocolo en particular.</span><span class="sxs-lookup"><span data-stu-id="65d8d-118">To resolve this error, please enable the fallback settings for the particular protocol.</span></span>