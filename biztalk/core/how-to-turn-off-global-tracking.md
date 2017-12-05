---
title: "Cómo desactivar el seguimiento Global | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eae3059a-cbdd-47c4-84cd-edfb5480b9fa
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c143d19e6071ca4f9ce488ae936082db86dc84dc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-turn-off-global-tracking"></a>Cómo desactivar el seguimiento global
De forma predeterminada, el seguimiento global se habilita cuando se instala BizTalk Server. La base de datos de seguimiento de BizTalk (BizTalkDTADb) aumenta de tamaño a medida que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa los datos del sistema. Si el rendimiento del disco es deficiente a causa del tamaño de la base de datos de seguimiento de BizTalk, puede purgar los datos de la misma. Si están surgiendo problemas de rendimiento que se solucionan de manera momentánea mediante la purga de la base de datos de seguimiento de BizTalk, y desea configurar BizTalk para que no recopile más información de seguimiento, considere la posibilidad de desactivar el seguimiento global.  
  
 Es importante tener en cuenta que, al desactivar el seguimiento global, se deshabilitan los interceptores de seguimiento de todo el grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Es decir, BizTalk no realizará un seguimiento de los eventos en las tablas de seguimiento. Como alternativa, puede desactivar el seguimiento de los eventos individuales.  
  
> [!NOTE]
>  Si utiliza Supervisión de la actividad económica (BAM), debe mantener un host de seguimiento dedicado, incluso si deshabilita el seguimiento global, ya que los eventos de BAM usan el Servicio de descodificación de datos de seguimiento (TDDS).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a>Para desactivar el seguimiento global (SQL Server 2008)  
  
1.  En el servidor SQL server que hospeda la base de datos de seguimiento de BizTalk (BizTalkDTADb), haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo, compruebe el nombre del servidor y la autenticación y, a continuación, haga clic en **conectar**.  
  
3.  En Microsoft SQL Server Management Studio, en **Explorador de objetos**, expanda \< *nombre_equipo*\>, expanda **bases de datos**, expanda  **BizTalkMgmtDb**, expanda **tablas**, haga clic en **adm_Group**y, a continuación, haga clic en **Abrir tabla**.  
  
4.  En el Visor de tablas, desplácese horizontalmente hasta que encuentre **GlobalTrackingOption**.  
  
5.  En el **GlobalTrackingOption** columna, cambie el valor de 1 a 0 para desactivar esta característica y, a continuación, presione ENTRAR.  
  
6.  Cierre Microsoft SQL Server Management Studio.  
  
    > [!NOTE]
    >  Deberá reiniciar los hosts de BizTalk para que el cambio surta efecto.  
  
7.  Haga clic en **iniciar**, haga clic en **programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
8.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Instancias de host**.  
  
9. En el panel de detalles, haga clic en cada host y, a continuación, haga clic en **reiniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [Cómo purgar datos de la base de datos de seguimiento de BizTalk](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)   
 [Cómo purgar datos manualmente desde la base de datos de seguimiento de BizTalk](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)