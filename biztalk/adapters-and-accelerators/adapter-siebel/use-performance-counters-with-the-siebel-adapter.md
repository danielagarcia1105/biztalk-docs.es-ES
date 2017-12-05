---
title: Utilizar contadores de rendimiento con el adaptador de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters, troubleshooting
- troubleshooting, performance counters
- performance counters, using
ms.assetid: 7930e8f6-5099-4a9c-b38a-13c9902635a6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bebbd605df52e023c78112b78ad51db13d896cc7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="use-performance-counters-with-the-siebel-adapter"></a>Utilizar contadores de rendimiento con el adaptador de Siebel
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]los clientes pueden utilizar los contadores de rendimiento para medir el rendimiento de los adaptadores. El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación crea la categoría de contador de rendimiento "[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]" junto con la instalación del Adapter Pack.  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>El contador de rendimiento de tiempo (acumulado) de LOB  
 El **.NET adaptador de BizTalk para Siebel** categoría tiene un contador de rendimiento denominado "Tiempo de LOB (acumulado)". Este contador de rendimiento indica el tiempo, en milisegundos, que la biblioteca de cliente LOB que se tarda en completar una acción que inicia el adaptador. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] crea una instancia del contador de rendimiento para cada acción, para un nombre de servidor concreto de Siebel. Las instancias se crean en el siguiente patrón:  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 En caso de los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], Id. de extremo es el nombre del servidor de Siebel, como se especifica en el URI de conexión. El identificador de acción podría ser cualquier acción realizada por el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] como inicio de sesión, cierre de sesión, metadatos, \<nombre del componente empresarial\>.\< operación\>, \<nombre de servicio de negocios\>.\< método de servicio de negocio\>. Si la convención de nomenclatura anterior da como resultado un nombre que supera los 127 caracteres solo el identificador de acción se muestra en el siguiente formato:  
  
```  
:::<action id>  
```  
  
 Si `:::<action id>` también supera los 127 caracteres, se recorta hasta 127 caracteres.  
  
 El contador de rendimiento se inicializa solo una vez que el adaptador realiza la primera llamada al sistema Siebel. Además, el **InstanceLifetime** propiedad del contador de rendimiento está establecida en 'Process', lo que significa que el contador de rendimiento deja de existir en cuanto finaliza el programa que crea el contador. 
  
> [!NOTE]
>  La precisión del contador de rendimiento de tiempo de LOB (acumulado) es 16 milisegundos.  
  
## <a name="enabling-performance-counters"></a>Habilitar los contadores de rendimiento  
 Los contadores de rendimiento se pueden habilitar o deshabilitar estableciendo la propiedad de enlace **EnablePerformanceCounters**. Establecer **EnablePerformanceCounters** enlazar la propiedad a **True** para habilitar los contadores de rendimiento. Para deshabilitar los contadores de rendimiento, establezca **EnablePerformanceCounters** a **False**. De forma predeterminada, **EnablePerformanceCounters** está establecido en **False**.  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>Contadores de rendimiento y el SDK del adaptador LOB de WCF  
 Cambiar el valor de la **EnablePerformanceCounters** cambios en el valor del contador de rendimiento correspondientes para las propiedades de enlace [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Además, la propiedad de enlace para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, mientras que para el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] es dinámico. Por lo tanto, si hay dos instancias de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace en el AppDomain y **EnablePerformanceCounters** enlaza la propiedad se establece en **True** en uno y **False**en el otro, el contador de rendimiento específicas del adaptador estará habilitado en una y deshabilitado en el otro. Sin embargo, dado que la propiedad de enlace para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, o bien se establece como **True** o **False**, dependiendo de qué valor se especifica en último lugar.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)