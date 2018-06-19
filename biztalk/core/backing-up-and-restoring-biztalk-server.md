---
title: Copia de seguridad y restauración de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe03a75a-1ea6-4ccc-9543-7989ec6b1cff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1adac25b23c69b51e07ed5f30768d046a453887a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230788"
---
# <a name="backing-up-and-restoring-biztalk-server"></a>Realizar una copia de seguridad y una restauración de BizTalk Server
Si se produce un error de hardware, es esencial tener una buena copia de seguridad de las bases de datos y de los componentes de BizTalk Server. Una buena copia de seguridad le permitirá recuperar la información en la que la pérdida de datos será mínima o ninguna. El modo de restaurar BizTalk Server depende de los componentes que se han instalado en el sistema en el que ha ocurrido el error. En esta guía se tratan los siguientes escenarios de error de hardware:  
  
 **Error de hardware en el equipo que ejecuta BizTalk Server**  
  
 Un error de hardware en el equipo que ejecuta BizTalk Server puede hacer que se interrumpa la actividad del sistema o disminuya el rendimiento, si el grupo de BizTalk no se ha diseñado para obtener alta disponibilidad. Para obtener más información sobre cómo crear un grupo de BizTalk de alta disponibilidad, vea [planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md).  
  
 Para asegurarse de que puede sustituir un equipo que ejecuta BizTalk Server después de que se produzca un error de hardware, debe realizar una copia de seguridad de los componentes de BizTalk Server en dicho equipo. Para obtener más información acerca de cómo realizar copias de y restaurar un equipo que ejecuta BizTalk Server, vea [realizar una copia de seguridad de un equipo ejecuta BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) y [recuperación de un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md).  
  
 **Error de hardware en el equipo que ejecuta SQL Server**  
  
 Puede minimizar el riesgo de que se produzca un error de hardware en un equipo que ejecuta SQL Server mediante la utilización de organización por clústeres de SQL Server. Incluso cuando se utiliza la organización por clústeres de SQL Server, puede haber situaciones en las que se produzca un error irrecuperable en los servidores SQL Server que contienen las bases de datos. Por ejemplo, todos los niveles de los datos se han visto afectados por un error. En estas situaciones, debe reactivar el grupo de BizTalk mediante la restauración del conjunto de bases de datos de las que se ha realizado una copia de seguridad más reciente.  
  
 Para obtener más información acerca de cómo proporcionar tolerancia a errores para las bases de datos de BizTalk Server, vea [proporcionar una alta disponibilidad para bases de datos de BizTalk Server](../core/providing-high-availability-for-biztalk-server-databases.md). En el caso de un error grave de SQL Server donde se ha producido un tiempo de inactividad, debe seguir las instrucciones en [copia de seguridad y restaurar las bases de datos de BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md).  
  
 En caso de que se produzca un error de hardware en un equipo en el que se ha instalado SQL Server y BizTalk Server, debe restaurar las bases de datos de BizTalk Server y, a continuación, recuperar sus componentes.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Lista de comprobación: Copia de seguridad y restauración](../core/checklist-backup-and-restore.md)  
  
-   [Prácticas recomendadas para la copia de seguridad y restauración](../core/best-practices-for-backup-and-restore.md)  
  
-   [Copia de seguridad y restaurar las bases de datos de servidor BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [Recuperación ante desastres para equipos que ejecutan BizTalk Server](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [Recuperar un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)