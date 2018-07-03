---
title: Configuración de reserva para el protocolo no encontrado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d93e5db1-16a3-4796-8fa2-fef934508034
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13d703e9cd82dde0dc0da55a630f69f1b42903e4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993125"
---
# <a name="fallback-settings-for-the-protocol-not-found"></a><span data-ttu-id="89e88-102">No se encuentra la configuración de reserva para el protocolo</span><span class="sxs-lookup"><span data-stu-id="89e88-102">Fallback Settings for the Protocol not found</span></span>
## <a name="details"></a><span data-ttu-id="89e88-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="89e88-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="89e88-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="89e88-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="89e88-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="89e88-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="89e88-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="89e88-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="89e88-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="89e88-107">Event Source</span></span>   | <span data-ttu-id="89e88-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e88-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="89e88-109">Componente</span><span class="sxs-lookup"><span data-stu-id="89e88-109">Component</span></span>    |                                       <span data-ttu-id="89e88-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="89e88-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="89e88-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="89e88-111">Symbolic Name</span></span>  |                      <span data-ttu-id="89e88-112">AgreementResolutionFallbackSettingsNotFound</span><span class="sxs-lookup"><span data-stu-id="89e88-112">AgreementResolutionFallbackSettingsNotFound</span></span>                       |
|  <span data-ttu-id="89e88-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="89e88-113">Message Text</span></span>   |                   <span data-ttu-id="89e88-114">Configuración de reserva para el {0} protocolo no encontrado.</span><span class="sxs-lookup"><span data-stu-id="89e88-114">Fallback Settings for the {0} Protocol not found.</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="89e88-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="89e88-115">Explanation</span></span>  
 <span data-ttu-id="89e88-116">Este evento de error,  indica que BizTalk Server pudo resolver en un acuerdo y que se ha redireccionado a la configuración de reserva y se ha encontrado que ésta no se encontraba allí para el protocolo en particular.</span><span class="sxs-lookup"><span data-stu-id="89e88-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement and has been redirected to Fallback settings and found that the fallback settings were not there for the particular protocol.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="89e88-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="89e88-117">User Action</span></span>  
 <span data-ttu-id="89e88-118">Para resolver este error, configure la configuración de reserva para el protocolo en particular.</span><span class="sxs-lookup"><span data-stu-id="89e88-118">To resolve this error, please configure the fallback settings for the particular protocol.</span></span>