---
title: Encabezados personalizados del adaptador de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, custom headers
ms.assetid: b0e18203-a33f-4d50-8483-396699cdff23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09a05b8c73cd7be84af01eb4465681816e429bc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263092"
---
# <a name="mqseries-adapter-custom-headers"></a>Encabezados personalizados del adaptador de MQSeries
Debido a las estructuras de encabezado utilizadas en mensajes MQSeries, debe administrar cualquier encabezado personalizado que desee utilizar. Los encabezados personalizados deben ser parte del cuerpo de mensaje para evitar interferir entre el procesamiento de los encabezados de MQSeries. Asegúrese de evitar degradar cualquier propiedad promocionada automáticamente. Para obtener más información acerca de las propiedades promocionadas automáticamente, consulte [propiedades del adaptador de MQSeries](../core/mqseries-adapter-properties.md).  
  
 A su vez, la integración de encabezados personalizados en el cuerpo del mensaje requiere un procesamiento adicional. Una solución es controlar los encabezados personalizados de las canalizaciones de la aplicación. Una canalización de recepción extrae la información de encabezado personalizado y promociona la información como propiedades de contexto. De forma similar, la canalización de envío toma las propiedades de contexto correspondientes al encabezado personalizado y degrada las propiedades en el cuerpo del mensaje.  
  
 Para obtener un ejemplo del uso de encabezados personalizados en un componente de canalización, consulte [MQSSendPipelineComponent (ejemplo de BizTalk Server)](../core/mqssendpipelinecomponent-biztalk-server-sample.md).  
  
## <a name="see-also"></a>Vea también  
 [Propiedades del adaptador de MQSeries](../core/mqseries-adapter-properties.md)