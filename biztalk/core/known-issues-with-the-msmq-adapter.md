---
title: Problemas conocidos con el adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce77cdac-79c1-4529-8f09-0fb1f87ca037
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f210d0e480a311aed0bed5d50f6a827bd6ea4e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22262620"
---
# <a name="known-issues-with-the-msmq-adapter"></a>Problemas conocidos del adaptador de MSMQ
Esta sección contiene información que puede servir de ayuda para evitar errores.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="msmq-adapter-receive-locations-do-not-process-documents"></a>Las ubicaciones de recepción del adaptador de MSMQ no procesa documentos  
  
##### <a name="problem"></a>Problema  
 Las ubicaciones de recepción del adaptador de MSMQ no procesan documentos.  
  
##### <a name="cause"></a>Causa  
 Si no hay suficientes subprocesos en el grupo de subprocesos .NET asociado a la instancia de host de BizTalk en la que se está ejecutando el controlador de recepción del adaptador de MSMQ, las ubicaciones de recepción del adaptador de MSMQ no pueden procesar documentos debido a la falta de subprocesos.  
  
##### <a name="resolution"></a>Solución  
 Para aumentar el número de subprocesos disponibles en el grupo de subprocesos de .NET para la instancia de host, siga los pasos descritos en la **valores de subprocesos que alojan CLR para el host** sección del tema [parámetros de configuración que afectan al adaptador Rendimiento](../core/configuration-parameters-that-affect-adapter-performance.md).  
  
 Dado que cada MSMQ ubicación de recepción que está enlazado a un MSMQ recibir controlador requiere un subproceso del grupo de subprocesos. NET, establezca **MinIOThreads** y **MinWorkerThreads** en un valor que es mayor o igual que el número de ubicaciones de recepción MSMQ enlazadas al controlador de recepción. En consecuencia, establezca el valor de **MaxIOThreads** y **MaxWorkerThreads** en un valor igual al número de MSMQ, ubicaciones de recepción vinculadas al controlador de recepción * 2 para admitir una elevada capacidad:  
  
|Entrada DWORD|Valor recomendado|  
|-----------------|-----------------------|  
|MaxIOThreads|Número de ubicaciones de recepción de MSMQ que están enlazadas al controlador de recepción * 2 del adaptador de MSMQ.|  
|MaxWorkerThreads|Número de ubicaciones de recepción de MSMQ que están enlazadas al controlador de recepción * 2 del adaptador de MSMQ.|  
|MinIOThreads|Número de ubicaciones de recepción de MSMQ que están enlazadas al controlador de recepción del adaptador de MSMQ.|  
|MinWorkerThreads|Número de ubicaciones de recepción de MSMQ que están enlazadas al controlador de recepción del adaptador de MSMQ.|  
  
 Estos valores recomendados no son un factor de los subprocesos que utilizan otros controladores de adaptador u orquestaciones que se ejecutan en la instancia de host; por lo que los valores deberían aumentar en consecuencia.  
  
#### <a name="msmq-adapter-receive-locations-shut-down-shortly-after-they-are-enabled"></a>Las ubicaciones de recepción del adaptador de MSMQ se cierran poco después de que se habiliten  
  
##### <a name="problem"></a>Problema  
 Las ubicaciones de recepción de MSMQ se cierran poco después de que se habiliten  
  
##### <a name="cause"></a>Causa  
 Este problema puede producirse si una instancia local no en clúster del servicio Message Queue Server no se ejecuta en el mismo equipo en el que se ejecuta la instancia de host para el controlador de recepción de MSMQ.  
  
##### <a name="resolution"></a>Solución  
 Inicie el servicio Message Queue Server en el equipo en el que se ejecuta la instancia de host para el controlador de recepción de MSMQ. El controlador de recepción del adaptador MSMQ necesita que una instancia local del servicio de Message Queue Server esté en ejecución aunque una instancia en clúster del servicio Message Queue Server esté en ejecución en el mismo equipo.  
  
#### <a name="sc-tool-causes-error-when-attempting-to-stop-service-for-host-instance"></a>La herramienta SC produce un error al intentar detener el servicio para la instancia de host  
  
##### <a name="problem"></a>Problema  
 Cuando intenta usar la herramienta SC (Sc.exe) para cerrar el servicio para la instancia de host de BizTalk, puede recibir un mensaje de error que se parezca al siguiente:  
  
 **Error de ControlService 1053:**  
  
 **El servicio no respondió a la solicitud de inicio o control de manera oportuna.**  
  
 Después de recibir este mensaje de error, el servicio para la instancia de host de BizTalk se detiene. Sin embargo, la herramienta SC puede emplear dos o más minutos para cerrar el servicio.  
  
 Este problema se produce cuando la ubicación de recepción de Microsoft Message Queue Server está habilitada en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Además, puede registrarse un mensaje de error parecido al siguiente en el registro del sistema:  
  
 **Tipo de evento: Error**  
  
 **Origen del evento: Administrador de Control de servicio**  
  
 **Categoría de eventos: ninguno**  
  
 **Id. de evento: 7011**  
  
 **Descripción:**  
  
 **Tiempo de espera (30000 milisegundos) esperando una respuesta de transacción del servicio BTSSvc$ BizTalkServerApplication.**  
  
##### <a name="resolution"></a>Solución  
 Ahora está disponible una revisión compatible de Microsoft. Sin embargo, esta revisión está pensada para corregir únicamente el problema que se describe en este artículo. Aplique esta revisión solo a los sistemas que están experimentando este problema específico. Es posible que se realicen más pruebas para esta revisión. Por lo tanto, si no se ve gravemente afectado por este problema, se recomienda esperar hasta el siguiente Service Pack que contenga esta revisión.  
  
 Para resolver este problema, envíe una petición a los servicios de atención al cliente en línea de Microsoft para obtener la revisión.  
  
> [!NOTE]
>  Si se producen más problemas o es necesario resolver algún problema, es aconsejable crear una petición de servicio independiente. Se aplicarán los costes de soporte normales a otras cuestiones y problemas de soporte que no se cualifiquen para esta revisión específica.  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador MSMQ](../core/troubleshooting-the-msmq-adapter.md)