---
title: Crear instancias e inicializar un adaptador de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f10e6507-3351-4173-95f5-48546ca5f5c4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b91bb59d974d68595e53c563311c74f590d33b3d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978925"
---
# <a name="instantiating-and-initializing-a-send-adapter"></a>Crear instancias e inicializar un adaptador de envío
De forma predeterminada, no se crea ninguna instancia de los adaptadores de envío hasta que se les entrega el primer mensaje. A este proceso se le denomina "creación diferida". El método predeterminado de creación diferida es útil para conservar los recursos del sistema. El adaptador de envío, una vez creado, se almacena en caché y está activo hasta que se detiene el servicio de BizTalk Server.  
  
 El **InitTransmitterOnServiceStart** miembro de la **capacidades** enumeración dirige el motor de mensajería para crear el adaptador de envío en el inicio del servicio, en lugar de utilizar la creación diferida predeterminada, Si se desea esto.  
  
 El modelo de enviar un mensaje es diferente del de recibir un mensaje en cuanto al procesamiento por lotes de los mensajes. En el caso de la recepción, el adaptador tiene mensajes entrantes que insertar en un lote obtenido del motor de mensajería. En el caso del envío, el motor de mensajería obtiene un lote del adaptador y envía mensajes al adaptador para que se transmitan. En ambos casos, se usa el proxy de transporte para obtener los objetos de lote de mensajes.  
  
## <a name="how-a-send-adapter-is-initialized"></a>Cómo se inicializa un adaptador de envío  
 Para habilitar la configuración y el enlace al proxy de transporte, los adaptadores deben implementar las interfaces de configuración siguientes:  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
  Los pasos siguientes describen la secuencia de eventos que conlleva la inicialización de un adaptador de envío:  
  
1. Cuando el motor de mensajería Inicializa un adaptador de envío, en primer lugar realiza un **QueryInterface** para **IPersistPropertyBag**, que es una interfaz opcional. Si el adaptador implementa la interfaz, la configuración del controlador se pasa al adaptador en el **carga** llamada al método. El adaptador usa esta información para asegurarse de que está configurado correctamente.  
  
2. El motor de mensajería realiza un **QueryInterface** para **IBTTransportControl**, que es una interfaz obligatoria.  
  
3. El motor llama a **IBTTransportControl.Initialize**, pasando el proxy de transporte para el adaptador.  
  
4. El motor de mensajería realiza un **QueryInterface** para **IBTTransmitter**.  
  
    Si el motor de mensajería detecta esta interfaz, el adaptador se considera como un transmisor no compatible con lotes.  
  
    Si el motor de mensajería no detecta esta interfaz, el motor de mensajería realiza un **QueryInterface** para **IBTBatchTransmitter**, cuya detección significa que el adaptador es un compatibles con lotes transmisor.  
  
    Si el motor de mensajería no detecta ninguna de estas interfaces, se produce un error de inicialización. Este error ocurre cuando no se detecta alguna de las interfaces obligatorias.  
  
   En el diagrama siguiente se muestra esta secuencia de llamadas a la API; las interfaces de color azul son las que implementa el adaptador.  
  
   ![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")  
  
   El adaptador puede enviar mensajes justo después de inicializarse y configurarse.  
  
   La ilustración siguiente muestra las interacciones de objetos que conlleva la inicialización de un adaptador de envío.  
  
   ![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")  
   Flujo de trabajo correspondiente a la inicialización de un adaptador de envío  
  
> [!NOTE]
>  Los adaptadores no deberían bloquear el motor de mensajería en las llamadas como **IBTTransportControl.Initialize** y **IPersistPropertyBag.Load**. Un procesamiento excesivo en estas llamadas afecta al tiempo de inicio del servicio.