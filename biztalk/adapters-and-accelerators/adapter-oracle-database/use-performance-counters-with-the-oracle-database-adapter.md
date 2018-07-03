---
title: Utilice los contadores de rendimiento con el adaptador de base de datos de Oracle | Microsoft Docs
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
ms.openlocfilehash: eb1137487a87532f015bd9edbf20b95b5e493e77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978549"
---
# <a name="use-performance-counters-with-the-oracle-database-adapter"></a>Utilice los contadores de rendimiento con el adaptador de base de datos de Oracle
Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] los clientes pueden usar los contadores de rendimiento para medir el rendimiento de los adaptadores. El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación crea la categoría de contador de rendimiento **.NET adaptador de BizTalk para Oracle DB** junto con la instalación del [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
## <a name="lob-time-cumulative-performance-counter"></a>Contador de rendimiento de tiempo (acumulativo) de LOB  
 El **.NET adaptador de BizTalk para Oracle DB** categoría tiene un contador de rendimiento denominado el "LOB hora (acumulativo)". Este contador de rendimiento indica el tiempo, en milisegundos, que la biblioteca de cliente de línea de negocio que se tarda en completar una acción que inicia el adaptador. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] crea una instancia del contador de rendimiento en cualquiera de los siguientes patrones:  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 Donde podría ser "string":  
  
- Connection.Open  
  
- Connection.Close  
  
- Metadatos  
  
- Acción de mensaje. Por ejemplo, si la acción es `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert` , a continuación, la cadena será SCOTT. Table.EMP.Insert.  
  
  El origen de datos de Oracle es el mismo que el especificado en el URI de conexión.  
  
  Se ha inicializado el contador de rendimiento solo una vez que el adaptador realiza la primera llamada a la base de datos de Oracle. Además, la propiedad InstanceLifetime del contador de rendimiento se establece en 'Process', lo que significa que el contador de rendimiento deja de existir en cuanto finaliza el programa que crea el contador. Para obtener más información sobre la `InstanceLifetime property`, consulte [ http://go.microsoft.com/fwlink/p/?LinkId=104181 ](http://go.microsoft.com/fwlink/p/?LinkId=104181).  
  
> [!NOTE]
>  La precisión del contador de rendimiento de tiempo de LOB (acumulativo) es 16 milisegundos.  
  
## <a name="enabling-performance-counters"></a>Habilitar los contadores de rendimiento  
 Los contadores de rendimiento se pueden habilitar o deshabilitar estableciendo la propiedad de enlace **EnablePerformanceCounters**. Para habilitar los contadores de rendimiento, establezca el **EnablePerformanceCounters** enlazar la propiedad a **True**. Para deshabilitar los contadores de rendimiento, establezca **EnablePerformanceCounters** a **False**. De forma predeterminada, **EnablePerformanceCounters** está establecido en **False**.  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>Contadores de rendimiento y el SDK del adaptador LOB de WCF  
 Cambiar el valor de la **EnablePerformanceCounters** enlaza la propiedad también cambia el valor del contador de rendimiento correspondientes para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Además, la propiedad de enlace para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, mientras que para el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] es dinámico. Por lo tanto, si hay dos instancias de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enlace en el AppDomain y el **EnablePerformanceCounters** enlaza la propiedad se establece en **True** en uno y **False** en el otro, el contador de rendimiento específicas del adaptador estará habilitado en uno y deshabilitado en el otro. Sin embargo, dado que la propiedad de enlace para [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, o bien se establecerá en **True** o **False** dependiendo de qué valor se especifica en último lugar.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)