---
title: Conservación de encabezados JMS al enrutar a través de una orquestación | Microsoft Docs
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
ms.openlocfilehash: 142bd0d2e5ff86362fe3c3ffa7ef8ec256202708
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979717"
---
# <a name="preserving-jms-headers-when-routing-through-an-orchestration"></a>Conservación de encabezados JMS al enrutar a través de una orquestación
En este caso de uso, los componentes proporcionados con [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extraer los encabezados de Java Message Service (JMS) de un mensaje entrante y, a continuación, los reconstruye en el mensaje saliente. Esto demuestra la conservación de encabezado de mensaje JMS y acceso al contexto de encabezado desde dentro de una orquestación, tal como se muestra en la figura 1.  
  
 ![Conservación de JMS](../esb-toolkit/media/ch3-preservingjms.gif "Ch3-PreservingJMS")  
  
 **Figura 1**  
  
 **Conservación de la información de encabezado JMS a lo largo de una orquestación de ESB y procesamiento**  
  
 El ejemplo de componente MQRFH2 de JMS incluido con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso y consta de las siguientes tres partes:  
  
- Parte 1 muestra cómo conservar el encabezado de fidelidad total tránsito de un mensaje de IBM WebSphere MQ, a través de ESB y BizTalk Server y de vuelta a IBM WebSphere MQ.  
  
- Parte 2 muestra cómo puede tener acceso a las propiedades de encabezado MQRFH2 código en una orquestación de ESB. En este caso, el código modifica una propiedad de encabezado JMS para especificar el nombre de la cola de destino.  
  
- Parte 3 muestra una cola con mensajes de carga masiva y muestra cómo la aplicación enruta los mensajes a las colas de destino especificadas como parte del contenido del mensaje.  
  
  Para obtener más información, consulte [instalar y ejecutar el ejemplo de componente MQRFH2 de JMS](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md).