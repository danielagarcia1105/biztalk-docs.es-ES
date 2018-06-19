---
title: Cómo actualizar referencias al servidor de análisis BAM y nombres de base de datos de esquema de estrella | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- restoring [BAM], Analysis database
- Analysis database [BAM], restoring
- restoring, BAM
- restoring [BAM], updating references
- BAM, restoring
- Analysis database [BAM], updating references
ms.assetid: cbe5e500-0a25-427e-bc76-1eae24b3e5f3
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4f98129efd2f7c027ecb6c3e69d494ff2e96e8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287452"
---
# <a name="how-to-update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a>Actualización de referencias a los nombres de base de datos de esquema de estrella y servidor de análisis de BAM
Si ha realizado copias de seguridad de las bases de datos BAMAnalysis y BAMStarSchema, podrá restaurarlas en un equipo distinto y cambiar el nombre a esas copias de seguridad en el caso de que se produzca un error de datos o del sistema.  
  
 Para restaurar las bases de datos del servidor de análisis de BAM o BAMStarSchema, siga los pasos descritos en [cómo restaurar las bases de datos](../core/how-to-restore-your-databases.md). Además, tendrá que actualizar los paquetes de Servicios de transformación de datos (DTS) de BAM con el nuevo nombre de base de datos y de servidor.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-update-references-to-the-bam-analysis-server-and-bam-star-schema-database-name-sql-server-2008-r2sp1"></a>Para actualizar las referencias al nombre de base de datos de servidor de análisis de BAM y de esquema de estrella de BAM (SQL Server 2008 R2 o SP1)  
  
1.  Detenga todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de BAM, o impida su ejecución hasta que se hayan restaurado las bases de datos BAMAnalysis o BAMStarSchema.  
  
2.  Detenga el servicio de aplicaciones de BizTalk (que incluye el servicio de bus de sucesos BAM) para que no intente importar más datos en las bases de datos.  
  
    1.  Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.  
  
    2.  Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **detener**.  
  
    > [!TIP]
    >  Otra manera de detener un servicio es usar el **Net Stop** comando. Para detener el servicio de BizTalk con Net Stop, abra un **símbolo** (si usa Windows Server 2008 o Windows Vista, inicie el símbolo mediante **ejecutar como administrador**) y escriba lo siguiente: `Net Stop BTSSvc$BizTalkServerApplication` a continuación, presione **ENTRAR**.  
  
3.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Business Intelligence Development Studio**.  
  
4.  En SQL Server Business Intelligence Development Studio, cree un nuevo proyecto. Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **proyecto**.  
  
5.  En el **nuevo proyecto** cuadro de diálogo **plantillas**, haga clic en **proyecto de Integration Services**y, a continuación, haga clic en **Aceptar**.  
  
6.  En el **proyecto de Integration Services** cuadro de diálogo **el Explorador de soluciones**, haga clic en **paquetes SSIS**y, a continuación, haga clic en **Agregar paquete existente**.  
  
7.  En el **Agregar copia de paquete existente** cuadro de diálogo, en la **Server** lista desplegable, seleccione el servidor que contiene el paquete BAM_AN.  
  
8.  En **ruta de acceso del paquete**, haga clic en el botón de puntos suspensivos.  
  
9. En el **paquete SSIS** diálogo cuadro, seleccione el paquete BAM_AN, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.  
  
     Con ello, el paquete aparecerá en el Explorador de soluciones.  
  
10. En **el Explorador de soluciones**, haga doble clic en el paquete BAM_AN. En **administradores de conexión**, haga doble clic en el número de la base de datos 3 (base de datos MSDB).  
  
11. En el **Connection Manager** cuadro de diálogo, en la **nombre del servidor** cuadro, escriba el nombre del servidor MSDB y, a continuación, haga clic en **Aceptar**.  
  
12. Haga clic en el **Explorador de paquetes** ficha, haga doble clic en el **Variables** carpeta y actualice los valores para el nombre del servidor de importación principal de principal y de importación en nombre de base de datos.  
  
13. Haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.  
  
14. En **Microsoft SQL Server Management Studio**, haga clic en **conectar**.  
  
15. Haga clic en **Integration Services**, haga doble clic en **paquetes almacenados**, haga clic en **MSDB**, haga clic en el paquete BAM_AN y, a continuación, haga clic en **Importar paquete**.  
  
16. En el **Importar paquete** cuadro de diálogo **ubicación del paquete**, seleccione **sistema de archivos**.  
  
17. En **ruta de acceso del paquete**, navegue al proyecto guardado, seleccione la BAM_AN\*archivo DTSX y, a continuación, haga clic en **abiertos**.  
  
18. Haga clic dentro de la **nombre del paquete** cuadro para rellenar automáticamente el cuadro.  
  
19. Haga clic en **Aceptar**y, a continuación, haga clic en **Sí** para sobrescribir.  
  
20. Reinicie el servicio de aplicaciones de BizTalk.  
  
    1.  Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.  
  
    2.  Haga clic en el **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication** de servicio y, a continuación, haga clic en **iniciar**.  
  
21. Habilite todos los paquetes SSIS de mantenimiento de datos y de actualización de cubos de SAE.  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad y restauración de BAM](../core/backing-up-and-restoring-bam.md)