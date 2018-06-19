---
title: Planear la disponibilidad de la base de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa74257-4159-46f6-b538-f7e9083d74ad
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d77ce6572ace3617308a046a422a3422b2dd8df5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008445"
---
# <a name="planning-for-database-availability"></a>Planear la disponibilidad de la base de datos
El motor de mensajería de BizTalk Server garantiza que los procesos empresariales son confiables y perdurables por conservar procesar los datos de estado y de negocio a una base de datos de SQL Server que se conoce como la base de datos de BizTalk Messagebox. Dado que la confiabilidad y durabilidad de los datos persistentes es tan buena como almacén de datos subyacente, planificación de alta disponibilidad de las bases de datos de BizTalk Server es muy importante.  
  
## <a name="hardware-considerations"></a>Consideraciones acerca del hardware  
 Para garantizar la alta disponibilidad para las bases de datos de BizTalk Server, tenga en cuenta lo siguiente al planear de hardware:  
  
1.  Considere la posibilidad de implementar una red de área de almacenamiento (SAN) para alojar las bases de datos de BizTalk Server. Los discos de SAN se deberían configurar utilizando RAID topología 1 + 0 (una banda de conjuntos reflejados) si es posible para obtener el máximo rendimiento y alta disponibilidad. 
  
2.  Planear la instalación de varios equipos que ejecuten SQL Server para alojar las bases de datos de BizTalk Server. Varios equipos que ejecuten SQL Server será necesarios para SQL Server de agrupación en clústeres (recomendado) o donde se encuentran determinadas bases de datos de BizTalk Server en instancias de SQL Server de físicos independientes (también se recomienda).  
  
3.  Planear la instalación de uno o más equipos que ejecutan SQL Server para implementar para fines de recuperación ante desastres de trasvase de registros de SQL Server. BizTalk Server incorpora capacidades en espera de base de datos mediante el uso de SQL Server trasvase de registros. SQL Server trasvase de registros automatiza la copia de seguridad y restauración de archivos de registro de transacciones y de base de datos, lo que permite un servidor en espera reanudar el procesamiento de base de datos en caso de que se produce un error en el servidor de producción. Para obtener más información acerca de cómo implementar para fines de recuperación ante desastres de trasvase de registros de SQL Server, vea [¿qué es BizTalk Server del trasvase de registros?](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="software-considerations"></a>Consideraciones de software  
 Para garantizar la alta disponibilidad para las bases de datos de BizTalk Server, considere lo siguiente al planear de software: Plan instalar una versión y edición de SQL Server que es compatible con el soporte técnico o soporte técnico de trasvase de BizTalk de agrupación en clústeres de conmutación por error. Para obtener una lista completa de las características compatibles con las ediciones de SQL Server, vea [ediciones y las características admitidas](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016).
  
## <a name="high-availability-vs-disaster-recovery"></a>Vs alta disponibilidad. Recuperación ante desastres  
 Hay dos métodos distintos para aumentar la disponibilidad de un entorno de BizTalk Server: proporcionar una alta disponibilidad con tolerancia a errores y equilibrio de carga, o proporcionar disponibilidad con recuperación ante desastres. Mientras cada método aumenta la disponibilidad, una diferencia clave entre ellos es que tolerancia a errores o normalmente equilibrio de carga proporciona mucho más rápido tiempo de recuperación que recuperación ante desastres. Por lo tanto, una solución basada en una tolerancia a errores o equilibrio de carga normalmente se considera como proporcionar alta disponibilidad en lugar de simplemente proporcionar disponibilidad. Ambos métodos deben emplearse en un entorno de BizTalk Server de producción.  
  
 Proporcionar una alta disponibilidad para las bases de datos de BizTalk Server con tolerancia a errores con los clústeres de Windows. Para obtener más información acerca de cómo proporcionar alta disponibilidad para las bases de datos de BizTalk Server, vea [alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md).  
  
 Aumentar la disponibilidad con ante desastres trasvase de registros de recuperación mediante BizTalk Server. Para aumentar la disponibilidad de las bases de datos de BizTalk Server con recuperación ante desastres, siga los pasos descritos en el tema [lista de comprobación: aumentar la disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).