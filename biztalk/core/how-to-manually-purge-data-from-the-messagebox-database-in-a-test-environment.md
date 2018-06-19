---
title: Cómo purgar datos manualmente desde la base de datos de cuadro de mensajes en un entorno de prueba | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 398991a9-344a-487a-a817-dfc97d48ebe6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4a6d5f8b232e31a140ee4786b87d2bb270505f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254060"
---
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a>Purga manual de datos de la base de datos de cuadro de mensaje en un entorno de prueba
Al ejecutar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de desarrollo o prueba, los datos almacenados en la base de datos de cuadro de mensajes no son normalmente datos económicos importantes "activos", por lo cual pueden eliminarse. En estos casos, es posible que necesite un método "rápido y sucio" para depurar datos desde la base de datos de cuadro de mensajes. Siga los procedimientos de este tema para depurar datos manualmente desde la base de datos de cuadro de mensajes usando el procedimiento almacenado bts_CleanupMsgbox.  
  
> [!NOTE]
>  solo debe realizar estos pasos en un entorno de prueba. No se admite la depuración manual de la base de datos de cuadro de mensajes de BizTalk en un entorno de producción.  
  
### <a name="to-stop-biztalk-services"></a>Procedimiento para detener los servicios de BizTalk  
  
1.  Detenga cualquier instancia del servicio de BizTalk desde la consola Servicios.  
  
2.  Si está ejecutando adaptadores en hosts aislados (por ejemplo, HTTP, SOAP o WCF), reinicie IIS ejecutando IISRESET desde un símbolo del sistema.  
  
3.  Cierre cualquier adaptador aislado personalizado que esté en ejecución.  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a>Para crear y ejecutar el procedimiento almacenado bts_CleanupMsgbox con SQL Server 2008  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el **conectar con SQL Server** cuadro de diálogo, seleccione el servidor SQL server y el método de autenticación adecuado y, a continuación, haga clic en **conectar**.  
  
3.  En el **bases de datos disponibles** lista desplegable, seleccione la base de datos de BizTalk Messagebox (**BizTalkMsgBoxDB** de forma predeterminada).  
  
4.  Haga clic en el **nueva consulta** icono en la barra de herramientas.  
  
5.  Abra la **msgbox_cleanup_logic.sql** archivo desde SQL Server Management Studio. El archivo msgbox_cleanup_logic.sql se encuentra en el directorio [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ del equipo de BizTalk Server.  
  
6.  Haga clic en el **Ejecutar consulta** icono en la barra de herramientas para ejecutar el script para crear el bts_CleanupMsgbox procedimiento almacenado. El procedimiento almacenado bts_CleanupMsgbox puede verse a continuación en la lista de procedimientos almacenados como dbo.bts_CleanupMsgbox.  
  
7.  Haga clic en el **nueva consulta** icono en la barra de herramientas.  
  
8.  Pegue el siguiente comando en la nueva ventana de consulta:  
  
    ```  
    exec bts_CleanupMsgbox  
    ```  
  
9. Haga clic en el **Ejecutar consulta** icono en la barra de herramientas para ejecutar la bts_CleanupMsgbox procedimiento almacenado.  
  
    > [!IMPORTANT]
    >  No ejecute el procedimiento almacenado bts_CleanupMsgbox en un servidor de producción que esté ejecutando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. solo debe ejecutar el procedimiento almacenado bts_CleanupMsgbox en un entorno de prueba. No se admite la ejecución del procedimiento almacenado bts_CleanupMsgbox en un entorno de producción.  
  
10. Reinicie los servicios de BizTalk según sea necesario.  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a>Consideraciones al ejecutar el procedimiento almacenado bts_CleanupMsgbox  
 Las siguientes consideraciones se aplican al ejecutar el procedimiento almacenado bts_CleanupMsgbox:  
  
1.  Si instala una revisión de seguridad en el sistema de prueba que actualiza los esquemas de base de datos de BizTalk, la revisión de seguridad podría sobrescribir el procedimiento almacenado bts_CleanupMsgbox con una versión vacía de dicho procedimiento. En tal caso, deberá seguir los procedimientos descritos en este tema para volver a crear el procedimiento almacenado bts_CleanupMsgbox.  
  
2.  Si crea una nueva base de datos MessageBox, el procedimiento almacenado bts_CleanupMsgbox se vaciará y deberá seguir los procedimientos descritos en este tema para volver a crear el procedimiento almacenado bts_CleanupMsgbox.  
  
3.  Uso del procedimiento almacenado bts_CleanupMsgbox es **no admite** en un sistema de producción. Este procedimiento almacenado eliminará todos los datos de su base de datos de cuadro de mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Cómo purgar datos de la base de datos de seguimiento de BizTalk](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)