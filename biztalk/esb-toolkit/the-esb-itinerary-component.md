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
# <a name="the-esb-itinerary-component"></a>El componente de itinerarios de ESB
El componente de ESB itinerario establece las propiedades de contexto del encabezado SOAP que se envía junto con el mensaje a un ESB itinerario en rampa.  
  
## <a name="installation"></a>Installation  
 Al instalar el núcleo de ESB automáticamente se instala el **itinerario** componente de canalización en la carpeta de componentes de canalización de BizTalk Server.  
  
## <a name="how-it-works"></a>Funcionamiento  
 El componente de ESB itinerario es un componente de canalización de BizTalk de Microsoft que sólo puede residir en una canalización de recepción. Promociona valores de encabezados de mensaje SOAP o de configuración del componente en el contexto del mensaje como propiedades. Puede encontrar un ejemplo de promoción de encabezados SOAP en los servicios Web de itinerario en rampa proporcionados con [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. Estos servicios Web que exponen los encabezados SOAP como parte de sus contratos y las aplicaciones cliente deben establecer los encabezados. A medida que el mensaje pasa a través del componente en una canalización de recepción, el componente lee el encabezado SOAP valores y promociona (escrituras) a las propiedades de contexto de mensaje.  
  
## <a name="using-the-esb-itinerary-component"></a>Mediante el componente de itinerarios de ESB  
 Puede agregar el componente de ESB itinerario a una canalización de recepción y, a continuación, usar la canalización en una ubicación de recepción. El componente promociona automáticamente los valores del encabezado SOAP o la configuración del componente en las propiedades de contexto del mensaje entrante.  
  
 Para obtener un ejemplo de cómo usar este componente, consulte [instalar y ejecutar el ejemplo de itinerario en rampa](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).