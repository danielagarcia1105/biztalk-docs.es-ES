---
title: "Supervisión de trabajos del Agente SQL Server y bases de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2eb5f318-10d3-4f43-991d-9bff2ebc20e2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c9991e7ebd61c72bbeb6a090b0497244da63e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-server-agent-jobs-and-databases"></a>Supervisar bases de datos y trabajos del Agente SQL Server
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]incluye varios [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente que realizan funciones importantes para mantener los servidores operativos y en buen estado. Por ello, debe supervisar el estado de funcionamiento de estos trabajos y garantizar que no se producen errores en su ejecución. Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración contiene reglas para supervisar elementos tales como bases de datos SQL y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente. Debe configurar el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración para una supervisión completa de todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente.  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración incluye dos reglas deshabilitadas para supervisar el estado de dos de lo más importante BizTalk [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente:  
  
-   Error crítico: Un trabajo del Agente SQL Server de BizTalk no se pudo: copia de seguridad de BizTalk Server  
  
-   Error crítico: Error en un trabajo de agente SQL Server de BizTalk: realiza el seguimiento de copia del mensaje  
  
 Para supervisar todos los BizTalk Server [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente desde la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración, debe habilitar estas reglas y cree reglas adicionales para otros trabajos que desea supervisar mediante el proceso siguiente.  
  
-   En la consola de administrador de Operations Manager, cree una copia de cualquiera de las dos reglas anteriores en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reglas principales de agrupar y cambiar el nombre de la regla de forma adecuada.  
  
-   En la sección de criterios de la regla, cambiar la comparación de comodín para el parámetro 1 correctamente.  
  
-   En algunos casos, los nombres de los trabajos son dependientes de nombres de base de datos creados por el usuario, por ejemplo, el nombre de la base de datos de cuadro de mensajes.  
  
-   La regla se puede destinar a un trabajo asociado con un único cuadro de mensajes o todos los cuadros de mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Cómo iniciar al Agente SQL Server](../technical-guides/how-to-start-the-sql-server-agent.md)