---
title: Utilice los contadores de rendimiento con el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae381b78-d89e-4cf2-810b-821e49422463
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f81189e34346d377686dac79b44e5a9b34889dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965522"
---
# <a name="use-performance-counters-with-the-sql-adapter"></a>Utilice los contadores de rendimiento con el adaptador de SQL
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]los clientes pueden utilizar los contadores de rendimiento para medir el rendimiento de los adaptadores. El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación crea la categoría de contador de rendimiento "[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]" junto con la instalación del Adapter Pack.  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>El contador de rendimiento de tiempo (acumulado) de LOB  
 El **BizTalk Adapter de .NET para SQL** categoría tiene un contador de rendimiento denominado "Tiempo de LOB (acumulado)". Este contador de rendimiento indica el tiempo, en milisegundos, que la biblioteca de cliente de SQL Server que se tarda en completar una acción que inicia el adaptador. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] crea una instancia del contador de rendimiento para cada acción, para un nombre de instancia y base de datos de SQL Server. Las instancias se crean en el siguiente patrón:  
  
```  
<processId>:<appDomainId>:<endpointId>:<actionId>  
```  
  
 El `<endpointId>` se deriva como `<sql_server_name>, <instance_name>, <database_name>`.  
  
 El \<actionId\> se deriva de la siguiente manera:  
  
-   Para abrir una conexión, el identificador de acción está "Abierta".  
  
-   Para las operaciones de entrada, el identificador de acción es "Inbound".  
  
-   Para las operaciones de salida, el Id. de acción es la acción de la operación que se invoca, con "/" reemplaza por un carácter de subrayado "_". Además, el identificador de acción tiene como prefijo el "ExecuteScalar", "ExecuteReader" o "ExecuteNonQuery" según el método que el adaptador se usa internamente para realizar la operación en la base de datos de SQL Server. Por ejemplo, el adaptador utiliza internamente el **ExecuteReader** método para ejecutar un procedimiento almacenado en SQL Server. Por lo tanto, el identificador de acción para el procedimiento almacenado, MyProcedure, será:  
  
    ```  
    ExecuteReader_Procedure_dbo_MyProcedure  
    ```  

 El contador de rendimiento se inicializa solo una vez que el adaptador realiza la primera llamada a la base de datos de SQL Server. Además, el [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) propiedad del contador de rendimiento está establecida en 'Process', lo que significa que el contador de rendimiento deja de existir en cuanto finaliza el programa que crea el contador.
  
> [!NOTE]
>  La precisión del contador de rendimiento de tiempo de LOB (acumulado) es 16 milisegundos.  
  
## <a name="enabling-performance-counters"></a>Habilitar los contadores de rendimiento  
 Los contadores de rendimiento se pueden habilitar o deshabilitar estableciendo la propiedad de enlace **EnablePerformanceCounters**. Para habilitar los contadores de rendimiento, establezca la **EnablePerformanceCounters** enlazar la propiedad a **True**. Para deshabilitar los contadores de rendimiento, establezca **EnablePerformanceCounters** a **False**. De forma predeterminada, la propiedad se establece en **False**. Para obtener más información acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>Contadores de rendimiento y el SDK del adaptador LOB de WCF  
 Cambiar el valor de la **EnablePerformanceCounters** enlaza la propiedad también cambia el valor del contador de rendimiento correspondientes para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Además, la propiedad de enlace para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, mientras que para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es dinámico. Por lo tanto, si hay dos instancias de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace en el dominio de aplicación y el **EnablePerformanceCounters** enlaza la propiedad se establece en **True** en uno y **False** en el otro, el contador de rendimiento específicas del adaptador estará habilitado en una y deshabilitado en el otro. Sin embargo, dado que la propiedad de enlace para [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, o bien se establece como **True** o **False** dependiendo de qué valor se especifica en último lugar.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador SQL](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)