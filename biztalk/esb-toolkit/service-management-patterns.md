---
title: "Patrones de la administración del servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fea915c-0074-472e-909b-fbbd88d7359c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a48639fb2a540b5b2597b34ad95ee390b4382c34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="service-management-patterns"></a>Patrones de la administración de servicio
## <a name="repair-and-resubmit"></a>Reparación y vuelva a intentarlo  
 El patrón de reparación y vuelva a intentarlo define una solución en la que un servicio no puede procesar un mensaje y debe correctamente externalizar su estado en el formulario del mensaje con errores, habilitar el contenido del mensaje que esté disponible para reparar y, a continuación, volver a enviarla a un servicio Para continuar procesando el mensaje.  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]incluye mecanismos por qué Microsoft BizTalk excepciones de mensajería y orquestación pueden normalizar y se expone para ninguna acción adicional. Al diseñar una solución ESB, es importante para la cuenta para el tratamiento de excepciones. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye una aplicación de Portal de administración de ESB de ejemplo que muestra cómo se pueden ver y administrar las excepciones. Para obtener información detallada acerca de cómo reparar y volver a enviar excepciones mediante la aplicación de ejemplo de Portal de administración de ESB, consulte [reparando y volver a enviar mensajes](../esb-toolkit/repairing-and-resubmitting-messages.md).