---
title: Listas de comprobación de preparación operativa | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76cab24c2ba0d47baa22dbe694a1d929e98c8f9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002757"
---
# <a name="operational-readiness-checklists"></a>Listas de comprobación de preparación operativa
Las listas de comprobación de preparación operativa contienen recomendaciones que debe tener en cuenta y las tareas que debe realizar antes de implementar una solución de BizTalk en producción. Estas listas de comprobación incluyen información para configurar los requisitos previos de software, aumentar la disponibilidad, supervisión del [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno y los procedimientos para probar.  
  
 Dado que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mantiene las dependencias en por lo que muchas otras tecnologías de Microsoft, debe completar las tareas de cada tecnología dependiente ayudar a garantizar que su producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno se ejecuta sin problemas.  
  
## <a name="typical-prerequisite-software"></a>Requisitos previos de Software normal  
 Requisitos previos de software para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plataforma de aplicaciones normalmente incluye los siguientes productos:  
  
- El sistema operativo de Windows  
  
- SQL Server 
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- Visual Studio (para fines de desarrollo, no en tiempo de ejecución)  
  
## <a name="additional-components"></a>Componentes adicionales  
 El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plataforma de aplicaciones también puede requerir algunos de los componentes de software siguientes:  
  
- Servicios de Internet Information Server (IIS)  
  
- SharePoint
  
- Microsoft Office Excel 
  
  > [!NOTE]  
  >  BizTalk Server admite solo la versión de 32 bits de Microsoft Office.  
  
- SQL Server
  
- SQLXML 
  
- .NET Framework 
  
- Los componentes que no son de Microsoft para habilitar la funcionalidad para determinados [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptadores.  
  
  Para obtener más información acerca del software de dependencia que es necesario para características específicas de la plataforma de aplicaciones de BizTalk para las distintas versiones de sistema operativo Windows, consulte [What ' s New, instalación, configuración y actualización](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).
- 
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Lista de comprobación: introducción a BizTalk Server](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [Lista de comprobación: configuración de Windows Server](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [Lista de comprobación: configuración de Internet Information Services](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [Lista de comprobación: configuración de SQL Server](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [Lista de comprobación: configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [Lista de comprobación: proporcionar una alta disponibilidad con la tolerancia a errores o el equilibrio de carga](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [Lista de comprobación: aumento de la disponibilidad con la recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [Lista de comprobación: supervisión de la preparación operativa](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [Lista de comprobación: mantenimiento y solución de problemas de las bases de datos de BizTalk Server](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [Lista de comprobación: probar la preparación operativa](../technical-guides/checklist-testing-operational-readiness.md)