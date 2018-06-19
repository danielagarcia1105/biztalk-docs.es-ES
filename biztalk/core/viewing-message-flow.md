---
title: Ver el flujo de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, messages
- messages, processing
- HAT, Message Flow view
- messages, HAT
ms.assetid: 08d2c052-98d0-43ca-99e5-48d0754411df
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d15ba3e6fa45b95ab49e1d24d5388a767d6bd8ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289316"
---
# <a name="viewing-message-flow"></a>Ver Flujo de mensajes
Un flujo de mensajes es el conjunto de pasos de procesamiento contiguos que toma un mensaje. Se obtiene acceso a la vista de mensajes a través del menú contextual que aparece al hacer clic con el botón secundario en una instancia de mensaje o servicio de la página de información general del grupo de la consola de administración de BizTalk Server. Cuando se encuentre en la vista Flujo de mensajes, podrá alternar entre la vista Flujo de mensajes y el Depurador de orquestaciones.  
  
 La vista Flujo de mensajes muestra los mensajes enviados y recibidos por una instancia de servicio (orquestación, puerto o canalización), además de detalles como la dirección URL, el puerto y la entidad utilizados. También es posible ver qué instancias de servicio precedentes controlaron los mensajes entrantes a la instancia de servicio que se visualice en un momento determinado. Se puede desplazar de nuevo a estas instancias, y ver los mensajes que entran en ellas y que salen de ellas. También puede ver las instancias de servicio posteriores que recibieron mensajes de la instancia de servicio que se visualiza en un momento determinado, así como desplazarse hacia delante a estas instancias para ver los mensajes que entran en ellas y que salen de ellas. Es decir, puede rastrear la ruta completa de un mensaje de activación a través del proceso empresarial.  
  
 También podrá desplazarse, en la vista Flujo de mensajes, de una instancia de servicio incompleta (una instancia que continúa con el procesamiento de un mensaje y que aún no se ha completado) a los detalles de esta instancia de servicio en la consola de administración de BizTalk Server para ver su estado actual (en ejecución, en suspensión, etc.).  
  
 En la parte superior de la ventana Flujo de mensajes, se muestra la información de servicio, como el tiempo de inicio y finalización, los códigos de error y la versión. En la parte inferior de la ventana se muestra Actividad de mensaje del servicio, donde se detallan los mensajes que se enviaron o recibieron. Se pueden ver más detalles de cada instancia de mensaje seleccionando los botones Expandir o Contraer. Las instancias de mensaje muestran todos los detalles de forma predeterminada.  
  
 Junto a la columna Entrada o salida, el elemento raíz y el espacio de nombres de destino identifican el esquema. A continuación, podrá encontrar los detalles del mensaje. Debajo de la información del esquema, aparece un vínculo con un nombre de elemento, como, por ejemplo, EquityLoanReceivePipeline. Al hacer clic en el vínculo, aparecerá la información del elemento, con lo que se permite seguir el mensaje a través de él.  
  
 Para volver al servicio con el que comenzó, haga clic en el elemento de destino o de origen correspondiente en el otro elemento.  
  
 La siguiente tabla contiene la información que se muestra para cada uno de los servicios.  
  
|Nombre|Contenido|  
|----------|--------------|  
|Id. de instancia|Identificador único global (GUID) asociado a la instancia.|  
|Host|Nombre del host que ejecuta la orquestación o la canalización.|  
|State|Estado actual de la instancia. Los estados posibles son En ejecución, Completado, Suspendido de forma manual, Error, Finalizado, En modo de depuración e Interrupción.|  
|Start Time|Hora de inicio de la canalización o la orquestación.|  
|Hora de finalización|Hora a la que se completó la canalización o la orquestación.|  
|Duración|Tiempo, en milisegundos, que tardó el elemento en ejecutarse.|  
|Código de salida|Código de salida técnico.|  
|Información del error|Mensaje de texto acerca del error.|  
|Nombre|Nombre de la orquestación o la canalización.|  
|Tipo|Tipo de elemento, orquestación o canalización.|  
|Id. de versión|Versión única del elemento.|  
|Tiempo de implementación|Momento en el que se implementó la canalización o la orquestación.|  
  
 Debajo de la tabla de detalles Elemento, se muestra la actividad de mensajes de las instancias de servicio enviadas o recibidas por la canalización o la orquestación específica. Cada fila de la tabla representa un mensaje y se puede expandir una instancia de mensaje para mostrar detalles del mensaje, como el Id., el tamaño y el nombre del puerto.  
  
 La siguiente tabla contiene la información que se muestra para cada instancia de mensaje.  
  
|Nombre|Contenido|  
|----------|--------------|  
|Entrada/salida|Un icono de mensaje recibido o de mensaje enviado indica los estados de los mensajes.|  
|Instancia de mensaje|Elemento de nivel superior y espacio de nombres de destino; intercambio sin analizar en el caso de que se desconozca.|  
|Estado de mensaje|Los Estados posibles: Aceptar, en transmisión, error de transmisión, error de transmisión (volver a intentarlo) y error de transmisión (volver a enviar en el transporte de reserva).|  
|Timestamp|Hora a la que este mensaje en concreto entró a formar parte de la acción actual (envío o recepción).|  
  
 Después de expandir la instancia de mensaje, se mostrará la siguiente información.  
  
|Nombre|Contenido|  
|----------|--------------|  
|Id. de instancia de mensaje|GUID del mensaje.|  
|Tamaño|Tamaño del mensaje. Si el mensaje no tiene tamaño, no se visualiza ningún valor.|  
|Partes|Número de partes del mensaje que no incluyen un acceso directo.|  
|Adaptador|Adaptador utilizado para transmitir el mensaje. Los siguientes son tipos de adaptadores posibles: archivo, HTTP, SOAP, Message Queue Server de BizTalk, SOAP o WCF.|  
|Dirección URL|URL de origen o destino.|  
|Puerto|Nombre del puerto al que se envió el mensaje o en el que se recibió.|  
|Nombre de entidad|Nombre de la entidad que envía o recibe el mensaje. El campo se visualiza sólo si se conoce la información.|  
|Certificado de descifrado|Huella digital del certificado utilizado para descifrar el mensaje. Este campo tan sólo se muestra si un mensaje incluye un certificado de descifrado.|  
|Signature|Firma del mensaje. Este campo sólo se visualiza si se firmó el mensaje.|  
|Icono de estado|Estado actual del mensaje, que puede incluir Recibido, Enviado o en Cola de trabajo.|  
|URL de elemento de origen o destino|Elemento (orquestación o canalización) identificado como el origen o el destino del mensaje. Al hacer clic en él, el sistema redirige al usuario a una vista para esa instancia del elemento.|  
  
 Cuando ve una instancia de orquestación, puede cambiar a la vista depurador de orquestaciones haciendo clic en **cambiar al depurador de orquestaciones**.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con la vista depurador de orquestaciones](../core/working-with-the-orchestration-debugger-view.md)   
 [Datos de instancia y los mensajes de seguimiento de visualización](../core/viewing-tracked-message-and-instance-data.md)