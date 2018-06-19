---
title: ¿Qué es el seguimiento de mensajes? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, metadata
- HAT, messages
- messages, tracking
- data, HAT
- metadata, tracking
- tracking, metadata
- HAT, data security
- tracking, messages
- configuring [HAT tracking], messages
- data, security
ms.assetid: 51cec59d-b411-4d8f-b771-7b2cf0f38945
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d76a4bd4133906a7949fac9e63816168506f412
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974642"
---
# <a name="what-is-message-tracking"></a>¿Qué es el seguimiento de mensajes?
Un mensaje es una instancia electrónica de datos, que se intercambia normalmente entre dos aplicaciones o procesos empresariales que se estén ejecutando. Una instancia de mensaje está compuesta por un cuerpo de mensaje, propiedades de mensaje y metadatos.  
  
 La consola de administración de BizTalk Server puede utilizarse para habilitar el seguimiento de propiedades de mensaje y de cuerpos de mensaje. Aquí también es posible ver el cuerpo del mensaje del que se efectúa el seguimiento, incluida la información de esquema, el nombre seguro y todas las propiedades promocionadas para el mensaje generado.  
  
## <a name="message-body"></a>Cuerpo de mensaje  
 El seguimiento del cuerpo del mensaje proporciona un registro de mensajes enviados y recibidos. Para guardar los mensajes después de que se haya completado el procesamiento de instancias de servicio, debe tener activado el seguimiento del cuerpo de los mensajes. Después de haber establecido las opciones de seguimiento, puede tardar unos minutos en ver los mensajes.  
  
> [!IMPORTANT]
>  El servicio Agente SQL Server debe ejecutarse en todas las bases de datos de cuadro de mensajes. El TrackedMessages_Copy_\<Nombrecuadrodemensajes\> trabajo pone a disposición para consultas de seguimiento y WMI cuerpos de mensaje. Para copiar eficazmente los cuerpos de mensaje, permanecen en la base de datos de cuadro de mensajes y se copian periódicamente a la base de datos de seguimiento de BizTalk (BizTalkDTADb) el TrackedMessages_Copy_\<Nombrecuadrodemensajes\> trabajo. Asimismo, la ejecución del servicio Agente SQL Server constituye un requisito previo para que el proceso de archivo y purga funcione correctamente.  
  
 Puede utilizar mensajes de los que se ha realizado un seguimiento para proporcionar confirmación de recepción, habilitar la solución de problemas y permitir la extracción de datos de las transacciones históricas. Es posible realizar un seguimiento de los cuerpos de mensaje en las orquestaciones, canalizaciones y puertos de entrada y salida. Puede recuperar estos mensajes mediante la consola de administración de BizTalk Server o mediante las interfaces de programación de aplicaciones (API) de Instrumental de administración de Windows (WMI) o del modelo de objetos (OM) de Operaciones (recomendado).  
  
 BizTalk Server no realiza el seguimiento de mensajes que no utilizan correctamente uno de los puntos de seguimiento. En algunos casos, como cuando un mensaje se ha suspendido porque no es válido, o si no hay ningún host espera el mensaje, pueden colocarse en la cola de suspensión sin sometidos a seguimiento. Si termina este mensaje, no se realizará ningún registro.  
  
> [!IMPORTANT]
>  El seguimiento de cuerpos de mensaje no constituye un sustituto de la auditoría legalmente obligatoria y no es compatible con la imposibilidad del rechazo.  
  
## <a name="message-properties"></a>Propiedades del mensaje  
 Las propiedades de mensaje incluyen propiedades promocionadas, información de enrutamiento y datos de socios comerciales. El seguimiento de las propiedades de mensaje le permite localizar un mensaje determinado entre los miles de los que puede haber realizado un seguimiento, si proporciona un registro de las propiedades promocionadas para cada mensaje en la lista Resultados. A continuación, puede realizar un seguimiento de un subconjunto del mensaje mediante una de estas propiedades.  
  
 Para realizar un seguimiento de propiedades de contexto, defina un esquema de propiedades para el espacio de nombres que se utiliza en el contexto para almacenar propiedades. Desde allí, puede seleccionar las propiedades de contexto de las que desea realizar un seguimiento. BizTalk Server realiza el seguimiento de éstas del mismo modo que realiza el seguimiento de las propiedades de mensaje promocionadas.  
  
> [!NOTE]
>  Asegúrese de asignar nombres diferentes a las propiedades del esquema. Si crea nombres duplicados, se genera un mensaje de error.  
  
 Por ejemplo, podría utilizar el editor de esquemas para promocionar el campo de número de pedido desde un esquema de pedido. A continuación, mediante Vista Búsqueda de mensajes, podría encontrar las instancias de mensaje que contengan un valor particular del campo del que se ha realizado un seguimiento, como número de pedido = 16995.  
  
 El seguimiento de la propiedad de mensaje crea mucha menos carga que el seguimiento del cuerpo del mensaje, ya que el primero solo realiza el seguimiento de los campos seleccionados. Después de haber establecido las opciones de seguimiento para la propiedad del mensaje, puede tardar unos minutos en ver las propiedades.  
  
## <a name="metadata"></a>Metadatos  
 Los metadatos, como el identificador de instancia de mensaje, la orquestación o canalización que registra el mensaje, el punto en el que la orquestación o canalización registra el mensaje y otros detalles de seguimiento pertinentes. Para que un mensaje de la base de datos de cuadro de mensajes se enrute a un proceso empresarial, debe contener las propiedades de contexto, como origen y tipo de mensaje. Estas propiedades se convierten en metadatos. El seguimiento de mensajes y de instancias de servicio usa los criterios de suscripción para consultar estos metadatos.  
  
 A través de la consola de administración de BizTalk Server, puede promocionar las propiedades de contexto seleccionando un esquema particular de sistema. Los esquemas de sistema se encuentran en el nodo Aplicaciones\BizTalk.System\Esquemas. BizTalk Server realiza un seguimiento estas propiedades de contexto global, es decir, todos los mensajes hacer un seguimiento de la propiedad de contexto determinado. Esto puede aumentar considerablemente el tamaño de la base de datos de seguimiento de BizTalk.  
  
## <a name="sensitive-data"></a>Datos confidenciales  
 Puede proteger los datos siguientes si se asegura de que no aparezcan en la ventana de propiedades de esquemas correspondiente, con lo que no serán susceptibles de seguimiento.  
  
-   Aplicar el **isSensitive** atributo a cualquier propiedad confidencial de un esquema de propiedades, por lo que ya no está visible en la propiedad de mensaje selecciones de configuración de seguimiento.  
  
-   Todos los transportes estándar tienen contraseñas confidenciales, por lo que no se puede realizar el seguimiento de estos transportes.  
  
-   Asimismo, estas propiedades confidenciales ya no están en la base de datos de administración. Por tanto, si establece opciones de seguimiento directamente en la base de datos, no se podrá realizar un seguimiento de éstas.  
  
-   Si realiza el seguimiento de cuerpos de mensaje salientes a través de la red, el seguimiento de mensajes quita todas las propiedades de transporte del acceso directo del cuerpo de mensaje del que se ha realizado el seguimiento. Por tanto, además de quitar propiedades de transporte saliente del acceso directo del cuerpo de mensaje del que se ha realizado un seguimiento, el seguimiento de mensajes también quita las propiedades de los transportes entrantes.  
  
    > [!IMPORTANT]
    >  Una propiedad promocionada puede contener datos confidenciales. Si las consultas de seguimiento de la página Concentrador de grupo realizan el seguimiento de una propiedad que incluya datos confidenciales, cualquier usuario con permiso para ejecutar las consultas de seguimiento podrá ver estos datos.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el seguimiento mediante la consola de administración de BizTalk Server](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)