---
title: Codificación de caracteres | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a0c21c8-3318-4533-9734-89302527cb67
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 319ddd649e47e053fe2896d577f28b72602593e3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014683"
---
# <a name="character-encoding"></a>Codificación de caracteres
TIBCO Enterprise Message Service (EMS) admite distintas codificaciones de caracteres en los mensajes que el adaptador de BizTalk para TIBCO EMS transmite a EMS. Los mensajes se cifran mediante la codificación UTF-8 predeterminada. Cuando se reciben mensajes, el adaptador determina su codificación y convierte las cadenas apropiadas a UTF-8 antes de pasarlos a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Todas las conversiones de caracteres utilizan las clases de Microsoft .NET Framework, por lo tanto, el adaptador admite las conversiones de caracteres proporcionadas por este mismo marco de trabajo.  
  
## <a name="running-in-a-clustered-environment"></a>Ejecutar en un entorno agrupado  
 Los consumidores reciben los mensajes publicados en las colas en un orden predeterminado por el servidor EMS; solo un adaptador del entorno agrupado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe el mensaje. La cola puede configurarse como *mutuamente*. Esto significa que sólo el primer adaptador que se registra automáticamente para el consumo de mensajes en la cola recibe los mensajes. El servidor EMS sólo envía mensajes a otros clientes si el cliente exclusivo no reconoce la recepción del mensaje. La configuración de cola exclusiva se realiza en la configuración de EMS, y no puede configurarla el cliente.  
  
> [!NOTE]
>  Nota sobre las suscripciones a temas: dado que todos los adaptadores de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo están configurados de forma idéntica, que están suscritos para el mensaje y cada suscripción de tema recibe el mensaje.  
  
## <a name="transaction-support"></a>Compatibilidad con transacciones  
 El adaptador proporciona compatibilidad con las transacciones cuando así lo requieren los puertos de envío de orquestación. Las transacciones no están admitidas con el servidor EMS cuando el adaptador está escuchando los mensajes; sin embargo, el adaptador confirma la recepción de todos los mensajes de EMS después del envío correcto de mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. EMS vuelve a enviar los mensajes sin confirmar al adaptador.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador de BizTalk para TIBCO EMS](../core/security-in-biztalk-adapter-for-tibco-ems.md)   
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)