---
title: "Preparar los servidores SQL de recuperación ante desastres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44b77fe8-393d-4781-b0b0-5b7f6e50a67b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e6021b7114b8b57c62dadfe742be1809df0bd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-the-disaster-recovery-sql-servers"></a>Preparar los servidores SQL de recuperación ante desastres
Crea el conjunto de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias en el sitio de recuperación ante desastres de bases de datos. Para asegurarse de que la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias de base de datos pueden proporcionar el mismo nivel de rendimiento a medida que la producción [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias de base de datos, la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias de base de datos deben configurarse con similares hardware y el número de equipos físicos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. En este escenario, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] trasvase de registros se configurará para cada producción [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia de base de datos para aplicar a su correspondiente [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia de base de datos en el sitio de recuperación ante desastres.  
  
 Una clave [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] requisito de trasvase de registros es que las letras de unidad especificadas en el sitio de producción donde se almacenan los archivos de base de datos coinciden con las letras de unidad especificadas en el sitio de recuperación ante desastres donde se restauran los archivos de base de datos. Por tanto, si la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] grupo de archivos de base de datos se encuentra en G:\data en producción, debe haber un directorio G:\data en el servidor de destino (DR) o se producirá un error en la restauración.  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]trasvase de registros no es compatible con la **RESTORE WITH MOVE** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] comando. Por este motivo, se recomienda que los nombres de instancia de base de datos en el sitio de recuperación ante desastres coinciden con los nombres de instancia de base de datos de producción (de forma predeterminada, el nombre de instancia es parte de la ruta de acceso de archivo). Otra opción consiste en crear simplemente un directorio en la letra de unidad correspondiente en el equipo de recuperación ante desastres con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para que la **restaurar** operación puede crear el archivo en la misma estructura de directorios, tal como se utiliza en producción.  
  
 Crear [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] seguridad los inicios de sesión para el sitio de recuperación ante desastres que se corresponden con el sitio de producción para que en caso de que una conmutación por error en el sitio de recuperación ante desastres es necesario, todos los inicios de sesión de seguridad de necesarios están presentes en el sistema de destino.  
  
 Una vez la instalación de la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias se ha completado, lleve a cabo una copia de seguridad completa de las bases de datos master y msdb para que un sistema limpio puede restaurarse en caso de que se produce un error en un cambio en el sitio de recuperación ante desastres.