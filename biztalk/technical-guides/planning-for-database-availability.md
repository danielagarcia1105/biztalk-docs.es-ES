---
title: Planear la disponibilidad de la base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aa74257-4159-46f6-b538-f7e9083d74ad
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea5aa21ad9db78236d7b1e5335053b7c9ce28770
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-database-availability"></a>Planear la disponibilidad de la base de datos
El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] motor de mensajería garantiza que los procesos empresariales son confiables y perdurables por conservar procesar los datos de estado y empresariales a un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] base de datos que se conoce como la base de datos de BizTalk Messagebox. Dado que la confiabilidad y durabilidad de los datos persistentes es tan buena como almacén de datos subyacente, planificación de alta disponibilidad de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es muy importante que las bases de datos.  
  
## <a name="hardware-considerations"></a>Consideraciones acerca del hardware  
 Para garantizar la alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, considere lo siguiente al planear de hardware:  
  
1.  Considere la posibilidad de implementar una red de área de almacenamiento (SAN) para alojar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Los discos de SAN se deberían configurar utilizando RAID topología 1 + 0 (una banda de conjuntos reflejados) si es posible para obtener el máximo rendimiento y alta disponibilidad. Para obtener más información sobre cómo usar una SAN para alojar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vea bases de datos de la [optimización de base de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=101578) notas del producto ([http://go.microsoft.com/fwlink/?LinkID=101578](http://go.microsoft.com/fwlink/?LinkID=101578)).  
  
2.  Planear la instalación de varios equipos que ejecuten [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] a casa el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Varios equipos que ejecuten [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] será necesaria para [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] agrupación en clústeres (recomendado) o del alojamiento determinados [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos físicas independientes [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias (también se recomienda).  
  
3.  Plan acerca de cómo instalar uno o más equipos que ejecuten [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] implementar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trasvase para fines de recuperación ante desastres de registros. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]capacidades en espera mediante el uso de la base de datos implementa [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trasvase de registros. [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]trasvase de registros automatiza la copia de seguridad y restauración de archivos de registro de transacciones y de base de datos, lo que permite un servidor en espera reanudar el procesamiento de base de datos en caso de que se produce un error en el servidor de producción. Para obtener más información acerca de cómo implementar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trasvase para fines de recuperación ante desastres de registros, vea [¿qué es BizTalk Server del trasvase de registros?](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="software-considerations"></a>Consideraciones de software  
 Para garantizar la alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, considere lo siguiente al planear de software: Plan instalar una versión y edición de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] que es compatible con el soporte técnico o soporte técnico de trasvase de BizTalk de agrupación en clústeres de conmutación por error. Para obtener una lista completa de las características admitidas por las ediciones de [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], consulte [características compatibles con las ediciones de SQL Server 2008](http://go.microsoft.com/fwlink/?LinkId=151940) ([http://go.microsoft.com/fwlink/? LinkId = 151940](http://go.microsoft.com/fwlink/?LinkId=151940)) en el [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] documentación.  
  
## <a name="high-availability-vs-disaster-recovery"></a>Vs alta disponibilidad. Recuperación ante desastres  
 Hay dos métodos distintos para aumentar la disponibilidad de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno: proporcionar una alta disponibilidad con tolerancia a errores y equilibrio de carga, o proporcionar disponibilidad con recuperación ante desastres. Mientras cada método aumenta la disponibilidad, una diferencia clave entre ellos es que tolerancia a errores o normalmente equilibrio de carga proporciona mucho más rápido tiempo de recuperación que recuperación ante desastres. Por lo tanto, una solución basada en una tolerancia a errores o equilibrio de carga normalmente se considera como proporcionar alta disponibilidad en lugar de simplemente proporcionar disponibilidad. Ambos métodos se deberían emplearse en producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
 Proporcionar una alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos con tolerancia a errores con los clústeres de Windows. Para obtener más información acerca de cómo proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md).  
  
 Aumentar la disponibilidad con recuperación ante desastres mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros. Para aumentar la disponibilidad de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos con recuperación ante desastres, siga los pasos descritos en el tema [lista de comprobación: aumentar la disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).