---
title: ¿Qué es el interceptor de BAM? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM Interceptor object
- BAM, collecting data
- BAM, Interceptor object
- data, collecting [BAM]
ms.assetid: e0213c4e-e2f4-4bb0-bd27-e5810f7e39d9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc78c5ae3f653e76652373767e60ec1dcaefba8c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013445"
---
# <a name="what-is-the-bam-interceptor"></a>¿Qué es el interceptor de BAM?
## <a name="overview"></a>Información general 

El interceptor de BAM es un objeto que permite instrumentar la aplicación para que capture datos de interés. En el diagrama siguiente se muestra el rol del interceptor de BAM y su interacción con los demás componentes de BAM:  
  
 ![](../core/media/bam-config-api.gif "bam_config_api")  
Interceptor de BAM  
  
 En cada paso de la aplicación donde pueda haber datos de interés, puede llamar a Interceptor OnStep, facilitar un identificador del paso y proporcionar algunos datos o un objeto arbitrario que esté utilizando en la aplicación.  
  
 Deberá implementar una función de devolución de llamada de tal forma que, cuando se produzca la llamada, el procedimiento de devolución de llamada obtenga el Id. de paso actual y el objeto de datos. Básicamente, el interceptor de BAM se encarga de propagar el objeto de datos a la devolución de llamada. La lógica real de extracción de datos reside en la aplicación. Por ejemplo, si los datos toman la forma de mensajes XML, la devolución de llamada utilizará XPaths. Para obtener más información acerca de XPaths, consulte [utilizar XPaths en la asignación de mensajes](../core/using-xpaths-in-message-assignments.md).  
  
 El interceptor de BAM decide qué datos solicitar, en función de la configuración que pueda crear mediante programación. El interceptor de BAM utiliza entonces los datos obtenidos para llamar a la secuencia DirectEventStream o BufferedEventStream, necesarias para el mantenimiento y el paso como argumento un a OnStep.  
  
 La operación de llamada al interceptor en cada paso no utiliza una gran cantidad de recursos. Si realiza la llamada y no efectúa ningún registro, el interceptor la devolverá inmediatamente. Esto significa que no habrá operaciones de disco, ni transacciones ni asignaciones y que, por lo tanto, casi no habrá impacto en el rendimiento. Al mismo tiempo, tendrá la posibilidad de extraer datos de BAM si es necesario. El impacto de rendimiento en los pasos relacionados con la extracción de datos y la disponibilidad de los datos dependerá de la implementación de la `IBAMDataExtractor Interface`.  
  
 Los siguientes ejemplos de código muestran el uso del interceptor durante la configuración y el tiempo de ejecución.  
  
## <a name="configuration-time"></a>Tiempo de configuración  
 El siguiente código muestra cómo configurar el interceptor para que se detenga en el paso recvPO de la aplicación y solicite el nombre y número de seguridad social del cliente:  
  
```  
ActivityInterceptorConfiguration cfg= new ActivityInterceptorConfiguration ("PurchaseOrder");  
...  
cfg.RegisterDataExtraction("CustomerName",recvPO,XpathName);  
cfg.RegisterDataExtraction("CustomerSSN",recvPO,XpathSSN);  
...  
BAMInterceptor interceptor=new BAMInterceptor();  
cfg.UpdateInterceptor(interceptor);  
...  
// The interceptor instance is ready.  
```  
  
 Tras crear una instancia del interceptor, podrá almacenarla para utilizarla más tarde, durante el tiempo de ejecución.  
  
 Puede crear diversos interceptores previamente creados, que representen distintas preferencias para los datos e hitos de BAM. Para obtener un rendimiento óptimo, serialice las instancias del interceptor utilizando la clase BinaryFormatter.  
  
## <a name="run-time"></a>Tiempo de ejecución  
 Utilice este código para usar el interceptor durante el tiempo de ejecución en un entorno de producción:  
  
```  
// Deserialize the Interceptor that was prepared before  
...  
es=new DirectEventStream(...)  
...  
Interceptor.OnStep(recvPO, data1, es, callback)  
...  
Interceptor.OnStep(approvePO, data2, es, callback)  
...  
```  
  
 Donde:  
  
- *recvPO* y *approvePO* son objetos arbitrarios que se usan para identificar los pasos descritos en la aplicación.  
  
- *Data1* y *data2* son objetos arbitrarios que haya en ese momento y puede contener datos interesantes: por ejemplo, el documento XML del pedido de compra.  
  
- *es* es la secuencia DirectEventStream o bufferedevent, dependiendo de los requisitos de rendimiento.  
  
- *devolución de llamada* es la implementación de la `IBAMDataExtractor Interface`.  
  
  El ejemplo de SDK [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md), se muestra el uso del Interceptor, que contiene tanto una herramienta y el ejemplo en tiempo de ejecución aplicación de configuración.  
  
  El motor de orquestaciones de BizTalk permite la intercepción que, a su vez, permite cambiar los datos que deben recopilarse para BAM en el tiempo de ejecución mediante el Editor de perfiles de seguimiento.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo determinar y establecer Roles de sistema de escritura de eventos para las actividades](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)  
  
## <a name="see-also"></a>Vea también  
 [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md)