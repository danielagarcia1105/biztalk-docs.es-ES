---
title: Procesamiento de adaptadores de recepción de MLLP | Microsoft Docs
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
ms.openlocfilehash: dbb5932d65bce2b17ebfca3645b8c755549b9a9c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968141"
---
# <a name="mllp-receive-adapter-processing"></a>Procesamiento de adaptadores de recepción de MLLP
El protocolo de capa inferior (MLLP) mínimos adaptador de recepción admite ambos modos de respuesta de solicitud unidireccionales y bidireccionales. El adaptador de escucha y acepta conexiones.  
  
 Cuando reciba el MLLP adaptador opera en modo bidireccional, el adaptador no recibirá un mensaje nuevo de la conexión hasta que la canalización ha generado la confirmación (ACK) para el mensaje anterior.  
  
## <a name="configuration-parameters"></a>Parámetros de configuración  
 Los parámetros para un controlador de recepción se configuran en el nivel de Host de BizTalk y se aplican a todas las ubicaciones de recepción MLLP asociadas con él.  
  
|Parámetro|Utilice|  
|---------------|---------|  
|*Max acepte el límite de conexiones*|Limita el número de conexiones abiertas simultáneas que aceptará el adaptador de recepción.|  
  
## <a name="acknowledgments-with-the-two-way-mllp-receive-adapter"></a>Adaptador de recepción de confirmaciones con el MLLP bidireccional  
 Cuando reciba un MLLP bidireccional adaptador recibe un mensaje, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) puede generar los siguientes tipos de mensajes de confirmación:  
  
- HL7 Mejorado confirmación ACK: en este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación de confirmación en la misma conexión. Envía una confirmación de Aceptar de aplicación en un puerto de envío diferentes.  
  
- Confirmación de aceptación de aplicación: En este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación de aceptación de aplicación en la misma conexión.  
  
- Estático ACK: en este escenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación en la misma conexión.  
  
- El tipo de confirmación generado depende el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración del explorador de configuración para la entidad que envía el mensaje. El valor de campos MSH 15 y 16 de un mensaje individual puede invalidar esta configuración. Sin embargo, para las aplicaciones que prevén confirmaciones estáticas, la configuración solo se puede establecer a través de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.  
  
## <a name="error-conditions"></a>Condiciones de error  
 Los siguientes eventos se producen cuando hay una condición de error o de inactividad:  
  
- Si se deshabilita la ubicación de recepción o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] apaga, ocurre lo siguiente:  
  
  - La ubicación de recepción dejará de aceptar nuevas conexiones.  
  
  - Para las conexiones existentes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] completamente recibe el mensaje actual y, a continuación, cierra la conexión.  
  
- Cuando se detecta inactividad (no carga se recibieron datos en la ubicación de recepción en el tiempo de espera especificado), el adaptador cierra la conexión.  
  
- Si [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje incompleto, se suspende la parte que recibe. Se omiten todos los bytes recibidos fuera de un mensaje (antes de la primera SB en una nueva conexión entre EB/CR y SB del siguiente mensaje).  
  
- Si se produce un error en la canalización analizar el mensaje, el mensaje todavía se entrega a la base de datos de cuadro de mensajes, con una propiedad promocionada **ParseError = true**.  
  
- Si se produce un error en un mensaje debido a la ausencia de una suscripción, o debido a errores estructurales en el encabezado, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suspende el mensaje en su formato original de "cable" (antes de que se está analizando). Una razón frecuente del error en la suscripción no es la falta de propiedades promocionadas. Puesto que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suspende el mensaje sin analizar, la **BTS. MessageType** estará en blanco.  
  
  En la tabla siguiente se enumera los errores que el MLLP devuelve del adaptador de recepción.  
  
|            Evento             |  Id.  |                                                                                                          Condición de error                                                                                                           |
|------------------------------|------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **ErrorListening**      | 8448 |                                                   No se puede enlazar a un socket local (que probablemente que alguna otra aplicación local usa la misma combinación de Id. de puerto y dirección IP).                                                    |
| **ErrorAcceptingConnection** | 8449 | No se pudo establecer una conexión TCP con la parte remota. Cualquier [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] alcanza el límite máximo de conexiones o los recursos eran insuficientes. |
|  **ErrorSubmittingMessage**  | 8452 |                   La base de datos no puede aceptar el mensaje. Cualquier [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] no estaba disponible o los recursos eran insuficientes.                   |
|     **ErrorSendingAck**      | 8454 |                                [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] no se pudo devolver la confirmación porque la conexión no estaba disponible.                                 |
  
## <a name="performance-counters"></a>Performance Counters  
 En la tabla siguiente se enumera los contadores de rendimiento que utiliza el adaptador MLLP.  
  
|Contador|Significado|  
|-------------|-------------|  
|Bytes|Tamaño de la carga de todos los documentos recibidos o enviados.|  
|Bytes/seg.|El rendimiento actual de la carga recibidos o enviados.|  
|Documentos procesados|**Recepción de MLLP**:<br /><br /> Número de documentos se entrega correctamente en la base de datos de cuadro de mensajes.<br /><br /> **Envío MLLP**:<br /><br /> Número de documentos se entrega correctamente a la aplicación remota.|  
|Documentos con errores|**Recepción de MLLP**:<br /><br /> Número de documentos no correctamente entregados a la base de datos de cuadro de mensajes.<br /><br /> **Envío MLLP**:<br /><br /> Número de documentos no correctamente entregados a la aplicación remota.|  
|Estado de la conexión|El estado de la conexión del adaptador, 1 o 0 (1 = conectado).|  
  
 Las instancias de contador de rendimiento utilizan el esquema de nomenclatura siguiente:  
  
```  
{recv|trans} : connection name : remote IP address : remote port ID  
```  
  
 Cuando reciba el MLLP adaptador utiliza el prefijo "recepción" y "trans" utiliza el adaptador de envío MLLP.  
  
> [!NOTE]
>  Mensajes de confirmación enviados por los puertos de recepción (por ejemplo, un adaptador funciona en modo bidireccional) y enviar puertos (en funcionamiento para recibir mensajes de confirmación en la misma conexión de socket) no se cuentan.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [Parámetros de configuración de envío y recepción de adaptadores](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [Procesamiento de adaptadores de envío MLLP](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [Configurar un puerto de envío para recibir confirmaciones](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)