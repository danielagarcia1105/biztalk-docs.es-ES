---
title: Limpiar el entorno de destino | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8585853b-e625-48c3-a241-81ebf1be0e1e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4023492bf79223b3ba6b1db5cedebadf88feb9c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="cleaning-the-destination-environment"></a>Limpiar el entorno de destino
Si el trabajo de restauración encuentra con condiciones de error que no se puede resolver, limpie el entorno de destino para que pueda iniciar desde un entorno vacío. Ejecuta el procedimiento almacenado **sp_LogShippingClean** ubicado en la base de datos maestra en el destino [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia se "limpia" el entorno de destino. Este procedimiento quita todas las bases de datos y elimina el último conjunto de datos restaurado para el origen especificado.  
  
 Antes de ejecutar este procedimiento, deshabilite la **envío de registro BTS - Restaurar bases de datos** trabajo (el trabajo de copia de seguridad del historial de get puede continuar la ejecución). Para obtener más información acerca de cómo deshabilitar el **envío de registro BTS - Restaurar bases de datos** trabajo vea [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md). Después de la **sp_LogShippingClean** se ejecuta el procedimiento, la próxima vez que se ejecuta el trabajo de restauración se encontrará la copia de seguridad completa más reciente con un conjunto de copia de seguridad de registros subsiguientes válido. Si este conjunto ya se ha restaurado, el trabajo de restauración borra la **restaurados** columna para el conjunto y la posterior establece y, a continuación, continúa con la restauración del conjunto.  
  
> [!NOTE]  
>  Dado que el trabajo busca la copia de seguridad completa más reciente establecer después de que se ha limpiado el entorno, forzar una copia de seguridad completa en el sistema de origen después de ejecutar este procedimiento, pero antes de ejecutar el trabajo de restauración.  
  
> [!NOTE]  
>  El **sp_LogShippingClean** procedimiento debe repetirse en todos los servidores que se va a restaurar las bases de datos para un sistema de origen especificado con el fin de mantener sincronizados entre sí en términos que se han aplicado los conjuntos de los diferentes servidores.  
  
 Para ejecutar el **sp_LogShippingClean** procedimiento, conéctese a la base de datos maestra en todos los [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias que forman parte de la recuperación ante desastres de sitio y ejecute el siguiente comando en el **nueva consulta** opción disponible en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio para cada [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia:  
  
```  
sp_LogShippingClean 'SourceID'  
```  
  
 donde **SourceID** corresponde al valor del identificador configurado en la producción [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de trasvase de registros](../technical-guides/troubleshooting-log-shipping.md)