---
title: Conservar encabezados JMS al enrutar a través de una orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9a59ff3-0cbf-499f-92b2-cf5b808d8b3f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362f41919a050b08bdba9c70c7771698ab71ce33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294676"
---
# <a name="preserving-jms-headers-when-routing-through-an-orchestration"></a>Conservar encabezados JMS al enrutar a través de una orquestación
En este caso de uso, se proporcionan con componentes [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extraer encabezados de Java Message Service (JMS) de un mensaje entrante y, a continuación, los reconstruye en el mensaje saliente. Esto demuestra la conservación de encabezado de mensaje JMS y acceso al contexto de encabezado desde dentro de una orquestación, tal como se muestra en la figura 1.  
  
 ![Conservación de JMS](../esb-toolkit/media/ch3-preservingjms.gif "Ch3-PreservingJMS")  
  
 **Figura 1**  
  
 **Cómo conservar información de encabezado JMS a lo largo de una orquestación de ESB y procesamiento**  
  
 El ejemplo de componente de JMS MQRFH2 que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso y consta de las tres partes siguientes:  
  
-   Parte 1 explica conservar el encabezado de plena fidelidad tránsito de un mensaje de IBM WebSphere MQ, a través de ESB y BizTalk Server y de vuelta a IBM WebSphere MQ.  
  
-   Parte 2 muestra cómo el código en una orquestación de ESB puede tener acceso a propiedades de encabezado de MQRFH2. En este caso, el código modifica una propiedad de encabezado JMS para especificar el nombre de la cola de destino.  
  
-   Parte 3 muestra una cola con los mensajes de carga masiva y cómo la aplicación enruta los mensajes a las colas de destino especificadas como parte del contenido del mensaje.  
  
 Para obtener más información, consulte [instalar y ejecutar el ejemplo de componente de JMS MQRFH2](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md).