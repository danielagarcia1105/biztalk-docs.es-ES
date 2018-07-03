---
title: La plantilla de mensaje de InfoPath | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb055b1-8480-44dd-8739-f2981bca63c3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c929e8ef1edcd88c0976d145354779b3e095634
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024474"
---
# <a name="the-infopath-message-template"></a>La plantilla de mensaje de InfoPath
Como alternativa a la visualización de los mensajes de error ESB en el Portal de administración de ESB, los usuarios pueden aprovechar una plantilla de mensaje de Microsoft InfoPath denominada el Visor de mensajes de excepción de ESB proporcionado con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
 El marco de administración de excepciones de ESB puede conservar los mensajes en un formato serializado que, junto con la plantilla de Visor de mensajes de excepción de ESB mostrará varias vistas del mensaje de error y los mensajes originales que contiene. El Visor de mensajes de excepción de ESB proporciona las siguientes vistas:  
  
- Vista General  
  
- Vista de objeto de excepción  
  
- vista Mensaje  
  
  Figura 1 muestra la vista General del Visor de mensaje de excepción de ESB, que muestra más propiedades de ambiente de la excepción.  
  
  ![Vista General de mensajes de excepción](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4-ExceptionMessageGeneralView")  
  
  **Figura 1**  
  
  **El Visor de mensajes de excepción de ESB que muestra la vista General**  
  
  La figura 2 muestra la vista del objeto de excepción, que muestra las propiedades y el seguimiento de pila de la **System.Exception** objeto.  
  
  ![Objeto de excepción del mensaje de excepción](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4-ExceptionMessageExceptionObject")  
  
  **Figura 2**  
  
  **El Visor de mensajes de excepción de ESB que muestra la vista del objeto de excepción**  
  
  Figura 3 se muestra la vista de mensajes, que proporciona una lista desplegable desde el que el usuario puede seleccionar desde mensajes conservados disponibles. La vista muestra los valores de las propiedades de contexto del mensaje persistente y el contenido del mensaje XML.  
  
  ![Mensaje de excepción la vista mensajes](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4-ExceptionMessageMessagesView")  
  
  **Figura 3**  
  
  **El Visor de mensajes de excepción de ESB que muestra la vista mensajes**