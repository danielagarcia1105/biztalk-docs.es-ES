---
title: Ejecutar el ejemplo de componente JMS MQRFH2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44f4b48c-398a-4ec1-a033-1fc4a76a305c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fcea4bca324f73ee37b63e78673140eae250692
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294268"
---
# <a name="running-the-jms-mqrfh2-component-sample"></a>Ejecutar el ejemplo de componente JMS MQRFH2
El ejemplo de componente de JMS MQRFH2 consta de tres partes:  
  
-   [Ejecutar el ejemplo de conservación de JMS MQRFH2 encabezado](../esb-toolkit/running-the-jms-mqrfh2-header-preservation-sample.md). Esta parte muestra conservar el encabezado totalmente exactos de tránsito de un mensaje de IBM WebSphere MQ, a través de ESB y Microsoft BizTalk Server y de vuelta a IBM WebSphere MQ.  
  
-   [Ejecuta el acceso a la propiedad de encabezado de un ejemplo de orquestación](../esb-toolkit/running-the-header-property-access-from-an-orchestration-sample.md). Esta parte explica cómo el código dentro de una orquestación de ESB puede tener acceso a propiedades de encabezado de MQRFH2. En este caso, el código utiliza una propiedad de encabezado para especificar el nombre de la cola de destino.  
  
-   [Ejecuta la mayor parte cargar muestra de enrutamiento basado en contenido](../esb-toolkit/running-the-bulk-load-content-based-routing-sample.md). Esta parte muestra una cola con los mensajes de carga masiva, y se muestra cómo la aplicación enruta los mensajes a las colas de destino especificadas como parte del contenido del mensaje.