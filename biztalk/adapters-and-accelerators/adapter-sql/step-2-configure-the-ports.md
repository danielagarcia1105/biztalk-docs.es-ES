---
title: 'Paso 2: Configurar los puertos | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e804da96-26ae-482d-b6e1-67af24d639d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c9aaefe0cff41365a587079d0c82629ddddc586
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967290"
---
# <a name="step-2-configure-the-ports"></a>Paso 2: Configurar los puertos
![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 **Objetivo:** en este paso, creará los puertos físicos en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Cree un puerto físico para cada puerto lógico que creó en la orquestación. Creará los siguientes puertos:  
  
-   Un unidireccional WCF-Custom puerto de recepción para recibir mensajes de notificación de cambios en **empleado** tabla en una base de datos de SQL Server.  
  
-   Una respuesta de solicitud de WCF-Custom puerto de envío para enviar mensajes de solicitud y recibir respuesta para invocar la **UPDATE_EMPLOYEE** procedimiento almacenado y para realizar la operación de inserción en el **Purchase_Order**tabla. En la orquestación, se utiliza el mismo puerto de envío para realizar las operaciones. De forma similar, en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, va a utilizar un puerto de envío único para ambas operaciones.  
  
-   Un puerto de envío unidireccional para enviar la respuesta para la operación de inserción. En este tutorial, porque debe informar al departamento de compras a través de un correo electrónico, se crea este puerto de envío como un puerto SMTP.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 1: implementar la orquestación](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md)).  
  
### <a name="to-create-a-physical-one-way-receive-port"></a>Para crear el puerto de recepción unidireccional físico  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola en el lado izquierdo, expanda **administración de BizTalk Server**, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.  
  
3.  Expanda **grupo de BizTalk**, expanda **aplicaciones**y expanda **SampleApplication**. Para este tutorial, creará todos los puertos y aplicaciones dentro de la aplicación SampleApplication.  
  
4.  Siga las instrucciones que aparecen en la sección "Implementación de adaptadores para recibir mensajes de SQL Server" de [configurar un puerto mediante el adaptador de WCF-custom y el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md). Nombre del puerto como **NotifyReceivePort**.  
  
5.  Asegúrese de establecer las propiedades de enlace siguiente para configurar el adaptador para recibir notificaciones de cambios en el **empleado** tabla.  
  
    |Propiedad de enlace|Valor|  
    |----------------------|-----------|  
    |**InboundOperationType**|Establezca esta propiedad en **notificación**.|  
    |**NotificationStatement**|Establezca esta propiedad en:<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **Nota:** específicamente debe especificar los nombres de columna en la instrucción tal y como se muestra en la siguiente instrucción Select. Además, debe siempre especificar el nombre de la tabla junto con el nombre del esquema, por ejemplo, `dbo.Employee`.|  
    |**NotifyOnListenerStart**|Establezca esta propiedad en **True**.|  
  
     Para obtener más información acerca de las propiedades de enlace diferente, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
### <a name="to-create-a-request-response-send-port-for-two-operations"></a>Para crear una respuesta de solicitud de puerto de envío para dos operaciones  
  
1.  Siga las instrucciones que aparecen en la sección "Implementación de adaptadores para enviar mensajes a SQL Server" de [configurar un puerto mediante el adaptador de WCF-custom y el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md). Nombre del puerto como **SQLOutboundPort**.  
  
2.  Dado que va a realizar dos operaciones con el mismo puerto de envío, debe usar la asignación dinámica de acción para especificar la acción para la operación. Al configurar el puerto, en la **acción** , especifique la asignación de acciones de la siguiente manera:  
  
    ```  
    <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
      <Operation Name="UpdateEmp" Action="TypedProcedure/dbo/UPDATE_EMPLOYEE" />  
      <Operation Name="InsertPO" Action="TableOp/Insert/dbo/Purchase_Order" />  
    </BtsActionMapping>  
    ```  
  
     Tenga en cuenta que en la orquestación, se crean dos operaciones para el puerto de envío de solicitudes y respuestas: **UpdateEmp** y **InsertPO**. Por lo tanto, en la configuración del puerto físico proporcionar los mismos nombres de operación en la asignación dinámica de acción. En el extracto anterior, la acción para **UpdateEmp** operación es `TypedProcedure/dbo/UPDATE_EMPLOYEE`. De forma similar, la acción para **InsertPO** operación es `TableOp/Insert/dbo/Purchase_Order`.  
  
3.  También debe configurar el puerto de envío para utilizar el asignador que creó en la orquestación para asignar el mensaje de respuesta de **UPDATE_EMPLOYEE** procedimiento almacenado para el mensaje de solicitud para la operación de inserción en **Purchase_ Orden** tabla. Para ello:  
  
    1.  Haga clic en el SQLOutboundPort en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración y, a continuación, haga clic en **propiedades**.  
  
    2.  Desde el **SQLOutboundPort – propiedades de puerto de envío** cuadro de diálogo, en el panel izquierdo, haga clic en **asignaciones de salida**.  
  
    3.  En el panel derecho, en la **asignaciones de salida** cuadro, haga clic en la celda situada bajo la **mapa** columna y en la lista desplegable, seleccione **Transform_1**. Este es el nombre de la asignación creada en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
         Haga clic en **Aceptar**.  
  
         ![Configurar asignación de salida](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-010-map-ports.gif "sql_adap_tut_010_map_ports")  
  
### <a name="to-create-an-smtp-send-port"></a>Para crear un puerto de envío de SMTP  
  
1.  Siga las instrucciones que aparecen en el "cómo configurar un puerto de envío de SMTP con el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración" en la sección [http://go.microsoft.com/fwlink/?LinkId=141549](http://go.microsoft.com/fwlink/?LinkId=141549). Nombre del puerto como **EmailResponse**.  
  
2.  Como parte de la configuración del puerto, especifique la dirección de correo electrónico para el departamento de compras de la **a** propiedad.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso crea un WCF-Custom puerto de recepción para recibir notificaciones de SQL Server, puerto de envío WCF-Custom para realizar operaciones en SQL Server y un puerto SMTP para enviar la respuesta de SQL Server como un correo electrónico al departamento de compras.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar e iniciar la aplicación de BizTalk, tal y como se describe en [paso 3: configurar e iniciar la aplicación](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Implementar la orquestación](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md)   
 [Paso 3: Configurar e iniciar la aplicación](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)   
 [Lección 5: Implementar la solución](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)