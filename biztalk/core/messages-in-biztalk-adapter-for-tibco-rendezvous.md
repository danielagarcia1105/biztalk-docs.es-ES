---
title: Mensajes en el adaptador de BizTalk para TIBCO Rendezvous | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passing messages
- TIBCO Rendezvous
- messages
- message passing
- messages, passing
ms.assetid: 12699550-22e7-4a11-a024-2302570970af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4bc1eadbefdeb5c59df9a1b999ffdd3e530587a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messages-in-biztalk-adapter-for-tibco-rendezvous"></a>Mensajes en el adaptador de BizTalk para TIBCO Rendezvous
El Adaptador de BizTalk para TIBCO Rendezvous proporciona conectividad bidireccional entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y TIBCO Rendezvous. Este adaptador utiliza tanto la API TIBCO Rendezvous como la API del marco de trabajo de adaptadores BizTalk para proporcionar una elevada integración.  
  
## <a name="about-tibco-rendezvous"></a>Acerca de TIBCO Rendezvous  
 TIBCO Rendezvous es un producto de software que proporciona un bus de mensaje para la integración de aplicaciones empresariales(EAI). TIBCO proporciona API de mensajería en C, C++, Java, Visual Basic y de Microsoft .NET Framework recibir fuentes de datos en hojas de cálculo de Microsoft Office Excel y otras aplicaciones de su elección. Para obtener más información, consulte [conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md).  
  
### <a name="message-passing"></a>Pasar mensajes  
 El concepto básico de pasar mensajes es bastante sencillo:  
  
-   Un mensaje tiene un único asunto formado por elementos separados por puntos. Se envía un mensaje a un único daemon de Rendezvous (aunque podría transmitirse a otros daemons).  
  
-   Un agente de escucha anuncia sus asuntos de interés a un daemon (con una función básica de comodín). Los mensajes con asuntos coincidentes se le entregan si los dos daemons están conectados entre sí o son el mismo daemon.  
  
 Una significativa funcionalidad "Empresarial" se agrega si se desea, con la posibilidad de usar las opciones Tolerancia a errores/Fiable o Certificado, todas implementadas a través de mensajes subyacentes básicos.  
  
 Los propios mensajes pueden verse como campos nombre-valor o número-valor escritos (los dos mecanismos de identificación de un mensaje pueden mezclarse y coincidir con determinadas restricciones). Un mensaje en sí puede contener submensajes, que a su vez pueden contener submensajes.  
  
 Los nombres de asunto se componen de uno o varios elementos separados por puntos. Los elementos implementan una jerarquía de nombres de asunto que refleja la estructura de la información en un sistema de aplicación. Las siguientes cadenas son ejemplos de nombres de asunto válidos:  
  
-   RUN.HOME  
  
-   RUN.for.Elected_Office  
  
 El Adaptador de BizTalk para TIBCO Rendezvous usa el SDK de TIBCO Rendezvous para publicar mensajes en asuntos de TIBCO Rendezvous y registrarse para eventos de TIBCO Rendezvous. Las clases relacionadas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se hospedan en un equipo con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Se inicia un proceso independiente (agente de tiempo de ejecución) y actúa como programa Rendezvous; se usan las funciones remotas de .NET Framework para intercambiar mensajes entre los dos.  
  
-   Los mensajes en el nivel de información, de advertencia y de error se envían al registro de eventos de Windows.  
  
-   Todos los niveles, incluidos los mensajes en el nivel de depuración, se envían al Registro de seguimiento de Windows.  
  
#### <a name="transmitter"></a>Transmisor  
 El Adaptador de BizTalk para TIBCO Rendezvous inicia un agente de tiempo de ejecución por cada puerto de envío. La API de .NET Framework de TIBCO Rendezvous solo permite establecer la codificación de caracteres en el ámbito global. Por lo tanto, una de las opciones de configuración de puerto es un número de página de códigos. Al comenzar un proceso diferente para cada página de código, el adaptador puede proporcionar una mejor compatibilidad con la globalización.  
  
#### <a name="receiver"></a>Receptor  
 El Adaptador de BizTalk para TIBCO Rendezvous inicia un agente de tiempo de ejecución por cada ubicación de recepción.  
  
#### <a name="transactions"></a>Transactions  
 El producto TIBCO Rendezvous no es transaccional. Es necesario un producto independiente, TIBCO Rendezvous TX. El Adaptador de BizTalk para TIBCO Rendezvous no admite transacciones en esta versión.  
  
#### <a name="security"></a>Seguridad  
 TIBCO Rendezvous solo admite la autenticación entre los programas y daemons de TIBCO Rendezvous. No realiza la autorización o el cifrado. Es necesario un producto independiente, TIBCO Rendezvous DataSecurity.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md)   
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)