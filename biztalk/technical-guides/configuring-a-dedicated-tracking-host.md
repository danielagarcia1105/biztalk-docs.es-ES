---
title: Configurar un Host de seguimiento dedicado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f997bcc2-08fd-4e9a-ba44-542ec8460d6d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b91a4b65c6e9a9b293e967385b8f0ac4eece1aa4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-a-dedicated-tracking-host"></a>Configurar un Host de seguimiento dedicado
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]está optimizado para el rendimiento, por lo que los motores de mensajes y orquestación principal no mueve realmente eventos o mensajes directamente a las bases de datos de seguimiento de BizTalk (DTA) o supervisión de la actividad económica (BAM), ya que esto podría desviar estos motores desde su servidor principal trabajo de ejecución de procesos empresariales. En su lugar, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deja los eventos y mensajes en la base de datos de cuadro de mensajes y las marca como que requieren un cambio a las bases de datos de seguimiento de BizTalk o BAM. Un proceso en segundo plano (el host de seguimiento), a continuación, mueve los eventos para las bases de datos de seguimiento de BizTalk y BAM, mientras un trabajo de agente SQL Server copias mensajes controlados en la base de datos de seguimiento de BizTalk.  
  
## <a name="advantages-of-using-a-dedicated-tracking-host"></a>Ventajas de utilizar un Host de seguimiento dedicado  
 Un BizTalk Host que realiza el seguimiento es responsable de transferir la DTA y BAM datos de seguimiento de la base de datos de cuadro de mensajes para las bases de datos de importación principal de BAM y de seguimiento de BizTalk (DTA). Este movimiento de datos de seguimiento tiene un impacto en el rendimiento de otros artefactos de BizTalk que se ejecutan en el mismo host que hospeda el seguimiento. Por lo tanto, debe usar un host dedicado que no hace nada pero el seguimiento de host.  
  
 Uso de un host de seguimiento dedicado también le permite detener otros hosts de BizTalk sin interferir con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de seguimiento. El movimiento de datos fuera de la base de datos de cuadro de mensajes de seguimiento es fundamental para un correcto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema. Si se detiene el Host de BizTalk responsables de mover los datos de seguimiento en el grupo de BizTalk, no se ejecutará el servicio de descodificación de datos de seguimiento. El impacto de esto es como sigue:  
  
-   Datos de seguimiento de HAT no se moverán desde la base de datos de cuadro de mensajes a la base de datos de seguimiento de BizTalk.  
  
-   Datos de seguimiento de BAM no se moverán desde la base de datos de cuadro de mensajes a la base de datos de importación principal de BAM.  
  
-   Dado que no se mueven los datos, no se puede eliminar de la base de datos de cuadro de mensajes.  
  
-   Cuando se detiene el servicio de descodificación de datos de seguimiento, seguimiento interceptores seguirá ejecutar y escribir datos de seguimiento en la base de datos de cuadro de mensajes. Si no se mueven los datos, esto hará que la base de datos de cuadro de mensajes se convierten en inflan, lo que afectará al rendimiento con el tiempo. Incluso si no se realiza el seguimiento de las propiedades personalizadas o no se configuran los perfiles BAM, de forma predeterminada algunos datos se realiza el seguimiento (como canalización de recepción y enviar eventos y eventos de orquestación). Si no desea ejecutar el servicio de descodificación de datos de seguimiento, desactivar todo el seguimiento para que ningún interceptores de guardan los datos en la base de datos. Para deshabilitar el seguimiento global, consulte [cómo desactivar el seguimiento Global](http://go.microsoft.com/fwlink/?LinkId=154193) (http://go.microsoft.com/fwlink/?LinkId=154193) Use el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para deshabilitar de forma selectiva los eventos de seguimiento.  
  
## <a name="optimizing-performance-for-a-dedicated-tracking-host"></a>Optimizar el rendimiento para un Host de seguimiento dedicado  
 Este host se debe ejecutar en al menos dos equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (redundancia en caso de uno produce un error). Para obtener un rendimiento óptimo, debe tener al menos un seguimiento de la instancia de host por base de datos de cuadro de mensajes. El número real de seguimiento de instancias de host debe ser N + 1, donde N = número de bases de datos de cuadro de mensajes. El "+ 1" es para redundancia. No hay ninguna ventaja para agregar más, ya que seguimiento solo una instancia de host puede mover datos de una base de datos de cuadro de mensajes específico. Como resultado, si el bloqueo, nunca debe ser un problema. El adicionales de una instancia de host de seguimiento se agrega para tolerancia a errores; Si uno de lo seguimiento hospeda instancias se produce un error, la instancia adicional asumirá las tareas de la instancia con errores.  
  
 Un seguimiento de la instancia de host mueve datos de seguimiento para bases de datos de cuadro de mensajes específicas, pero nunca habrá datos móviles para una base de datos de cuadro de mensajes específico de la instancia de host de más de un seguimiento. Por ejemplo, si tiene tres bases de datos de cuadro de mensaje y sólo dos instancias de host de seguimiento, a continuación, una de las instancias de host debe mover los datos de dos de las bases de datos de cuadro de mensajes. Agrega una tercera instancia de host de seguimiento distribuye el seguimiento hospedar trabajo a otro equipo que ejecute [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este escenario, agregar un cuarto de seguimiento de la instancia de host no se distribuiría cualquier host de seguimiento más trabajo, pero proporcionaría un adicional de seguimiento de la instancia de host de tolerancia a errores.  
  
 Para obtener más información sobre el servicio de Bus de sucesos SAE, vea los temas siguientes en la Ayuda de BizTalk Server:  
  
-   [Administrar el servicio de Bus de eventos BAM](http://go.microsoft.com/fwlink/?LinkId=154194) (http://go.microsoft.com/fwlink/?LinkId=154194)  
  
-   [Creación de instancias del servicio de Bus de sucesos SAE](http://go.microsoft.com/fwlink/?LinkId=154195) (http://go.microsoft.com/fwlink/?LinkId=154195)  
  
## <a name="configuring-a-dedicated-tracking-host"></a>Configurar un Host de seguimiento dedicado  
 Para llevar a cabo el procedimiento de esta sección, debe tener los siguientes derechos de usuario para modificar las propiedades de host para permitir el seguimiento de host:  
  
-   Debe ser un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  
  
-   Debe disponer de los siguientes derechos en SQL Server:  
  
    -   Debe ser un administrador de SQL Server o un miembro de la *db_owner* o *db_securityadmin* roles de base de datos de SQL Server en el seguimiento de BizTalk base de datos (BizTalk DTADb), (de las bases de datos de cuadro de mensajes BizTalkMsgBoxDb) y la base de datos de importación principal de BAM (BAMPrimaryImport).  
  
    -   Debe ser miembro del rol sysadmin de SQL Server en todos los equipos donde hay bases de datos de cuadro de mensajes, o un miembro de la *db_owner* o *db_ddladmin* rol de SQL Server para todas las bases de datos de cuadro de mensajes.  
  
#### <a name="to-enable-host-tracking"></a>Para habilitar el seguimiento de host  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **Hosts**.  
  
3.  En el panel de detalles, haga clic en el host que desea modificar y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades de Host** cuadro de diálogo, en la **General** ficha, active o desactive **opciones - Permitir seguimiento de Host**y, a continuación, haga clic en **Aceptar**.  
  
     Activar esta casilla para indicar que el host carga el componente de seguimiento de BizTalk para procesar la supervisión de estado y datos empresariales. Si la activa, el host actual tendrá acceso de lectura y escritura a las tablas de seguimiento en la base de datos de cuadro de mensajes, así como en la base de datos de seguimiento. Por tanto, los objetos que se ejecuten en este host tendrán también acceso de lectura y escritura a estas bases de datos.  
  
     Si la desactiva, el host actual solo tendrá privilegios de escritura para las tablas de seguimiento en la base de datos de cuadro de mensajes y no tendrá acceso a la base de datos de seguimiento.  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)