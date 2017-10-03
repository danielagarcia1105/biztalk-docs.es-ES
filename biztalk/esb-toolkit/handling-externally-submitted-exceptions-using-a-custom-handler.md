---
title: Control externamente enviado excepciones mediante un controlador personalizado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53fa661e-d391-47c0-92d5-1d0c45b5963d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ba3fc49756619f77188f0a311ff46eb18e7f0b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-externally-submitted-exceptions-using-a-custom-handler"></a>Control externamente enviado excepciones mediante un controlador personalizado
En este caso de uso, un cliente externo envía un mensaje de excepción a través de un servicio Web. Un puerto de envío configurado previamente con el componente de canalización de codificador de excepción de ESB, se suscribe al mensaje de error; procesa y lo almacena como un archivo de disco que se puede ver con Microsoft InfoPath, tal como se muestra en la figura 1.  
  
 ![Tratamiento de excepciones externas](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3-HandlingExternalExceptions")  
  
 **Figura 1**  
  
 **Controlar los mensajes entrantes de excepción o error y almacenarla en un archivo de disco**  
  
 El ejemplo de servicio de control de excepciones incluido con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Muestra cómo utilizar el servicio de la excepción de ESB como un mecanismo universal para enviar mensajes de error de las aplicaciones externas que se almacenará en la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] base de datos de administración de excepciones. Para obtener más información, consulte [ejecutar el ejemplo de servicio de control de excepciones](../esb-toolkit/running-the-exception-handling-service-sample.md).