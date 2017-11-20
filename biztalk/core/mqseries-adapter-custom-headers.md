---
title: Encabezados personalizados del adaptador de MQSeries | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MQSeries adapters, custom headers
ms.assetid: b0e18203-a33f-4d50-8483-396699cdff23
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09a05b8c73cd7be84af01eb4465681816e429bc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-custom-headers"></a><span data-ttu-id="d46a4-102">Encabezados personalizados del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="d46a4-102">MQSeries Adapter Custom Headers</span></span>
<span data-ttu-id="d46a4-103">Debido a las estructuras de encabezado utilizadas en mensajes MQSeries, debe administrar cualquier encabezado personalizado que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="d46a4-103">Because of the header structures used in MQSeries messages, you must manage any custom headers you want to use.</span></span> <span data-ttu-id="d46a4-104">Los encabezados personalizados deben ser parte del cuerpo de mensaje para evitar interferir entre el procesamiento de los encabezados de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="d46a4-104">Custom headers must be part of the message body to avoid interfering with the processing of the MQSeries headers.</span></span> <span data-ttu-id="d46a4-105">Asegúrese de evitar degradar cualquier propiedad promocionada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d46a4-105">Make sure that you avoid demoting any one of the automatically promoted properties.</span></span> <span data-ttu-id="d46a4-106">Para obtener más información acerca de las propiedades promocionadas automáticamente, consulte [propiedades del adaptador de MQSeries](../core/mqseries-adapter-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d46a4-106">For more information about automatically promoted properties, see [MQSeries Adapter Properties](../core/mqseries-adapter-properties.md).</span></span>  
  
 <span data-ttu-id="d46a4-107">A su vez, la integración de encabezados personalizados en el cuerpo del mensaje requiere un procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="d46a4-107">In turn, the incorporation of custom headers in the message body requires additional processing.</span></span> <span data-ttu-id="d46a4-108">Una solución es controlar los encabezados personalizados de las canalizaciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d46a4-108">One solution is to handle the custom headers in the pipelines of the application.</span></span> <span data-ttu-id="d46a4-109">Una canalización de recepción extrae la información de encabezado personalizado y promociona la información como propiedades de contexto.</span><span class="sxs-lookup"><span data-stu-id="d46a4-109">A receive pipeline extracts the custom header information and promotes the information as context properties.</span></span> <span data-ttu-id="d46a4-110">De forma similar, la canalización de envío toma las propiedades de contexto correspondientes al encabezado personalizado y degrada las propiedades en el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d46a4-110">Similarly, the send pipeline takes the context properties corresponding to the custom header and demotes the properties in the body of the message.</span></span>  
  
 <span data-ttu-id="d46a4-111">Para obtener un ejemplo del uso de encabezados personalizados en un componente de canalización, consulte [MQSSendPipelineComponent (ejemplo de BizTalk Server)](../core/mqssendpipelinecomponent-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d46a4-111">For an example of using custom headers in a pipeline component, see [MQSSendPipelineComponent (BizTalk Server Sample)](../core/mqssendpipelinecomponent-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46a4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d46a4-112">See Also</span></span>  
 [<span data-ttu-id="d46a4-113">Propiedades del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="d46a4-113">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)