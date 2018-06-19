---
title: Ejecutar el ejemplo de conservación de JMS MQRFH2 encabezado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65982dca-77e1-4267-9528-26c59237e9b1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab840ed1d319f8fd50d3a386e0ffc9b349f61b9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295132"
---
# <a name="running-the-jms-mqrfh2-header-preservation-sample"></a>Ejecutar el ejemplo de conservación de JMS MQRFH2 encabezado
Esta parte de este ejemplo coloca un mensaje en una cola de WebSphere. ESB toma este mensaje y coloca en una cola de salida de WebSphere. Esto demuestra que el ESB y Microsoft BizTalk conservan encabezados de RFH2 plena fidelidad como un mensaje se transmite a través de BizTalk Server.  
  
 **Para ejecutar el ejemplo de conservación de encabezado**  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.  
  
2.  Ejecute la utilidad de IBM RfhUtil y, a continuación, seleccione el Administrador de cola denominado ESB. JMS. Sample.QueueManager en la primera lista desplegable para conectarse a este administrador de cola.  
  
3.  En la segunda lista desplegable, seleccione la cola de salida de destino denominada ESB. JMS. EJEMPLO. SENDTOBIZTALK, tal como se muestra en la figura 1.  
  
     ![Administrador de cola](../esb-toolkit/media/ch6-queuemanager.gif "Ch6-QueueManager")  
  
     **Figura 1**  
  
     **Conectar con el Administrador de cola y la cola de salida en RfhUtil**  
  
4.  Si la lista desplegable no contiene ninguna cola, asegúrese de que el Administrador de cola se ejecuta mediante la comprobación del elemento de WebSphere MQ servicios, como se muestra en la figura 2.  
  
     ![Web esfera](../esb-toolkit/media/ch6-websphere.gif "Ch6-WebSphere")  
  
     **Figura 2**  
  
     **Comprobación de que el Administrador de cola se está ejecutando en el elemento de servicios de WebSphere**  
  
5.  Haga clic en el **ReadFile** situado en la utilidad RfhUtil y navegue hasta el archivo de mensaje de prueba denominado 000128 de prueba. JMS ubicado en la subcarpeta denominada \Source\Samples\JMS\Test\Data\Load\\. Este archivo contiene un lote de mensajes de prueba 128, pero la utilidad carga solo la primera de ellas.  
  
6.  Haga clic en el **RFH** ficha y, a continuación, asegúrese de que sólo el **JMS** casilla está activada.  
  
7.  Haga clic en el **jms** ficha y, a continuación, asegúrese de que el seleccionado **responder a** cola es ESB. JMS. EJEMPLO. DYNAMICQ1 y que el seleccionado **cola de destino** es ESB. JMS. EJEMPLO. DYNAMICQ2.  
  
8.  Haga clic en el **Main** ficha y, a continuación, haga clic en el **escribir preguntas** botón para escribir el mensaje en la cola.  
  
9. Después de un retraso mientras se ejecuta la aplicación, aparece el mensaje de salida ESB en ESB. JMS. EJEMPLO. DYNAMICQ1 y ESB. JMS. EJEMPLO. Colas de DYNAMICQ1. Abra el Explorador de la cola de WebSphere y examinar las colas para confirmarlo.  
  
10. Vuelva a la utilidad RfhUtil y conectarse a las colas para ver los mensajes. Haga clic en el **MQMD, RFH,** y **jms** excepción en las pestañas para comprobar que los valores de entrada y salidos se ha modificado para el mensaje en la cola de destino y que el mensaje en la cola de respuesta es el mismo que, en lugar de un mensaje JMS estándar, el mensaje se marca como "Sí".