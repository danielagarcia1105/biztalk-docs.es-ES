---
title: Resolución de punto a punto de puntos de conexión y los requisitos de transformación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4c570bf-8274-4779-ae83-2aef2bf57ded
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8899c5f713f1c9ebfe299d3e431754dd8b9794d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294468"
---
# <a name="point-to-point-resolution-of-endpoints-and-transformation-requirements"></a>Resolución de punto a punto de puntos de conexión y los requisitos de transformación
En este caso de uso, un cliente del servicio Web llama a un servicio Web sin tener que pasar a través de ESB. Los dos puntos se comunican directamente, pero antes de que el cliente realiza la llamada, que debe resolver el extremo del servicio Web. La llamada al servicio Web puede ser un unidireccional o solicitud-respuesta. Una manera de conseguirlo es usar las características de resolución dinámica de ESB, tal como se muestra en la figura 1.  
  
 ![Punto de &#45; a &#45; Punto de resolución de extremos](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3-PointToPoint")  
  
 **Figura 1**  
  
 **Resolver los extremos que usan UDDI**  
  
 El ejemplo de servicio de la resolución que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. El ejemplo muestra cómo llamar al servicio de resolución de ESB para llevar a cabo la resolución, lo que permite probar la resolución mientras se desarrolla el contenido de los almacenes de back-end, como Universal Description, Discovery y Integration (UDDI), XML Path Language (XPath) Estáticos o directivas en el motor de reglas de negocio de BizTalk Server.  
  
 Para obtener más información, consulte [instalar y ejecutar el ejemplo de servicio de resolución](../esb-toolkit/installing-and-running-the-resolver-service-sample.md).