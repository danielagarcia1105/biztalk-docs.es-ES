---
title: La plantilla de mensaje de InfoPath | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bb055b1-8480-44dd-8739-f2981bca63c3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b8ec04d16da25f39060540aa8a8205421397d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-infopath-message-template"></a>La plantilla de mensaje de InfoPath
Como alternativa a la visualización de mensajes de error ESB en el Portal de administración de ESB, los usuarios pueden beneficiarse de una plantilla de mensaje de Microsoft InfoPath denominada el Visor de mensajes de excepción de ESB, proporcionará el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
 El marco de trabajo de administración de excepciones de ESB puede conservar los mensajes en un formato serializado que, junto con la plantilla del Visor de mensajes de excepción de ESB, mostrará varias vistas del mensaje de error y los mensajes originales que contiene. El Visor de mensajes de excepción de ESB proporciona las siguientes vistas:  
  
-   Vista General  
  
-   Vista de objetos de excepción  
  
-   vista Mensaje  
  
 Figura 1 muestra la vista General del Visor de mensajes de excepción de ESB, que muestra más propiedades de ambiente de la excepción.  
  
 ![Vista General de mensajes de excepción](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4-ExceptionMessageGeneralView")  
  
 **Figura 1**  
  
 **El Visor de mensajes de excepción de ESB que muestra la vista General**  
  
 La figura 2 muestra la vista de objeto de excepción, que muestra las propiedades y el seguimiento de pila de la **System.Exception** objeto.  
  
 ![Objeto de excepción de mensaje de excepción](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4-ExceptionMessageExceptionObject")  
  
 **Figura 2**  
  
 **El Visor de mensajes de excepción de ESB que muestra la vista de objeto de excepción**  
  
 La figura 3 muestra la vista de mensajes, que proporciona una lista de desplegable desde el que el usuario puede seleccionar desde mensajes persistentes disponibles. La vista muestra los valores de las propiedades de contexto del mensaje persistente y el contenido del mensaje XML.  
  
 ![Mensaje de excepción la vista mensajes](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4-ExceptionMessageMessagesView")  
  
 **Figura 3**  
  
 **El Visor de mensajes de excepción de ESB que muestra la vista mensajes**