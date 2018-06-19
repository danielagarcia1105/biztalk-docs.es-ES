---
title: Estados de la instancia de servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, states
- messages, processing
- states, service instances
ms.assetid: 38189538-72b3-49df-810b-e134362e35ef
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27bb6cac8925055bb8ed5359b3d038c44c136335
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272572"
---
# <a name="service-instance-states"></a>Estados de instancia de servicio
Cuando se procesa un mensaje, tienen lugar las acciones siguientes:  
  
-   En la ubicación de recepción, el adaptador de recepción, o componente de transporte, recibe el mensaje de una aplicación externa y lo envía a BizTalk Server para su procesamiento.  
  
    > [!NOTE]
    >  Se recibe un mensaje por el sistema en una variedad de formatos: XML, un archivo plano, o como un intercambio de datos electrónicos (EDI) entre empresas.  
  
-   La canalización de recepción descifra, descodifica y desensambla el mensaje.  
  
-   El motor de mensajería envía el mensaje y sus propiedades de acceso directo, como tipo y origen de mensaje, a la base de datos de cuadro de mensajes.  
  
-   Cuando se encuentra una suscripción coincidente, el mensaje se procesa en función de un conjunto de esquemas y asignaciones, y a veces de directivas o reglas de negocio que residen en el servidor de host.  
  
-   Una vez procesado, el mensaje resultante se almacena (escrito) en la base de datos de cuadro de mensajes. Las propiedades de acceso directo se han modificado para indicar dónde enviar el mensaje; por ejemplo, qué puerto de envío utilizar.  
  
-   Las propiedades de acceso directo del mensaje se evalúan con las expresiones de filtro definidas para el puerto de envío, y la base de datos de cuadro de mensajes entrega el mensaje al puerto de envío apropiado.  
  
-   Se debe cumplir una suscripción a una canalización de envío o un puerto de envío para que se pueda enviar el mensaje. El mensaje se cifra y se transmite.  
  
 Cada proceso de este ciclo genera su propio conjunto de eventos.  
  
 Del mismo modo que las instancias de servicio (puerto de recepción, orquestaciones, puertos de envío) procesan mensajes que se desplazan por BizTalk Server, estas instancias de servicio se pueden encontrar en uno de varios estados. Esta sección describe cuáles son estos estados y ofrece ejemplos de estados en momentos diferentes de su ciclo de vida.  
  
## <a name="service-instance-states"></a>Estados de instancia de servicio  
 La tabla siguiente muestra los estados posibles de una instancia de servicio con una explicación para cada estado.  
  
|State|Explicación|  
|-----------|-----------------|  
|**En el punto de interrupción**|Una orquestación activa coincide con un punto de interrupción, normalmente con uno establecido por un programador de soluciones de BizTalk Server. Este estado es válido sólo para orquestaciones.|  
|**Listo para ejecutarse**|Una instancia de servicio que se haya activado pero que todavía no se haya empezado a ejecutar, normalmente por indisponibilidad temporal de recursos, como una elevada carga de procesamiento en el servidor.|  
|**Activo**|Instancia de servicio en ejecución.|  
|**Deshidratación**|El estado de instancia se almacena en la base de datos de cuadro de mensajes y ningún servicio de Windows ejecuta esa instancia.|  
|**Completado con mensajes descartados**|La instancia de servicio se completó pero la instancia no consumió algunos mensajes.|  
|**Suspendido (reanudable)**|Instancia suspendida; puede reanudarla. **Importante:** reanudar una instancia de mensajería hará lo siguiente: <ul><li>Reanudar la instancia de mensajería.</li><li>Enviar el mensaje al puerto de envío.</li><li>El puerto de envío entrega el mensaje al destino, incluso si el estado del puerto de envío no es Iniciado.</li></ul> <br /><br /> Tenga en cuenta que cuando suspende una instancia programada y luego la reanuda, la instancia adopta un estado deshidratado.|  
|**Suspendido (no reanudable)**|Instancia suspendida, pero no puede reanudarla. Puede guardar los mensajes a los que hace referencia la instancia y luego finalizar la instancia.<br /><br /> Tenga en cuenta que cuando suspende una instancia programada y luego la reanuda, la instancia adopta un estado deshidratado.|  
|**Pendiente de suspender / pendiente de finalizar**|Un estado temporal, no un estado independiente. Lo puede combinar con otros estados.<br /><br /> Un mensaje de control para suspender o finalizar se envió a una instancia de servicio, pero la instancia aún no lo ha recogido. Sólo se permite una operación pendiente a la vez Cuando se deshidrata una instancia con una operación pendiente, puede finalizar la instancia.|  
  
### <a name="tracked-service-instance-states"></a>Estados de instancia de servicio supervisados  
 En la tabla siguiente se muestran los estados de seguimiento de instancias de servicio, con una explicación para cada estado.  
  
|State|Explicación|  
|-----------|-----------------|  
|**Se inició**|Cualquier instancia de servicio que se encuentre, en un momento determinado, en el cuadro de mensajes, por ejemplo, en un estado de punto de interrupción o suspendido (reanudable), se muestra como iniciada en la base de datos de seguimiento de BizTalk.|  
|**Completado**|El procesamiento de la instancia de servicio se ha completado correctamente.|  
|**Terminada**|Se finalizó la instancia de servicio.|  
  
## <a name="message-states"></a>Estados de mensaje  
 La tabla siguiente muestra los estados de un mensaje, con una explicación para cada estado.  
  
|State|Explicación|  
|-----------|-----------------|  
|**Consumido**|Una instancia de servicio está procesando el mensaje.|  
|**En proceso**|El mensaje se ha entregado al motor y se está procesando. Se encuentra en memoria.|  
|**En cola**|En cola abarca los estados de instancia En cola (en espera de procesarse), En cola (programado para entregarse más tarde) y En cola (en espera de reintento).|  
|**En cola (en espera de procesarse)**|El mensaje se encuentra en un escenario de entrega ordenada cuando el mensaje anterior es objeto de reintento por parte del puerto de envío de entrega ordenada.|  
|**En cola (programado para entregarse más tarde)**|El mensaje está esperando a ser enviado por un puerto de envío que tiene establecida una ventana de servicio.|  
|**En cola (espera de reintento)**|El mensaje se encuentra asociado a un puerto de envío que intenta volver a enviarlo, puesto que el URI de destino no se encuentra disponible.|  
|**Suspendida**|Suspendido abarca los estados de instancia Suspendido (reanudable) y Suspendido (no reanudable).|  
|**Suspendido (reanudable)**|La instancia de servicio asociada con el mensaje está suspendida y se puede reanudar.<br /><br /> Al reanudar una instancia de mensajería, se llevan a cabo los pasos que se describen a continuación:<br /><br /> -Reanudar la instancia de mensajería.<br />-Enviar el mensaje al puerto de envío.<br />-El puerto de envío entrega el mensaje al destino; incluso si el puerto de envío no está en un estado iniciado.|  
|**Suspendido (no reanudable)**|La instancia de servicio asociada con el mensaje está suspendida y no se puede reanudar.|  
  
## <a name="instance-states-before-and-after-an-operation"></a>Estados de instancia antes de una operación y después de ella  
 La tabla siguiente muestra los estados antes y después de una operación.  
  
> [!NOTE]
>  El estado inicial y final se muestra en negrita en la columna izquierda y fila superior. La operación se muestra en el cuerpo de la tabla.  
  
|Estado inicial|Estado nuevo después de que se aplique la operación|||||||  
|--------------------|------------------------------------------|------|------|------|------|------|------|  
||**En el punto de interrupción**|**Activo**|**Deshidratación**|**Suspendida**|**Terminada**|**Pendiente de finalizar**|**Pendiente de suspender**|  
|**En el punto de interrupción**|Adjuntar desde el depurador|Continuar desde el depurador|Detener Servicio de Windows|||Finalizar|Suspender|  
|**En el punto de interrupción (deshidratado)**|Adjuntar desde el depurador|Continuar desde el depurador|Detener Servicio de Windows|Suspender|Finalizar|||  
|**Listo para ejecutarse**||||Suspender|Finalizar|||  
|**Programado**||El tiempo de ejecución recoge la instancia porque se han iniciado ventanas de servicio.||||||  
|**Activo**|||Detener Servicio de Windows|||Finalizar|Suspender|  
|**Deshidratación**||El tiempo de ejecución recoge la instancia.|Detener Servicio de Windows|Suspender|Finalizar|||  
|**Suspendido (reanudable)**|Reanudar en punto de interrupción desde el depurador|Reanudar|||Finalizar|||  
|**Suspendido (no reanudable)**|||||Finalizar|||  
|**Termina con mensajes sin consumir**|||||Finalizar|||  
|**Pendiente de suspender**|Se puede intentar adjuntar, pero con el tiempo se debe producir un error.||Detener Servicio de Windows|Solicitud procesada|Sólo se podrá finalizar cuando la instancia esté deshidratada|||  
|**Pendiente de finalizar**|Se puede intentar adjuntar, pero con el tiempo se debe producir un error.||Detener servicio de Windows, la instancia se deshidrata||Solicitud procesada o instancia deshidratada|||  
  
## <a name="instance-states-during-an-operation"></a>Estados de instancia durante una operación  
 La tabla siguiente muestra el cambio de estado cuando el sistema realiza una operación en una instancia.  
  
|Estado inicial|Operación||||||  
|--------------------|---------------|------|------|------|------|------|  
||**Finalizar**|**Suspender**|**Reanudar**|**Reanudar en punto de interrupción**|**Continuar**|**Adjuntar**|  
|**En el punto de interrupción**|Finalizado|Suspendida|||Activo|En el punto de interrupción|  
|**En el punto de interrupción (deshidratado)**|Finalizado|Suspendida|||Activo|En el punto de interrupción|  
|**Preparado para ejecutarse**|Finalizado|Suspendida|||||  
|**Programado**|Finalizado|Suspendida|||||  
|**Activo**|Finalizado|Suspendida|||||  
|**Deshidratación**|Finalizado|Suspendida|||||  
|**Suspendido (reanudable)**|Finalizado||Activo|En el punto de interrupción|||  
|**Suspendido (no reanudable)**|Finalizado||||||  
|**Termina con mensajes sin consumir**|Finalizado||||||  
|**Pendiente de suspender**|Las finalizadas sólo podrán funcionar cuando la instancia esté deshidratada|||||Condición de anticipación|  
|**Pendiente de finalizar**|Ha terminado; solo funcionará, cuando la instancia esté deshidratada|||||Condición de anticipación|  
  
> [!NOTE]
>  Se produce una condición de anticipación cuando el sistema entrega varios mensajes de control a la instancia y no se garantiza el orden en el que la instancia los procesa.  
  
## <a name="see-also"></a>Vea también  
 [Mediante la página concentrador de grupo](../core/using-the-group-hub-page.md)