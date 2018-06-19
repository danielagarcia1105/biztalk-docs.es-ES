---
title: El componente de itinerarios de ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 379edc6a-7d53-4338-87a5-47b5238453a4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80aa7c1ef4bc53ad2e2821eaf8dc4184777900a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294972"
---
# <a name="the-esb-itinerary-component"></a><span data-ttu-id="7539c-102">El componente de itinerarios de ESB</span><span class="sxs-lookup"><span data-stu-id="7539c-102">The ESB Itinerary Component</span></span>
<span data-ttu-id="7539c-103">El componente de ESB itinerario establece las propiedades de contexto del encabezado SOAP que se envía junto con el mensaje a un ESB itinerario en rampa.</span><span class="sxs-lookup"><span data-stu-id="7539c-103">The ESB Itinerary component sets the context properties from the SOAP header sent along with the message to an ESB itinerary on-ramp.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="7539c-104">Installation</span><span class="sxs-lookup"><span data-stu-id="7539c-104">Installation</span></span>  
 <span data-ttu-id="7539c-105">Al instalar el núcleo de ESB automáticamente se instala el **itinerario** componente de canalización en la carpeta de componentes de canalización de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7539c-105">Installing the ESB Core automatically installs the **Itinerary** pipeline component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="7539c-106">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="7539c-106">How It Works</span></span>  
 <span data-ttu-id="7539c-107">El componente de ESB itinerario es un componente de canalización de BizTalk de Microsoft que sólo puede residir en una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="7539c-107">The ESB Itinerary component is a Microsoft BizTalk pipeline component that can reside only in a receive pipeline.</span></span> <span data-ttu-id="7539c-108">Promociona valores de encabezados de mensaje SOAP o de configuración del componente en el contexto del mensaje como propiedades.</span><span class="sxs-lookup"><span data-stu-id="7539c-108">It promotes values from either SOAP message headers or component settings into the message context as properties.</span></span> <span data-ttu-id="7539c-109">Puede encontrar un ejemplo de promoción de encabezados SOAP en los servicios Web de itinerario en rampa proporcionados con [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7539c-109">You can find an example of promoting SOAP headers in the Itinerary On-Ramp Web services provided with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="7539c-110">Estos servicios Web que exponen los encabezados SOAP como parte de sus contratos y las aplicaciones cliente deben establecer los encabezados.</span><span class="sxs-lookup"><span data-stu-id="7539c-110">These Web services expose SOAP headers as part of their contracts, and client applications must set the headers.</span></span> <span data-ttu-id="7539c-111">A medida que el mensaje pasa a través del componente en una canalización de recepción, el componente lee el encabezado SOAP valores y promociona (escrituras) a las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="7539c-111">As the message passes through the component in a receive pipeline, the component reads the SOAP header values and promotes (writes) them to the message context properties.</span></span>  
  
## <a name="using-the-esb-itinerary-component"></a><span data-ttu-id="7539c-112">Mediante el componente de itinerarios de ESB</span><span class="sxs-lookup"><span data-stu-id="7539c-112">Using the ESB Itinerary Component</span></span>  
 <span data-ttu-id="7539c-113">Puede agregar el componente de ESB itinerario a una canalización de recepción y, a continuación, usar la canalización en una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="7539c-113">You can add the ESB Itinerary component to a receive pipeline and then use the pipeline in a receive location.</span></span> <span data-ttu-id="7539c-114">El componente promociona automáticamente los valores del encabezado SOAP o la configuración del componente en las propiedades de contexto del mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="7539c-114">The component automatically promotes SOAP header values or component settings into the context properties of the incoming message.</span></span>  
  
 <span data-ttu-id="7539c-115">Para obtener un ejemplo de cómo usar este componente, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7539c-115">For an example of how to use this component, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>