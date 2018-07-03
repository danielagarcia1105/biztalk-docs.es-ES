---
title: Utilice los contadores de rendimiento con el adaptador de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7d722b7-8343-4956-81ed-acd5a463a9b1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4b2c187dbc33a441de8d11d489c5377c0c4e742
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985013"
---
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a>Utilice los contadores de rendimiento con el adaptador de Oracle E-Business Suite
Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] los clientes pueden usar los contadores de rendimiento para medir el rendimiento de los adaptadores. El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación crea la categoría de contador de rendimiento **.NET adaptador de BizTalk para Oracle E-Business Suite** junto con la instalación del [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
## <a name="lob-time-cumulative-performance-counter"></a>Contador de rendimiento de línea de negocio tiempo (acumulativo)  
 El **.NET adaptador de BizTalk para Oracle E-Business Suite** categoría tiene un contador de rendimiento denominado el "LOB hora (acumulativo)". Este contador de rendimiento indica el tiempo, en milisegundos, que la biblioteca de cliente de línea de negocio que se tarda en completar una acción que inicia el adaptador. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] crea una instancia del contador de rendimiento en cualquiera de los siguientes patrones:  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 Donde podría ser "string":  
  
- Connection.Open  
  
- Connection.Close  
  
- Metadatos  
  
- Acción de mensaje. Por ejemplo, si la acción es `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE` , a continuación, la cadena será InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE.  
  
  El origen de datos de Oracle es el mismo que el especificado en el URI de conexión.  
  
  Se ha inicializado el contador de rendimiento solo una vez que el adaptador realiza la primera llamada a la base de datos de Oracle. Además, la propiedad InstanceLifetime del contador de rendimiento se establece en 'Process', lo que significa que el contador de rendimiento deja de existir en cuanto finaliza el programa que crea el contador. 
  
> [!NOTE]
>  La precisión del contador de rendimiento de tiempo de LOB (acumulativo) es 16 milisegundos.  
  
## <a name="enabling-performance-counters"></a>Habilitar los contadores de rendimiento  
 Los contadores de rendimiento se pueden habilitar o deshabilitar estableciendo la propiedad de enlace **EnablePerformanceCounters**. Para habilitar los contadores de rendimiento, establezca el **EnablePerformanceCounters** enlazar la propiedad a **True**. Para deshabilitar los contadores de rendimiento, establezca **EnablePerformanceCounters** a **False**. De forma predeterminada, **EnablePerformanceCounters** está establecido en **False**.  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>Contadores de rendimiento y el SDK del adaptador LOB de WCF  
 Cambiar el valor de la **EnablePerformanceCounters** enlaza la propiedad también cambia el valor del contador de rendimiento correspondientes para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Además, la propiedad de enlace para el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, mientras que para el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] es dinámico. Por lo tanto, si hay dos instancias de la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace en el AppDomain y el **EnablePerformanceCounters** enlaza la propiedad se establece en **True** en uno y **False** en el otro, el contador de rendimiento específicas del adaptador estará habilitado en uno y deshabilitado en el otro. Sin embargo, dado que la propiedad de enlace para [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es estático, o bien se establecerá en **True** o **False** dependiendo de qué valor se especifica en último lugar.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)