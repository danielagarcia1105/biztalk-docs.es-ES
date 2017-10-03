---
title: "Listas de comprobación de preparación operativa | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87da295129a4cb90ecf643cd06eb18ac3e6aa18e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operational-readiness-checklists"></a>Listas de comprobación de preparación operativa
Las listas de comprobación de preparación operativa contienen recomendaciones que debe tener en cuenta y las tareas que se deben realizar antes de implementar una solución de BizTalk en producción. Estas listas de comprobación incluyen información para configurar el software de requisito previo, aumentar la disponibilidad, supervisión de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno y procedimientos para las pruebas.  
  
 Dado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mantiene las dependencias en muchas otras tecnologías de Microsoft, debe completar las tareas para cada tecnología dependiente ayudar a garantizar que su producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno se ejecuta sin problemas.  
  
## <a name="typical-prerequisite-software"></a>Requisitos previos de Software normal  
 Software requerido para la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plataforma de aplicaciones suele incluir los siguientes productos:  
  
-   El sistema operativo Windows  
  
-   [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]SP1 o[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)](para fines de desarrollo, no en tiempo de ejecución)  
  
## <a name="additional-components"></a>Componentes adicionales  
 El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plataforma de aplicaciones también puede necesitar varios de los siguientes componentes de software:  
  
-   Servicios de Internet Information Server (IIS)  
  
-   Windows SharePoint® Services 2010  
  
-   SharePoint Foundation 2010  
  
-   Microsoft Office SharePoint Server 2007 Service Pack 1 (SP1) (MOSS)  
  
-   Windows SharePoint Services 3.0 con SP1 o SP2  
  
-   Microsoft Office Excel 2010 o 2007  
  
    > [!NOTE]  
    >  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]admite solo la versión de 32 bits de Microsoft Office 2010.  
  
-   SQL Server 2005 Notification Services  
  
-   SQLXML 4.0 con Service Pack 1  
  
-   .NET framework 1.0  
  
-   .NET Framework 2.0  
  
-   .NET framework 3.0  
  
-   Microsoft .NET Framework 4 y .net Framework 3.5 con Service Pack 1 (SP1)  
  
-   Los componentes no son de Microsoft para habilitar la funcionalidad para determinados [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores.  
  
 Para obtener más información acerca del software de dependencia que se requiere para características específicas de la plataforma de aplicaciones de BizTalk para las distintas versiones de sistema operativo de Windows, vea la sección "Matriz de dependencia de características" en el [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] instalación y Guía de actualización de la versión de sistema operativo de Windows específica. El [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] están disponibles en las guías de instalación y actualización [http://go.microsoft.com/fwlink/?LinkID=152913](http://go.microsoft.com/fwlink/?LinkID=152913).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Lista de comprobación: Introducción a BizTalk Server](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [Lista de comprobación: Configurar Windows Server](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [Lista de comprobación: Configurar Internet Information Services](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [Lista de comprobación: Configurar SQL Server](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [Lista de comprobación: Configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [Lista de comprobación: Proporcionar una alta disponibilidad con tolerancia a errores o equilibrio de carga](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [Lista de comprobación: Aumentar la disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [Lista de comprobación: Supervisión preparación operativa](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [Lista de comprobación: Mantenimiento y solución de problemas de las bases de datos de servidor BizTalk Server](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [Lista de comprobación: Probar la preparación operativa](../technical-guides/checklist-testing-operational-readiness.md)