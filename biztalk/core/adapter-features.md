---
title: Características del adaptador de TIBCO Enterprise Message Service | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede748ce-3f28-4942-b2bd-e38e5f1b0f54
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce63950ea9fca42969a7d8574fec76f438ed5f8f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015139"
---
# <a name="tibco-ems-adapter-features"></a>Características del adaptador de TIBCO EMS
El adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) permite publicar y suscribirse a colas y temas administrados por TIBCO EMS, mediante BizTalk Server y TIBCO SDK. El adaptador integra los mensajes de TIBCO EMS de forma rápida, fácil y confiable. Intercambia formatos de datos XML entre servidores de TIBCO EMS y Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para proporcionar una infraestructura de aplicación confiable y estrechamente integrada. Proporciona operaciones de integración de adaptadores de transmisión y recepción, así como administración de procesos empresariales de un extremo a otro, mediante esquemas XML.  
  
## <a name="data-validation"></a>Validar datos  
 El adaptador de BizTalk para TIBCO EMS se ejecuta en proceso con el host de BizTalk Server, como adaptador nativo estrechamente integrado, y valida la configuración del puerto en el momento de la configuración. Valida los datos tanto como sea posible; por ejemplo, nombre válido, número válido, válido en rango. No intenta realizar una conexión. Por lo tanto, el host, el destino de puerto, el usuario y la contraseña no se validan hasta que se efectúe una llamada en tiempo de ejecución, en cuyo caso se registra un error.  
  
## <a name="message-delivery"></a>Entrega de mensajes  
 El adaptador de BizTalk para TIBCO EMS garantiza la entrega única de mensajes. Los mensajes que no llegan a EMS se marcan como reintentables cuando se suspenden. Puede haber algunas excepciones, por ejemplo, cuando existe una configuración de puerto no válida en el momento de la ejecución.  
  
 El adaptador acepta los tipos de mensaje de EMS de texto.  El adaptador admite transacciones para mensajes que se envíen a EMS, y la compatibilidad con transacciones se controla mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  La conexión entre el adaptador de BizTalk para TIBCO EMS y el servidor EMS no es segura. No es compatible con el SDK de TIBCO EMS proporcionado.  
  
 El adaptador admite todas las propiedades JMS estándar y extensiones de EMS. Estas propiedades se colocan en el contexto del mensaje de BizTalk para que estén disponibles para una orquestación.  
  
## <a name="general-adapter-features"></a>Características del adaptador general  
 El adaptador de BizTalk para TIBCO EMS proporciona un medio de intercambio de datos empresariales en tiempo real, entre sistemas TIBCO EMS y BizTalk Server. Permite que el adaptador para la interacción entre una aplicación XML y TIBCO EMS. Habilita las aplicaciones XML para el procesamiento entrante y saliente con TIBCO EMS.  
  
 El adaptador acepta los mensajes XML para permitir que las aplicaciones de BizTalk Server se comuniquen con TIBCO EMS mediante una de las siguientes opciones:  
  
-   Adaptador de transmisión que usa un puerto de envío estático unidireccional para enviar un mensaje a TIBCO EMS.  
  
-   Adaptador de recepción que usa un puerto de recepción estático unidireccional para recibir mensajes de TIBCO EMS.  
  
### <a name="transmit-adapter-architecture-send--static-one-way"></a>Arquitectura del adaptador de transmisión: Envío: estático unidireccional  
 En un escenario de envío unidireccional, el puerto de envío se configura para enviar mensajes a una cola/tema. El adaptador de BizTalk para TIBCO Enterprise Message Service envía la solicitud al servidor TIBCO EMS, en la cola/el tema especificado. El adaptador envía el mensaje al sistema TIBCO EMS mediante el protocolo de comunicación TIBCO EMS. El sistema TIBCO EMS recibe las solicitudes y ejecuta la lógica empresarial. Para realizar llamadas en TIBCO EMS, se debe proporcionar el adaptador con la información de configuración para obtener acceso al servidor TIBCO EMS.  
  
 La siguiente imagen muestra la operación de envío unidireccional del adaptador.  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
### <a name="receive-adapter-architecture-receive--static-one-way"></a>Arquitectura del adaptador de recepción: Recepción: estática unidireccional  
 En un escenario de recepción unidireccional, la ubicación de recepción se configura para enviar mensajes a una cola/un tema de EMS. El adaptador de BizTalk para TIBCO EMS escucha los mensajes de una cola/un tema específico y envía los mensajes recibidos a BizTalk Server.  
  
 La siguiente imagen muestra la operación de recepción unidireccional del adaptador.  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de aplicaciones](../core/developing-applications5.md)   
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)