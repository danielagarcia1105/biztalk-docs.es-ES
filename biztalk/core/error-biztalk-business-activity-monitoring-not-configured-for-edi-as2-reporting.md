---
title: "Supervisión de la actividad de negocio de BizTalk no se ha configurado para la generación de informes de estado de EDI AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f46c1c8-2771-4b16-8fb1-71952792ac4a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e84301e55cd6fbdcb74467758c7e338e61b727f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-business-activity-monitoring-has-not-been-configured-for-edi-as2-status-reporting"></a><span data-ttu-id="5723b-102">Supervisión de la actividad de negocio de BizTalk no se ha configurado para la generación de informes de estado de AS2 de EDI</span><span class="sxs-lookup"><span data-stu-id="5723b-102">BizTalk Business Activity Monitoring has not been configured for EDI-AS2 status reporting</span></span>
## <a name="details"></a><span data-ttu-id="5723b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5723b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5723b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5723b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5723b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5723b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5723b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5723b-106">Event ID</span></span>|-|  
|<span data-ttu-id="5723b-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5723b-107">Event Source</span></span>|<span data-ttu-id="5723b-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5723b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="5723b-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5723b-109">Component</span></span>|<span data-ttu-id="5723b-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="5723b-110">AS2 Engine</span></span>|  
|<span data-ttu-id="5723b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5723b-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="5723b-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5723b-112">Message Text</span></span>|<span data-ttu-id="5723b-113">Supervisión de la actividad económica (BAM) no se ha configurado para la generación de informes de estado de EDI/AS2.</span><span class="sxs-lookup"><span data-stu-id="5723b-113">BizTalk Business Activity Monitoring has not been configured for EDI/AS2 status reporting.</span></span> <span data-ttu-id="5723b-114">La característica de informes de estado se deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="5723b-114">Hence status reporting feature will be disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5723b-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="5723b-115">Explanation</span></span>  
 <span data-ttu-id="5723b-116">Este evento de error,  indica que no se habilitó la generación de informes de estado de EDI/AS2 porque Supervisión de la actividad económica (BAM) no se ha configurado a través del Asistente para configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5723b-116">This Error/Warning/Information event indicates that EDI/AS2 status reporting is not enabled because Business Activity Monitoring (BAM) has not been configured through the BizTalk Configuration Wizard.</span></span> <span data-ttu-id="5723b-117">La infraestructura de BAM es un requisito previo para la generación de informes de estado de EDI/AS2.</span><span class="sxs-lookup"><span data-stu-id="5723b-117">The BAM infrastructure is a prerequisite for EDI/AS2 status reporting.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5723b-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5723b-118">User Action</span></span>  
 <span data-ttu-id="5723b-119">Para resolver este error, ejecute el Asistente para configuración de BizTalk y configure Supervisión de la actividad económica.</span><span class="sxs-lookup"><span data-stu-id="5723b-119">To resolve this error, run the BizTalk Configuration Wizard and configure Business Activity Monitoring.</span></span>