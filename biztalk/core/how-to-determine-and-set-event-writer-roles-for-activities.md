---
title: "Cómo determinar y establecer Roles de sistema de escritura de eventos para las actividades | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73bfe8ff-167a-4bf0-ab87-3926290d52d8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9fa663d395fc36205e137da374f17cb9470521
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-determine-and-set-event-writer-roles-for-activities"></a>Cómo determinar y establecer roles de escritor de eventos para las actividades
BAM proporciona dos modos de seguridad cuando se escriben eventos sobre actividades. Puede conceder permisos para escribir eventos sobre actividades individuales o conceder permisos para escribir eventos sobre todas las actividades implementadas.  
  
 Las funciones de escritor de eventos de actividad que se crean al implementar la definición de BAM proporcionan seguridad de nivel de actividad. Por ejemplo, si implementa una definición para una actividad denominada CreditCard, BAM crea una función de escritor de eventos denominada bam_CreditCard_EventWriter. Esta función tiene permisos para escribir eventos para la actividad. Para conceder permisos de usuario para escribir eventos para la actividad, agregue el usuario a la función.  
  
 Como alternativa, puede conceder derechos a los usuarios para escribir eventos en todas las actividades si los agrega al super rol BAM_EVENT_WRITER, que tiene permisos para escribir en todas las actividades.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento, debe contar con lo siguiente:  
  
-   Una conexión a BAMPrimaryImportDb, donde se implementó la actividad.  
  
-   Permisos DBO en la base de datos.  
  
### <a name="to-add-a-user-to-an-event-writer-role"></a>Para agregar un usuario a una función de escritor de eventos  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Microsoft SQL Server 2008**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el **conectar con SQL Server** cuadro de diálogo, seleccione el servidor SQL Server y el método de autenticación adecuado y, a continuación, haga clic en **conectar**.  
  
3.  En el **Explorador de objetos** panel expanda **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.  
  
4.  Haga clic en el **nueva consulta** icono en la barra de herramientas.  
  
5.  Copie los siguientes comandos y péguelos en la ventana de consulta. Reemplace el nombre de dominio, el nombre de usuario y los marcadores de posición del nombre de la actividad con los valores adecuados.  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'bam_<activity name>_EventWriter', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  Los nombres de función distinguen entre mayúsculas y minúsculas. Los nombres de actividad también distinguen entre mayúsculas y minúsculas; es decir, deben coincidir con el uso de mayúsculas y minúsculas utilizado cuando se implementó la actividad.  
  
6.  Haga clic en el **Execute** icono en la barra de herramientas o presione F5 para ejecutar los comandos.  
  
### <a name="to-add-a-user-to-an-event-writer-super-role"></a>Para agregar un usuario a una superfunción de escritor de eventos  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Microsoft SQL Server 2008**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el **conectar con SQL Server** cuadro de diálogo, seleccione el servidor SQL Server y el método de autenticación adecuado y, a continuación, haga clic en **conectar**.  
  
3.  En el **Explorador de objetos** panel expanda **bases de datos**y, a continuación, seleccione la base de datos de importación principal de BAM.  
  
4.  Haga clic en el **nueva consulta** icono en la barra de herramientas.  
  
5.  Copie los siguientes comandos y péguelos en la ventana de consulta. Reemplace el nombre de dominio y el nombre de usuario con los valores adecuados.  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'BAM_EVENT_WRITER', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  Los nombres de función distinguen mayúsculas de minúsculas. Debe especificar la función de escritor de evento de acuerdo con lo especificado.  
  
6.  Haga clic en el **Execute** icono en la barra de herramientas o presione F5 para ejecutar los comandos.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la seguridad BAM](../core/managing-bam-security.md)