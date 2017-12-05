---
title: Utilice los contadores de rendimiento con el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b928eaf-2ab6-40a6-a1dd-804d4e89541e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bfff208920b25ee1a22aa2c3c74feeba42f4b43
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="use-performance-counters-with-the-wcf-lob-adapter-sdk"></a>Utilice los contadores de rendimiento con el SDK de adaptador LOB de WCF
Puede usar la herramienta de rendimiento para recopilar automáticamente datos de rendimiento de equipos locales o remotos que ejecutan el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Puede definir el inicio y detener tiempos de generación automática de registros, administrar varias sesiones de registro desde una sola ventana de consola y establecer una alerta en un equipo que permite que se envíe un mensaje o un registro para iniciarse cuando se cumplen los criterios. Este tema describen los contadores de rendimiento para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  
  
## <a name="performance-objects-and-counters"></a>Los contadores y objetos de rendimiento  
 Al instalar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], un objeto de rendimiento único denominado "ServiceModel adaptadores" está instalado. El objeto de rendimiento contiene un número de contadores de rendimiento. Un objeto de rendimiento mide la actividad para un recurso determinado, aplicación o servicio. Objetos de rendimiento y los contadores de obtendrán datos de rendimiento de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], características y servicios en el equipo cuando se utilicen. Normalmente, estos datos de rendimiento se denominan para el componente que genera los datos. Contadores de rendimiento se utilizan para recopilar información específica o datos de un objeto de rendimiento determinado.  
  
 Al seleccionar los contadores del objeto de rendimiento ServiceModel adaptadores, puede elegir supervisar sólo las instancias de adaptador específico de información, seleccione la instancia en la lista Seleccionar instancias. Cada instancia del adaptador se mostrarán en el formato de \<ProcessId\>@\<ConnectionString\>. Por ejemplo, 115@echo:&#124; &#124; host &#124; temp? echoprefix = anterior indica la instancia de adaptador de eco ejecutando en proceso 115.  
  
 Para obtener información sobre los contadores de rendimiento de WCF, vea [contadores de rendimiento de WCF](https://msdn.microsoft.com/library/ms735098.aspx).
  
### <a name="servicemodel-adapters-metadata-cache-performance-counters"></a>Contadores de rendimiento de memoria caché de metadatos de ServiceModel adaptadores  
 La siguiente tabla resume los contadores de rendimiento de la memoria caché que pueden utilizar para supervisar la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  
  
|Contador|Description|  
|-------------|-----------------|  
|% De memoria caché de lectura aciertos|Porcentaje de metadatos de lectura aciertos de la caché de adaptador.|  
|Metadatos resuelto|Número de elementos de metadatos resuelto por el adaptador.|  
|% Total de caché|Porcentaje del límite de tamaño de caché en uso.|  
  
### <a name="servicemodel-adapters-connection-performance-counters"></a>Contadores de rendimiento de conexión de adaptadores de ServiceModel  
 La siguiente tabla resume los contadores de rendimiento de conexión que pueden utilizar para supervisar la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  
  
|Contador|Description|  
|-------------|-----------------|  
|Conexiones anuladas|Número de conexiones de sistema de destino ha anulado.|  
|Las conexiones en uso|Número de conexiones de sistema de destino actualmente en uso.|  
|Conexiones abiertas|Número de conexiones de sistema de destino actualmente abierta.|  
|Conexiones listo|Número de conexiones de sistema de destino disponibles.|  
|Solicitudes de conexión pendientes|Número de pendiente de las solicitudes de conexión de sistema de destino.|  
  
### <a name="servicemodel-adapters-message-exchange-performance-counters"></a>Contadores de rendimiento de intercambio de mensajes de adaptadores de ServiceModel  
 La siguiente tabla resume los contadores de rendimiento de exchange de mensaje que pueden utilizar para supervisar la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  
  
|Contador|Description|  
|-------------|-----------------|  
|Llamadas salientes|Número de llamadas salientes desde el adaptador al sistema de destino.|  
|Las llamadas salientes/seg.|Número de llamadas salientes por segundo desde el adaptador al sistema de destino.|  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador creado mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)