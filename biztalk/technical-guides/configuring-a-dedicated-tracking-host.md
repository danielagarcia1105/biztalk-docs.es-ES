---
title: Configuración de un Host de seguimiento dedicado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f997bcc2-08fd-4e9a-ba44-542ec8460d6d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: defed64020300ebe6843e8e06bb15a51af2c4ec3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986717"
---
# <a name="configuring-a-dedicated-tracking-host"></a>Configuración de un Host de seguimiento dedicado
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está optimizado para rendimiento, así que la orquestación principal y los motores de mensajes no realmente la transición eventos o mensajes directamente a las bases de datos de seguimiento de BizTalk (DTA) o supervisión de la actividad económica (BAM), ya que esto sería desviar estos motores de su principal trabajo de la ejecución de procesos empresariales. En su lugar, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deja los eventos y mensajes en la base de datos de cuadro de mensajes y los marca como que requieren un cambio a las bases de datos BAM o de seguimiento de BizTalk. Un proceso en segundo plano (el host de seguimiento), a continuación, mueve los eventos para las bases de datos BAM y de seguimiento de BizTalk, mientras que un trabajo de agente SQL Server copias mensajes controlados a la base de datos de seguimiento de BizTalk.  
  
## <a name="advantages-of-using-a-dedicated-tracking-host"></a>Ventajas del uso de un Host de seguimiento dedicado  
 Un Host de BizTalk que aloje el seguimiento es responsable de mover la DTA y BAM datos de seguimiento de la base de datos de cuadro de mensajes a las bases de datos de importación principal de BAM y de seguimiento de BizTalk (DTA). Este movimiento de datos de seguimiento tiene un impacto en el rendimiento de otros artefactos de BizTalk que se ejecutan en el mismo host que hospeda el seguimiento. Por lo tanto, debe usar un host dedicado que no hace nada, pero el seguimiento de host.  
  
 Uso de un host de seguimiento dedicado también le permite detener otros hosts de BizTalk sin interferir con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de seguimiento. El movimiento de datos fuera de la base de datos de cuadro de mensajes de seguimiento es fundamental para un correcto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema. Si se detiene el Host de BizTalk responsable de mover datos de seguimiento en el grupo de BizTalk, no se ejecutará el servicio de descodificación de datos de seguimiento. El impacto de esto es como sigue:  
  
- Datos de seguimiento de HAT no se moverá desde la base de datos de cuadro de mensajes a la base de datos de seguimiento de BizTalk.  
  
- Datos de seguimiento de BAM no se moverá desde la base de datos de cuadro de mensajes a la base de datos de importación principal de BAM.  
  
- Dado que no se mueven los datos, no se puede eliminar de la base de datos de cuadro de mensajes.  
  
- Cuando se detiene el servicio de descodificación de datos de seguimiento, los interceptores de seguimiento aún ejecutará y escribir datos de seguimiento en la base de datos de cuadro de mensajes. Si no se mueven los datos, esto hará que la base de datos de cuadro de mensajes se infle, lo que afectará al rendimiento con el tiempo. Incluso si no se realiza el seguimiento de las propiedades personalizadas o no se configuran los perfiles BAM, de forma predeterminada algunos datos se realiza un seguimiento (como canalización de recepción / envío de eventos y eventos de orquestación). Si no desea ejecutar el servicio de descodificación de datos de seguimiento, desactive la opción de todo el seguimiento para que no los interceptores de guardan los datos en la base de datos. Para deshabilitar el seguimiento global, consulte [cómo desactivar el seguimiento Global](http://go.microsoft.com/fwlink/?LinkId=154193) (<http://go.microsoft.com/fwlink/?LinkId=154193>) Use el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para deshabilitar de forma selectiva los eventos de seguimiento.  
  
## <a name="optimizing-performance-for-a-dedicated-tracking-host"></a>Optimizar el rendimiento de un Host de seguimiento dedicado  
 Este host se debe ejecutar en al menos dos equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (redundancia en caso de una falla). Para obtener un rendimiento óptimo, debe tener al menos un seguimiento de la instancia de host por base de datos de cuadro de mensajes. El número real de las instancias de host de seguimiento debe ser N + 1, donde N = número de bases de datos. El "+ 1" es para la redundancia. No hay ninguna ventaja a la adición de más que eso, porque la instancia de host de solo seguimiento puede mover los datos para una base de datos de cuadro de mensajes específico. Como resultado, el bloqueo nunca debe ser un problema. La más de una instancia de host de seguimiento se agrega para tolerancia a errores; Si uno de lo seguimiento aloja las instancias se produce un error, la instancia adicional supone que las tareas de la instancia con errores.  
  
 Seguimiento de un instancia de host mueve datos de seguimiento para bases de datos de cuadro de mensajes específicas, pero nunca habrá movimiento de datos para una base de datos de cuadro de mensajes específico de la instancia de host de más de un seguimiento. Por ejemplo, si tiene tres bases de datos de cuadro de mensajes y solo dos instancias de host de seguimiento, a continuación, una de las instancias de host debe mover los datos de dos de las bases de datos de cuadro de mensajes. Agrega una tercera instancia de host de seguimiento distribuye el seguimiento de host de trabajo a otro equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este escenario, agregando una cuarta instancia de host de seguimiento no sería distribuir cualquier host de seguimiento más trabajo, pero proporcionaría adicional seguimiento de la instancia de host para la tolerancia a errores.  
  
 Para obtener más información sobre el servicio de Bus de eventos BAM, consulte los siguientes temas de Ayuda de BizTalk Server:  
  
-   [Administrar el servicio de Bus de eventos BAM](http://go.microsoft.com/fwlink/?LinkId=154194) ()http://go.microsoft.com/fwlink/?LinkId=154194)  
  
-   [Creación de instancias de servicio de Bus de eventos BAM](http://go.microsoft.com/fwlink/?LinkId=154195) ()http://go.microsoft.com/fwlink/?LinkId=154195)  
  
## <a name="configuring-a-dedicated-tracking-host"></a>Configuración de un Host de seguimiento dedicado  
 Para llevar a cabo el procedimiento en esta sección, debe tener los siguientes derechos de usuario para modificar las propiedades del host para permitir el seguimiento de host:  
  
- Debe ser un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  
  
- Debe disponer de los siguientes derechos en SQL Server:  
  
  -   Debe ser un administrador de SQL Server o un miembro de la *db_owner* o *db_securityadmin* roles de base de datos de SQL Server en la base de seguimiento BizTalk (BizTalk DTADb), (bases de datos de cuadro de mensajes (BizTalkMsgBoxDb) y la base de datos de importación principal de BAM (BAMPrimaryImport).  
  
  -   Debe ser miembro del rol sysadmin de SQL Server en todos los equipos donde hay bases de datos o un miembro de la *db_owner* o *db_ddladmin* rol de SQL Server para todas las bases de datos de cuadro de mensajes.  
  
#### <a name="to-enable-host-tracking"></a>Para habilitar el seguimiento de host  
  
1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **Hosts**.  
  
3. En el panel de detalles, haga clic en el host que desea modificar y, a continuación, haga clic en **propiedades**.  
  
4. En el **propiedades de Host** cuadro de diálogo el **General** ficha, active o desactive **opciones - Permitir seguimiento de Host**y, a continuación, haga clic en **Aceptar**.  
  
    Activar esta casilla para indicar que el host carga el componente de seguimiento de BizTalk para procesar la supervisión de estado y datos empresariales. Si la activa, el host actual tendrá acceso de lectura y escritura a las tablas de seguimiento en la base de datos de cuadro de mensajes, así como en la base de datos de seguimiento. Por tanto, los objetos que se ejecuten en este host tendrán también acceso de lectura y escritura a estas bases de datos.  
  
    Si la desactiva, el host actual solo tendrá privilegios de escritura para las tablas de seguimiento en la base de datos de cuadro de mensajes y no tendrá acceso a la base de datos de seguimiento.  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)