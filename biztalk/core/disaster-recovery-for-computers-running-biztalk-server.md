---
title: "Recuperación ante desastres para equipos que ejecutan BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10a2c26d-55d5-45d1-9fb1-e0664f005c21
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac655c10aaa443f9971fc40f7301a9e608e0e7eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="disaster-recovery-for-computers-running-biztalk-server"></a>Recuperación ante desastres para equipos que ejecutan BizTalk Server
Si se produce un error de hardware irrecuperable en el equipo de la organización en el que se ejecuta BizTalk Server, será preciso sustituirlo con un equipo idéntico. En este caso, se presume que las bases de datos de BizTalk Server se encuentran intactas y que el error se ha producido en cualquiera de los equipos en los que se ejecuta BizTalk Server.  
  
 Un posible enfoque de este supuesto consiste en mantener una imagen actualizada de cada uno de los equipos de la instalación en los que se ejecuta BizTalk Server. Cuando se produce un error de hardware en un equipo, la única acción de recuperación requerida es implementar la imagen almacenada en un nuevo equipo. Los temas de recuperación ante desastres tratan el caso en el que este almacenamiento no es factible.  
## <a name="recovering-different-editions-of-biztalk-server"></a>Recuperar distintas ediciones de BizTalk Server  
 El enfoque de recuperación varía en función de la edición de BizTalk Server que se ejecute en el equipo.  
  
 Para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Developer Edition y [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Enterprise Edition, se permiten varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Cuando se produce un error en alguno de los equipos en los que se ejecuta BizTalk Server, se puede preparar un equipo de sustitución y unirlo al grupo de BizTalk existente. En este caso, se puede unir al grupo de BizTalk un equipo con un nombre idéntico o distinto.  
  
 En el caso de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Standard Edition, no es posible unir el equipo a un grupo de BizTalk, de modo que el enfoque anterior no resulta adecuado. En lugar de ello, se indican los pasos necesarios para instalar un nuevo equipo y restaurar los valores de configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que funcione como sustituto. Para obtener más información, consulte [cómo recuperar el grupo de BizTalk](../core/how-to-recover-the-biztalk-group.md).  
  
## <a name="recovery-phases"></a>Fases de recuperación  
 En la recuperación de un equipo en el que se ejecute BizTalk Server, se pueden diferenciar las tres fases siguientes:  
  
1.  **Preparación de la plataforma Base**  
  
     En esta fase, se incluye la preparación de un equipo con la plataforma base, incluido el sistema operativo, los requisitos previos de software y los componentes de BizTalk Server apropiados. En esta guía, se supone que, antes de intentar restaurar la configuración de BizTalk Server, se dispone de un equipo con la plataforma base, los requisitos previos y los componentes de BizTalk Server instalados. Esta guía no trata la restauración de la plataforma base.  
  
2.  **Restaurar la configuración de servidor BizTalk Server**  
  
     En esta fase, se da por supuesto que se dispone de un registro de las características configuradas en el equipo en el que se produjo el error, incluida una copia del archivo de configuración de BizTalk Server para ese equipo. En esta guía, se ofrecen directrices para efectuar la restauración de la configuración de BizTalk Server.  
  
3.  **Restauración de aplicaciones de BizTalk**  
  
     En esta fase, se efectúa la restauración de los ensamblados .NET conectados con las aplicaciones alojadas por los procesos de BizTalk Server en el equipo de sustitución. Los artefactos que resulten necesarios, como los ensamblados de usuario, aparte de los ensamblados de BizTalk, deberían instalarse en sus ubicaciones respectivas o en la caché de ensamblados global (GAC) del equipo. En esta guía, se proporcionan algunas directrices para esta fase. No obstante, no hay secuencias de comandos o herramientas independientes para la restauración de aplicaciones de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad y restauración de BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)