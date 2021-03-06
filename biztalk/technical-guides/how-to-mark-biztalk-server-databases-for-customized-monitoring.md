---
title: Cómo las bases de datos de marca el servidor BizTalk Server para la supervisión personalizada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfbdc73d-a108-42ee-a5d8-401d5bfe5e7d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea069140b9dd89fafa13fe57be9eefa17eceb790
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023714"
---
# <a name="how-to-mark-biztalk-server-databases-for-customized-monitoring"></a>Cómo marcar bases de datos de BizTalk Server para la supervisión personalizada
Si ha instalado Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración, puede personalizar la forma [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se supervisan las bases de datos. Esto garantiza que el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración supervisa los siguientes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos:  
  
-   Base de datos de archivo de BAM (BAMArchive)  
  
-   Base de datos de importación principal de BAM BAMPrimaryImport  
  
-   Base de datos de esquema de estrella (BAMStarSchema)  
  
-   Base de datos de seguimiento de BizTalk (BizTalkDTADb)  
  
-   Base de datos de administración de BizTalk  (BizTalkMgmtDb)  
  
-   Base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb)  
  
-   Base de datos del motor de reglas (BizTalkRuleEngineDb)  
  
-   Base de datos de inicio de sesión único empresarial (SSODB)  
  
> [!NOTE]
>  Debe haber iniciado sesión como un miembro del rol de Operations Manager Advanced Operator o [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] grupo de administración.  
  
### <a name="to-mark-biztalk-server-databases-for-customized-monitoring"></a>Para marcar las bases de datos de BizTalk Server para la supervisión personalizada  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **System Center Operations Manager 2007**y, a continuación, haga clic en **consola del operador**.  
  
2. En la consola del operador, haga clic en el **Authoring** botón.  
  
3. En el **Authoring** panel, expanda **objetos del módulo de administración**y, a continuación, haga clic en **detecciones de objetos**.  
  
4. Para buscar una detección para SQL Server, en la barra de herramientas de la consola de operador, haga clic en **buscar**y en el **buscar** cuadro de texto escriba **SQL 2008** para buscar SQL Server 2008.  
  
5. En el **tipo detectado: SQL 2008 DB** categoría, seleccione **detectar bases de datos de un motor de base de datos**.  
  
6. En la barra de herramientas de la consola de operaciones, haga clic en **invalida** y, a continuación, elija **invalidar la detección de objetos**. Puede elegir invalidar la detección para los objetos de un tipo específico o para todos los objetos dentro de un grupo. Después de elegir qué grupo de tipo de objeto va a invalidar, el **propiedades de invalidación** abre el cuadro de diálogo.  
  
   > [!NOTE]  
   >  Si el **invalida** botón no está disponible, asegúrese de que ha seleccionado un monitor y no un objeto contenedor en el panel monitores.  
  
7. Active la casilla situada en la **invalidar** columna junto a la **lista de exclusión** parámetro y en el **Reemplazar valor** columna, escriba el nombre de la base de datos que desea excluir de la supervisión. Asegúrese de que el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no aparecen en las bases de datos que desea supervisar el **Reemplazar valor** columna.  
  
   > [!TIP]  
   >  Puede usar las detecciones de objeto modificado para crear un nuevo módulo de administración. En la parte inferior del panel, el **Seleccionar módulo de administración de destino** desplegable muestra un valor predeterminado de **módulo de administración predeterminado**. Haga clic en **New** para crear un nuevo módulo de administración con las detecciones de objeto modificado.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de servidores SQL Server](../technical-guides/monitoring-sql-servers.md)