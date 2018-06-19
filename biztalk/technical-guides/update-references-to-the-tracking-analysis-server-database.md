---
title: Actualizar las referencias a la base de datos del servidor de análisis de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a403325-1394-4668-946f-01b610cb686e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b85c5c50bc8aeb388d6b7df1591f4b13900998e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976322"
---
# <a name="update-references-to-the-tracking-analysis-server-database"></a>Actualizar las referencias a la base de datos del servidor de análisis de seguimiento
La base de datos del servidor de análisis de seguimiento es opcional y contiene los cubos de procesamiento analítico en línea (OLAP). Estos cubos OLAP son agregaciones de datos contenidos en la base de datos de seguimiento de BizTalk.  
  
 Para restaurar la base de datos del servidor de análisis de seguimiento, use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager para procesar los cubos MessageMetrics y ServiceMetrics. Para obtener instrucciones, consulte [administrar Backing Up and Restoring (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (http://go.microsoft.com/fwlink/?LinkId=130939) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla.  
  
 Para restaurar la base de datos de seguimiento de Analysis Server en un equipo alternativo, también debe actualizar las referencias al nombre de base de datos en la base de datos de administración de BizTalk mediante el procedimiento siguiente.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-update-references-to-the-tracking-analysis-server-database-name"></a>Para actualizar referencias al nombre de base de datos de seguimiento de Analysis Server  
  
1.  En el sistema de destino, haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008**y, a continuación, haga clic en **deSQLServerManagementStudio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo, seleccione la **tipo de servidor** como **motor de base de datos**, proporcione un nombre de servidor, proporcione las credenciales para conectarse o el servidor y, a continuación, Haga clic en **conectar**.  
  
3.  Abra el servidor adecuado haciendo clic en él, haga doble clic en **bases de datos**, haciendo doble clic en **BizTalkMgmtDb**y, a continuación, haga clic en **tablas**.  
  
4.  En el panel de detalles, haga clic en **adm_Group**y, a continuación, seleccione **Abrir tabla**.  
  
5.  Modifique las columnas que corresponden a la base de datos original para hacer referencia a los valores apropiados de la nueva base de datos.  
  
    > [!NOTE]  
    >  *\<DBType\>*  DBServerName y  *\<DBType\>*  DBName indican la ubicación de la base de datos, donde  *\<DBType\>*  corresponde al tipo de la base de datos, por ejemplo, TrackingAnalysis.  
  
6.  Cierre la tabla para guardar los valores nuevos.  
  
## <a name="see-also"></a>Vea también  
 [Actualización de referencias de base de datos](../technical-guides/updating-database-references.md)