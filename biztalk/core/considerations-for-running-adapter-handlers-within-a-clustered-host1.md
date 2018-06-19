---
title: Consideraciones para la ejecución de controladores de adaptador dentro de un clúster Host1 | Documentos de Microsoft
ms.custom: ''
ms.date: 2016-03-17
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- high availability
- receive adapters, clustering
- clustering, POP3 adapters
- FTP adapters, clustering
- clustering, receive adapters
- NLB system
- MSMQ send handler
- MSMQ receive handler
- clustering, FTP adapters
- handlers [adapters], best practices
- hosts, clustering
- MSMQ adapters
- clustering, MSMQ adapters
- adapters, best practices
- adapters, handlers
- POP3 adapters, clustering
- MSMQ adapters, clustering
- clustering
ms.assetid: ee66663c-4f4d-4515-9df1-aacf4fc72be4
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1fc93db61cddae43023f5c25eec62ecebd46e69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238484"
---
# <a name="considerations-for-running-adapter-handlers-within-a-clustered-host"></a>Consideraciones para ejecutar controladores de adaptador en un host agrupado
Compatibilidad con clústeres de host de BizTalk está disponible para proporcionar alta disponibilidad para el siguiente integrado adaptadores de BizTalk: adaptador de FTP, el adaptador SFTP, el adaptador de MSMQ y el adaptador de POP3. También se proporciona esta funcionalidad, de modo que hay una alta disponibilidad a la hora de ejecutar una sola instancia de un adaptador para una entrega ordenada.  
  
 Todos los controladores de adaptador de BizTalk pueden ejecutarse en un host agrupado. No obstante, con independencia de lo que se describe a continuación, la ejecución de controladores de adaptador en un host agrupado no supone ninguna ventaja. Si los requisitos de procesamiento no incluyen ninguno de los escenarios descritos a continuación, no deben ejecutar controladores de adaptador en un host del clúster.  
  
## <a name="running-the-ftp-or-sftp-adapter-receive-handler-within-a-clustered-biztalk-host"></a>Ejecutar el controlador de recepción del adaptador de FTP o SFTP en un host de BizTalk agrupado  
 En la mayoría de los adaptadores integrados de BizTalk, se puede conseguir una alta disponibilidad creando varios controladores de adaptador para ejecutarlos en instancias de host de BizTalk en diferentes servidores [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de un grupo de BizTalk. Sin embargo, los controladores de recepción del adaptador de FTP o SFTP no se deben configurar para ejecutarse en varias instancias de host de BizTalk simultáneamente. Esta recomendación se hace porque el adaptador de recepción FTP o SFTP utiliza el protocolo FTP o SFTP para recuperar archivos del sistema de destino. El protocolo FTP o SFTP no bloquea los archivos para asegurarse de que no se recuperan varias copias del mismo archivo simultáneamente cuando se ejecutan varias instancias del adaptador de recepción FTP o SFTP.  
  
 Para proporcionar una alta disponibilidad al adaptador de recepción FTP o SFTP, debe configurar el adaptador de recepción FTP o SFTP para ejecutarse en una instancia de host de BizTalk que se ha agrupado.  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a>Ejecutar controladores del adaptador de MSMQ en un host de BizTalk agrupado  
 Para garantizar la alta disponibilidad del adaptador de MSMQ y la coherencia transaccional de los mensajes enviados o recibidos por el adaptador de MSMQ, debe realizar lo siguiente:  
  
1.  Configurar Message Queue Server (MSMQ) como un recurso agrupado en un grupo de clústeres de Windows en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos.  
  
2.  Agregue el servicio MSMQ agrupado a la lista de dependencias de recurso del host de BizTalk agrupado. Esto garantiza que el host de BizTalk en clúster siempre se inicia después del servicio MSMQ agrupado en escenarios de conmutación por error.  
  
3.  Configure los controladores de envío y recepción del adaptador de MSMQ en una instancia de host de BizTalk que se haya configurado como un recurso de clúster en el mismo grupo de clúster que el recurso de MSMQ agrupado.  
  
 Estos pasos se recomiendan por los siguientes motivos:  
  
 **Controlador de recepción del adaptador de MSMQ** : las versiones MSMQ anteriores a MSMQ 4.0 (Windows Server 2008) no admite lecturas transaccionales remotas; lecturas transaccionales locales solo se admiten. En este caso, el adaptador de MSMQ recepción controlador debe ejecutarse en una instancia de host que es local para el servicio de Message Queue Server en clúster para realizar lecturas transaccionales locales con el adaptador de MSMQ.  
  
> [!IMPORTANT]
>  El controlador de recepción del adaptador de MSMQ requiere que haya una instancia local no agrupada del servicio Message Queue Server en ejecución, en el mismo equipo en el que se ejecuta la instancia de host del controlador de recepción.  
  
 **Controlador de envío del adaptador de MSMQ** : para asegurar la coherencia de envíos transaccionales realizados por el adaptador de MSMQ, la cola saliente utilizada por el controlador de envío del adaptador MSMQ debe tener alta disponibilidad para que si se produce un error en cola el servicio MSMQ para la salida puede ser reanudar. Configurar un clúster Queuingresource de mensaje y los controladores de adaptador MSMQ en un grupo de clúster asegurará que la cola saliente utilizada por el controlador de envío del adaptador MSMQ será alta disponibilidad. Esto mitigará la posibilidad de pérdida de mensajes en el caso de que deje de funcionar el servicio Message Queue Server.  
  
> [!NOTE]
>  Si la ubicación de recepción de MSMQ es **sólo** recibir desde las colas MSMQ de un MSMQ server remoto, a continuación, se puede conseguir alta disponibilidad mediante la ejecución de MSMQ de recepción host en varios equipos de BizTalk del grupo de BizTalk.  Para proporcionar alta disponibilidad para MSMQ, debe asegurarse que el servidor MSMQ remoto está usando la conmutación por error de Windows.  Si usa las colas transaccionales, el servidor MSMQ remoto debe ejecutar MSMQ 4.0 (Windows Server 2008) o superior.  
  
## <a name="running-the-pop3-adapter-receive-handler-within-a-clustered-biztalk-host"></a>Ejecutar el controlador de recepción del adaptador de POP3 en un host de BizTalk agrupado  
 No es necesario configurar el controlador de recepción del adaptador de POP3 para ejecutarse en un host de BizTalk a menos que el servidor POP3 del que lee el adaptador permita varias conexiones concurrentes al mismo buzón. Si el servidor POP3 al que está conectado el adaptador de POP3 permite varias conexiones concurrentes a los buzones, se recomienda asegurar la alta disponibilidad del adaptador de POP3 configurando un solo controlador de recepción del adaptador de POP3 para ejecutarlos en una instancia de host de BizTalk que se haya agrupado. Se recomienda esta actuación para garantizar que no se recuperan varias copias del mismo mensaje de correo electrónico de forma simultánea cuando se ejecutan varias instancias del adaptador de recepción POP3.  
  
## <a name="running-a-receive-adapter-that-supports-ordered-delivery-with-a-clustered-biztalk-host"></a>Ejecutar un adaptador de recepción que admita entrega ordenada con un host de BizTalk agrupado  
 Los adaptadores de MSMQ y MQSeries integrados proporcionan la capacidad de enviar documentos a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el orden en el que se recibieron. La correcta implementación de esta funcionalidad requiere que se esté ejecutando solo una instancia de estos adaptadores de recepción en un momento dado. Para proporcionar una alta disponibilidad a una sola instancia de estos adaptadores, se deben configurar para ejecutarse en una instancia de host de BizTalk agrupada.