---
title: "Recopilar excepciones y enrutamiento de mensajes para la reparación y vuelva a intentarlo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a61658a-0bac-4802-b506-02e61a3d2a9b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6a9123526dd35f788c86a610ee51ed8e90c1bc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="collecting-exceptions-and-routing-messages-for-repair-and-resubmit"></a>Recopilar excepciones y enrutamiento de mensajes para la reparación y vuelva a intentarlo
En este caso de uso, un controlador de excepciones personalizado recoge un mensaje de error recibido a través de un servicio Web y los enruta a un archivo de disco en un formato compatible con una plantilla de InfoPath que se incluye con la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. El usuario puede abrir el archivo con Microsoft InfoPath, editar el contenido del mensaje y vuelva a enviar el mensaje para el procesamiento, como se muestra en la figura 1.  
  
 ![Recopilar reparación de excepciones](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3-CollectingExceptionsRepair")  
  
 **Figura 1**  
  
 **Enrutamiento de un mensaje para su reparación y reenvío**  
  
 El ejemplo de reparación y volver a enviar controlador de excepciones personalizado que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Cuando un proceso en una orquestación detecta un error, el controlador de excepciones en cuanto orquestación genera y publica un mensaje de error ESB. Este mensaje de error incluye, en su carga, los mensajes (incluidos sus propiedades de contexto que están relacionados con [!INCLUDE[prague](../includes/prague-md.md)]) que estaban "en proceso" cuando se produjo la excepción y la excepción actual detectada por el motor de orquestaciones de BizTalk. Cuando se publica un mensaje de error ESB, se anulará en cola para una orquestación de suscripción (un controlador de excepciones personalizado) que extrae e inspecciona los mensajes en curso y el objeto de excepción del sistema y enruta los mensajes en curso en una carpeta de archivos, desde el que un usuario puede editar el mensaje mediante InfoPath y reenviarlo a BizTalk Server para su procesamiento.  
  
 Para obtener más información, consulte [ejecuta la reparación y volver a enviar ejemplo del controlador de excepción personalizada](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md).