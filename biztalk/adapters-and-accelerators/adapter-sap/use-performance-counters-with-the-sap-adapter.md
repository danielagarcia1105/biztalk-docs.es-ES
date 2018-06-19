---
title: Utilizar contadores de rendimiento con el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, using
- troubleshooting, using performance counters
ms.assetid: 2749add3-31f1-47ff-b3b4-ef46c76fa533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbc7ed347bc81a8a00ff7faa826bd48203c47e63
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962258"
---
# <a name="use-performance-counters-with-the-sap-adapter"></a>Utilizar contadores de rendimiento con el adaptador SAP
Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] los clientes pueden usar los contadores de rendimiento para medir el rendimiento de los adaptadores. El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación crea la categoría de contador de rendimiento "[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]" a lo largo de instalar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
## <a name="lob-time-cumulative-performance-counter"></a>Contador de rendimiento de tiempo (acumulado) de LOB  
 El **el adaptador de BizTalk .NET para SAP** categoría tiene un contador de rendimiento denominado el "tiempo LOB (acumulado)". Este contador de rendimiento indica el tiempo, en milisegundos, que la biblioteca de cliente LOB que se tarda en completar una acción que inicia el adaptador. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] crea una instancia del contador de rendimiento en el patrón siguiente:  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 El identificador de punto de conexión podría ser:  
  
-   Para las llamadas desde el adaptador al sistema SAP (saliente)  
  
    -   A,\<host de servidor de aplicación\>,\<número del sistema\>  
  
    -   B,\<host de servidor de mensaje\>,\<R3NAME\>  
  
    -   D.,\<destino\>  
  
-   Para las llamadas desde el sistema SAP para el adaptador (entrada)  
  
    -   I,\<host de puerta de enlace\>,\<servidor de puerta de enlace\>  
  
    -   Id.,\<destino\>  
  
 El identificador de acción podría ser:  
  
-   \<Nombre RFC\> (para una llamada de RFC)  
  
-   T,\<nombre RFC\> (para una llamada tRFC)  
  
 El contador de rendimiento se inicializa solo una vez que el adaptador realiza la primera llamada al sistema SAP. Además, el [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) propiedad del contador de rendimiento está establecida en 'Process', lo que significa que el contador de rendimiento deja de existir en cuanto finaliza el programa que crea el contador.
  
> [!NOTE]
>  La precisión del contador de rendimiento de tiempo de LOB (acumulado) es 16 milisegundos.  
  
## <a name="enabling-performance-counters"></a>Habilitar los contadores de rendimiento  
 Los contadores de rendimiento se pueden habilitar o deshabilitar estableciendo la propiedad de enlace *EnablePerformanceCounters*. Para habilitar los contadores de rendimiento, establezca la *EnablePerformanceCounters* enlazar la propiedad a **True**. Para deshabilitar los contadores de rendimiento, establezca *EnablePerformanceCounters* a **False**. De forma predeterminada, *EnablePerformanceCounters* está establecido en **False**.  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>Contadores de rendimiento y el SDK del adaptador LOB de WCF  
 Cambiar el valor de la *EnablePerformanceCounters* enlaza la propiedad también cambia el valor del contador de rendimiento correspondientes para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Además, la propiedad de enlace para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, mientras que para el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] es dinámico. Por lo tanto, si hay dos instancias de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace en el AppDomain y *EnablePerformanceCounters* enlaza la propiedad se establece en **True** en uno y **False**en el otro, el contador de rendimiento específicas del adaptador estará habilitado en una y deshabilitado en el otro. Sin embargo, dado que la propiedad de enlace para [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, o bien se establece como **True** o **False** dependiendo de qué valor se especifica en último lugar.  
  
## <a name="see-also"></a>Vea también  

[Solucionar problemas del adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)