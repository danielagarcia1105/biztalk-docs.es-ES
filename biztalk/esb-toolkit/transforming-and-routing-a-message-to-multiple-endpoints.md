---
title: "Transformar y enrutar un mensaje a varios puntos de conexión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 544db12c-95fc-4321-b397-ec9e7410e37d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99e30c2d7b095d0b075b98a48f9263abd361b6cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a>Transformar y enrutar un mensaje a varios puntos de conexión
En este caso de uso, ESB realiza una transformación en un mensaje enviado a través del servicio Web de itinerario en rampa. Una búsqueda de resolución dinámica determina el nombre de asignación y transforma el mensaje entrante. Además, el itinerario especifica n número de puntos de conexión de destino que el servicio de itinerario resolverá dinámicamente y a la que enrutará el mensaje transformado. Todas las operaciones se producen en la capa de mensajería, como se muestra en la figura 1.  
  
 ![Transformación de múltiples extremos](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3-TransformingMultipleEndpoints")  
  
 **Figura 1**  
  
 **Transformar y enrutar un mensaje a varios puntos de conexión**  
  
 El ejemplo de resolución dinámica que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Muestra cómo utilizar componentes de canalización ESB, específicamente el componente de desensamblador de envío de ESB, para resolver la ubicación del extremo dinámicamente, establecer las propiedades de enrutamientos y resolver y ejecutar [!INCLUDE[prague](../includes/prague-md.md)] se asigna en el nivel de mensajería, sin usar un orquestación. También muestra los patrones de mensajería unidireccionales y bidireccionales.  
  
 Para obtener más información, consulte [instalar y ejecutar el ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) y [instalar y ejecutar el ejemplo de servicios Web varios](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).