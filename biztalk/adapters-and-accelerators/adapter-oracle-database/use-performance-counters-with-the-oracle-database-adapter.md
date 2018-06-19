---
title: Utilizar contadores de rendimiento con el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, using
- performance counter, LOB Time Cumulative
- performance counters, enabling
- performance counters, and the WCF LOB Adapter SDK
ms.assetid: beb80896-7594-411e-a83c-169d5278e2ce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce36fe948daeb89d8fc248dbe33191aa69cdd9ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215188"
---
# <a name="use-performance-counters-with-the-oracle-database-adapter"></a>Utilizar contadores de rendimiento con el adaptador de la base de datos de Oracle
Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] los clientes pueden usar los contadores de rendimiento para medir el rendimiento de los adaptadores. El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación crea la categoría de contador de rendimiento **BizTalk Adapter de .NET para Oracle DB** junto con la instalación del [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
## <a name="lob-time-cumulative-performance-counter"></a>Contador de rendimiento de tiempo (acumulado) de LOB  
 El **BizTalk Adapter de .NET para Oracle DB** categoría tiene un contador de rendimiento denominado el "LOB tiempo (acumulado)". Este contador de rendimiento indica el tiempo, en milisegundos, que la biblioteca de cliente LOB que se tarda en completar una acción que inicia el adaptador. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] crea una instancia del contador de rendimiento en cualquiera de los siguientes modelos:  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 Donde "cadena" podría ser:  
  
-   Connection.Open  
  
-   Connection.Close  
  
-   Metadatos  
  
-   Acción de mensaje. Por ejemplo, si la acción es `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert` , a continuación, la cadena será SCOTT. Table.EMP.Insert.  
  
 El origen de datos de Oracle es el mismo que el especificado en el URI de conexión.  
  
 El contador de rendimiento se inicializa solo una vez que el adaptador realiza la primera llamada a la base de datos de Oracle. Además, la propiedad InstanceLifetime del contador de rendimiento se establece en 'Process', lo que significa que el contador de rendimiento deja de existir en cuanto finaliza el programa que crea el contador. Para obtener más información sobre la `InstanceLifetime property`, consulte [http://go.microsoft.com/fwlink/p/?LinkId=104181](http://go.microsoft.com/fwlink/p/?LinkId=104181).  
  
> [!NOTE]
>  La precisión del contador de rendimiento de tiempo de LOB (acumulado) es 16 milisegundos.  
  
## <a name="enabling-performance-counters"></a>Habilitar los contadores de rendimiento  
 Los contadores de rendimiento se pueden habilitar o deshabilitar estableciendo la propiedad de enlace **EnablePerformanceCounters**. Para habilitar los contadores de rendimiento, establezca la **EnablePerformanceCounters** enlazar la propiedad a **True**. Para deshabilitar los contadores de rendimiento, establezca **EnablePerformanceCounters** a **False**. De forma predeterminada, **EnablePerformanceCounters** está establecido en **False**.  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>Contadores de rendimiento y el SDK del adaptador LOB de WCF  
 Cambiar el valor de la **EnablePerformanceCounters** enlaza la propiedad también cambia el valor del contador de rendimiento correspondientes para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Además, la propiedad de enlace para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, mientras que para el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] es dinámico. Por lo tanto, si hay dos instancias de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enlace en el AppDomain y **EnablePerformanceCounters** enlaza la propiedad se establece en **True** en uno y **False** en el otro, el contador de rendimiento específicas del adaptador estará habilitado en una y deshabilitado en el otro. Sin embargo, dado que la propiedad de enlace para [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, o bien se establece como **True** o **False** dependiendo de qué valor se especifica en último lugar.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)