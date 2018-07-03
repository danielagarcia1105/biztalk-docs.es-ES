---
title: 'Diseñar con patrones: solución orientada a servicios | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- patterns [service solutions], examples
- examples, programming patterns
- patterns [service solutions], designing
- designing, programming patterns
ms.assetid: c196cd9d-2b2d-4548-bc7d-26196f7c2878
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32096bfa790f52ab29eed9d4b6b849688c73c922
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971005"
---
# <a name="designing-with-patterns-the-service-oriented-solution"></a>Diseñar con patrones: solución orientada a servicios
La solución orientada a servicios muestra cómo exponer una aplicación de BizTalk como un servicio para que la utilicen otras aplicaciones. La presentación de una aplicación como un servicio permite que otras aplicaciones consuman fácilmente la información y la utilicen en los servicios que proporcionan. Para obtener más información acerca del servicio interfaces vea "Service Interface" en [ http://go.microsoft.com/fwlink/?LinkId=46185 ](http://go.microsoft.com/fwlink/?LinkId=46185). Para obtener más información acerca de la integración orientada a servicios, vea "Service-Oriented Integration" en [ http://go.microsoft.com/fwlink/?LinkId=46186 ](http://go.microsoft.com/fwlink/?LinkId=46186).  
  
 La solución es una aplicación de información de crédito que proporciona los datos como una respuesta de servicio Web después de agregar información relevante de otras tres aplicaciones. La aplicación consolida los resultados y devuelve un único mensaje que contiene la información de crédito resumida. Los tres sistemas de servidor son los siguientes:  
  
- **Sistema empresarial SAP:** el servidor SAP proporciona el límite de crédito total del cliente. La solución se comunica con este sistema de servidor mediante el conector de SAP de [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  
  
- **Sistema de transacciones pendientes.** este sistema informa acerca del importe total de las transacciones pendientes de la cuenta. La solución utiliza Microsoft Host Integration Server (HIS) para comunicarse con el gran sistema (mainframe) de Windows Server. También usa la tecnología Transaction Integrator de HIS. Éstos permiten al sistema interactuar con el gran sistema como un servicio Web. La orquestación de BizTalk consume este servicio Web.  
  
- **Sistema de seguimiento de pago.** el sistema de seguimiento de pagos informa acerca del último pago realizado por el usuario. Este sistema utiliza MQSeries.  
  
  Como se indica en la información descrita en la descripción general de la solución, también puede utilizar una interfaz de servicio no Web a través de colas de MQSeries. (Para obtener más información sobre la estructura general de la aplicación, consulte [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md)). Aunque los servicios Web son la forma más habitual de crear arquitecturas orientadas a servicios, no todas las aplicaciones los pueden utilizar. Las soluciones de BizTalk Server le permiten proporcionar, además de servicios Web, formas alternativas para que las aplicaciones heredadas utilicen el servicio.  
  
  El acceso de MQSeries simula cómo un sistema heredado de respuesta interactiva de voz puede utilizar la solución. El acceso de MQSeries, junto con el acceso del servicio Web, muestra cómo las aplicaciones heredadas y nuevas pueden utilizar una única solución.  
  
## <a name="patterns-used-in-the-service-oriented-solution"></a>Patrones utilizados en la solución orientada a servicios  
 El diagrama siguiente muestra una versión simplificada de los patrones de la solución orientada a servicios.  
  
 ![Servicio&#45;orientada a los patrones de la solución](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
 La solución consta de cuatro partes principales, cada uno de los cuales representa un patrón: la interfaz de servicio, un enrutador basado en contenido, una lista de destinatarios y un agregador. La interfaz de servicio representa el mecanismo de interfaz que permite conectar a la solución. El enrutador basado en contenido comprueba la validez del mensaje y envía un mensaje de error si no es válido. La lista de destinatarios envía el mensaje a las tres aplicaciones servidor. Cuando las aplicaciones servidor responden, el agregador combina las respuestas en un único mensaje de respuesta. El mensaje de respuesta vuelve al solicitante a través de la interfaz de servicio.  
  
 Tenga en cuenta que quedan muchos datos sin especificar en el diagrama:  
  
-   En el diagrama se omiten los traductores de mensajes que la solución necesita para comunicarse con los sistemas externos.  
  
-   El diagrama no especifica cómo comunicarse con los procesos del servidor.  
  
-   El diagrama tampoco indica la naturaleza de la interfaz de servicio.  
  
-   En el diagrama tampoco se detalla si se debe utilizar o no una comunicación sincrónica o asincrónica.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de un servicio de la solución orientada a servicios](../core/developing-a-service-oriented-solution.md)   
 [Traducir los patrones del servicio en la solución orientada a servicios](../core/translating-the-patterns-of-the-service-oriented-solution.md)