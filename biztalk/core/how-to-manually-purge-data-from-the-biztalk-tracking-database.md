---
title: Cómo purgar datos manualmente desde la base de datos de seguimiento de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging, manually
- purging, warnings
ms.assetid: f350d850-5034-4166-940c-8d10b7b445fb
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb7b0eb838295e4abdc059a1437b6cf338d0a99
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993085"
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a>Cómo purgar datos manualmente desde la base de datos de seguimiento de BizTalk
El trabajo DTA Archive and Purge SQL Server Agent reduce la necesidad de purgar manualmente los datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb) debido a la continua purga de la base de datos y a la compactación de los datos de seguimiento almacenados. Es posible que tenga que efectuar una purga manual cuando la base de datos de seguimiento de BizTalk (BizTalkDTADb) haya crecido tanto como para ocasionar una pérdida continua de rendimiento y el trabajo DTA Archive and Purge no pueda hacer frente al crecimiento de la base de datos.  
  
> [!CAUTION]
>  Este procedimiento elimina todos los datos de seguimiento de las instancias finalizadas de la base de datos de seguimiento de BizTalk (BizTalkDTADb), independientemente de la hora de finalización. Antes de llevar a cabo este procedimiento, es conveniente que archive la base de datos de seguimiento de BizTalk (BizTalkDTADb) separada del resto de bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a>Procedimiento para purgar datos desde la base de datos de seguimiento de BizTalk  
  
1. Haga una copia de seguridad de las bases de datos de BizTalk Server.  
  
2. Archive la base de datos de seguimiento de BizTalk (BizTalkDTADb).  
  
3. Abra la Consola de servicios. Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**. Si un **User Account Control** muestra el cuadro de diálogo, haga clic en **continuar**.  
  
4. Cuando aparezca la Consola de servicios, busque y detenga cada uno de los siguientes servicios. Para detener un servicio, haga clic en la fila de servicio en la **servicios** panel y, a continuación, haga clic en **detener**.  
  
   -   BizTalkServiceBizTalkGroup: BizTalkServerApplication  
  
   -   Servicio de inicio de sesión único (SSO) empresarial  
  
        Si el BizTalkServiceBizTalkGroup: servicio BizTalkServerApplication está en ejecución cuando se intenta apagar la empresa único inicio de sesión, un **detener otros servicios** se mostrará el cuadro de diálogo. Haga clic en **Sí**.  
  
   -   Servicio de actualización de motor de reglas  
  
5. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**. Si un **User Account Control** muestra el cuadro de diálogo, compruebe que la acción descrita es lo que desea y, a continuación, haga clic en **continuar**.  
  
6. En el **consola de administración de BizTalk Server** en el panel del explorador en el lado izquierdo de la ventana, haga doble clic en **grupo de BizTalk** para expandir la lista debajo de él, a continuación, haga doble clic en **plataforma Configuración de**y, a continuación, haga clic en **instancias de Host**. Esto mostrará una lista de instancias de host (el **instancias de Host** panel) y propiedades relacionadas, en el lado derecho de la pantalla.  
  
7. En el **instancias de Host** panel, haga clic en cada instancia de host y, a continuación, haga clic en **detener**.  
  
8. Haga clic en **iniciar**, vaya a **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
9. En el símbolo del sistema, escriba:  
  
     **net stop iisadmin /y**  
  
     Esto detiene el servicio IIS Admin y todos los servicios dependientes uno a uno y evita que los datos nuevos se escriban en BizTalkDTADb, mientras que los datos se están purgando. Anote la lista de servicios a medida que se van deteniendo. Necesitará utilizar esta lista de servicios más adelante para reiniciar IIS.  
  
     A continuación se ofrece un ejemplo de la salida obtenida tras ejecutar este comando (la lista de servicios dependientes puede variar):  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
11. En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde reside la base de datos de seguimiento de BizTalk (BizTalkDTADb) y el tipo de autenticación adecuado y, a continuación, haga clic en **Connect** a conectar con el servidor SQL Server apropiado.  
  
12. En **Microsoft SQL Server Management Studio**, haga doble clic en **bases de datos**, haga doble clic en el **BizTalkDTADb** base de datos, haga doble clic en  **Programación**y, a continuación, haga clic en **Stored Procedures**.  
  
13. En el **detalles del explorador de objetos** panel, haga clic en **dtasp_PurgeAllCompletedTrackingData**y, a continuación, haga clic en **Ejecutar procedimiento almacenado**.  
  
14. En el **Ejecutar procedimiento** cuadro de diálogo, haga clic en **Aceptar**.  
  
     Este procedimiento almacenado elimina todos los datos de seguimiento relativos a las instancias finalizadas, independientemente de su hora de finalización.  
  
15. Abra Servicios. Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**. Si un **User Account Control** muestra el cuadro de diálogo, compruebe que la acción descrita es lo que desea y, a continuación, haga clic en **continuar**.  
  
16. Haga clic en cada uno de los siguientes servicios y, a continuación, haga clic en **iniciar**:  
  
    -   BizTalkServiceBizTalkGroup: BizTalkServerApplication  
  
    -   Servicio de inicio de sesión único (SSO) empresarial  
  
    -   Servicio de actualización de motor de reglas  
  
17. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
18. En el **consola de administración de BizTalk Server**, haga doble clic en el **grupo de BizTalk**, haga doble clic en **configuración de plataforma**y, a continuación, haga clic en **Host Instancias**.  
  
19. En el **detalles del explorador de objetos** panel, haga clic en cada instancia de host detenida y, a continuación, haga clic en **iniciar**.  
  
20. Inicie un símbolo del sistema, como se describe en el paso 8 anterior.  
  
21. En el símbolo del sistema, reinicie cada uno de los servicios IIS que detuvo en el paso 4. Tipo:  
  
     **Net start**  *\<IISserviceName\>*  
  
     Donde *\<IISserviceName\>* es el nombre del servicio IIS que desea reiniciar. Deberá repetir este comando para cada uno de los servicios IIS.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [Copia de seguridad y restaurar bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [Cómo iniciar, detener, pausar, reanudar o reiniciar servicios de BizTalk Server](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)