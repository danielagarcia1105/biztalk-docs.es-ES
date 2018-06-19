---
title: Cómo procesa el adaptador de recepción de MLLP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, receive adapters
- MLLP adapters, send adapters
- receive adapters
ms.assetid: 03c9a5f6-6f23-454f-8bab-e7c7b6057efa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28713e22c37c12ef6f2cb9f8df8d228759d00c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207452"
---
# <a name="mllp-receive-adapter-processing"></a>Cómo procesa el adaptador de recepción de MLLP
El protocolo de nivel inferior (MLLP) mínimo adaptador de recepción admite dos modos de respuesta de solicitud unidireccionales y bidireccionales. El adaptador de escucha y acepta conexiones.  
  
 Cuando reciba el MLLP adaptador funciona en modo bidireccional, el adaptador no recibirá un mensaje nuevo de la conexión hasta que la canalización ha generado la confirmación (ACK) para el mensaje anterior.  
  
## <a name="configuration-parameters"></a>Parámetros de configuración  
 Los parámetros para un controlador de recepción estén configurados en el nivel de Host de BizTalk y se aplican a todas las ubicaciones de recepción MLLP asociadas a él.  
  
|Parámetro|Utilice|  
|---------------|---------|  
|*Max acepte el límite de conexiones*|Limita el número de conexiones abiertas simultáneas que aceptará el adaptador de recepción.|  
  
## <a name="acknowledgments-with-the-two-way-mllp-receive-adapter"></a>Adaptador de recepción de confirmaciones con la MLLP bidireccional  
 Cuando recibe un MLLP bidireccional adaptador recibe un mensaje, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) puede generar los siguientes tipos de mensajes de confirmación:  
  
-   HL7 Mejorado confirmación ACK: en este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación confirmar en la misma conexión. Envía una confirmación de Aceptar de aplicación en un puerto de envío diferentes.  
  
-   Confirmación de aceptación de aplicación: En este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación de aceptación de aplicación en la misma conexión.  
  
-   Estático ACK: en este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación en la misma conexión.  
  
-   El tipo de confirmación generado depende el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración del explorador de configuración para la entidad que envía el mensaje. El valor en los campos MSH 15 y 16 de un mensaje individual puede invalidar esta configuración. Sin embargo, para las aplicaciones que confirmaciones estático, la configuración sólo se puede establecer mediante [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.  
  
## <a name="error-conditions"></a>Condiciones de error  
 Los siguientes eventos se producen cuando existe una condición de error o de inactividad:  
  
-   Si se deshabilita la ubicación de recepción o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se cierra, ocurre lo siguiente:  
  
    -   La ubicación de recepción ya no acepta nuevas conexiones.  
  
    -   Para las conexiones existentes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] completamente recibe el mensaje actual y, a continuación, cierra la conexión.  
  
-   Cuando se detecta inactividad (ningún dato de carga recibido en la ubicación de recepción en el tiempo de espera especificado), el adaptador cierra la conexión.  
  
-   Si [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje incompleto, se suspende la parte que recibe. Se omiten todos los bytes recibidos fuera de un mensaje (antes del primer SB en una nueva conexión, entre EB/CR y SB del siguiente mensaje).  
  
-   Si se produce un error en la canalización analizar el mensaje, el mensaje todavía se entrega a la base de datos de cuadro de mensajes, con una propiedad promocionada **ParseError = true**.  
  
-   Si se produce un error en un mensaje debido a la ausencia de una suscripción o debido a errores estructurales en el encabezado, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suspende el mensaje en su forma de "cable" original (antes de que se está analizando). Un motivo frecuente del error de suscripción no es la falta de propiedades promocionadas. Puesto que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suspende el mensaje sin analizar, la **BTS. MessageType** estará en blanco.  
  
 En la tabla siguiente se enumera los errores que el MLLP devuelve del adaptador de recepción.  
  
|Evento|ID|Condición de error|  
|-----------|--------|---------------------|  
|**ErrorListening**|8448|No se pudo enlazar a un socket local (probablemente que otra aplicación local usa la misma combinación de Id. de dirección/puerto IP).|  
|**ErrorAcceptingConnection**|8449|No se pudo establecer una conexión de TCP con la parte remota. Cualquier [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] alcanzó el límite máximo de conexiones o los recursos eran insuficientes.|  
|**ErrorSubmittingMessage**|8452|La base de datos de cuadro de mensajes no pudo aceptar el mensaje. Cualquier [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] no estaba disponible o los recursos eran insuficientes.|  
|**ErrorSendingAck**|8454|[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]no se pudo devolver la confirmación porque la conexión no estaba disponible.|  
  
## <a name="performance-counters"></a>Performance Counters  
 En la tabla siguiente se enumera los contadores de rendimiento que usa el adaptador MLLP.  
  
|Contador|Significado|  
|-------------|-------------|  
|Bytes|Tamaño de la carga de todos los documentos recibidos o enviados.|  
|Bytes/seg.|El rendimiento actual de la carga recibidos o enviados.|  
|Documentos procesados|**Recepción de MLLP**:<br /><br /> Número de documentos se ha entregado correctamente a la base de datos de cuadro de mensajes.<br /><br /> **Envío MLLP**:<br /><br /> Número de documentos se ha entregado correctamente a la aplicación remota.|  
|Documentos con errores|**Recepción de MLLP**:<br /><br /> Número de documentos no correctamente entregados a la base de datos de cuadro de mensajes.<br /><br /> **Envío MLLP**:<br /><br /> Número de documentos que no se entregue a la aplicación remota.|  
|Estado de la conexión|El estado de la conexión del adaptador, 1 o 0 (1 = conectado).|  
  
 Las instancias del contador de rendimiento utilizan el esquema de nomenclatura siguiente:  
  
```  
{recv|trans} : connection name : remote IP address : remote port ID  
```  
  
 Cuando reciba el MLLP adaptador utiliza el prefijo "recepción" y el adaptador de envío MLLP utiliza "transacciones".  
  
> [!NOTE]
>  Mensajes de confirmación enviados por (por ejemplo, un adaptador funciona en un modo bidireccional) de puertos de recepción y envían no se cuentan los puertos (funcionando para recibir los mensajes de confirmación en la misma conexión de socket).  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [Parámetros de configuración para el envío y adaptadores de recepción](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [Cómo procesa el adaptador MLLP envío](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [Cómo configurar un puerto de envío para recibir mensajes de confirmación](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)