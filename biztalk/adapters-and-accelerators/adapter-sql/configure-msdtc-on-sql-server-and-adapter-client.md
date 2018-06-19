---
title: Configurar MSDTC en el cliente de SQL Server y el adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c87f455-a8c4-4169-bf18-695926136df1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf519044dc28d417d85682189dd4a52585310ac0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222924"
---
# <a name="configure-msdtc-on-sql-server-and-adapter-client"></a>Configurar MSDTC en el cliente de SQL Server y el adaptador
Las operaciones se realizan en SQL Server mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el modelo de servicio WCF o el modelo de canal WCF) se pueden realizar en un ámbito de transacción. Si el programa de cliente tiene más de un recurso transaccional como parte de la misma transacción, la transacción obtiene elevada a una transacción MSDTC. Para habilitar el adaptador realizar operaciones dentro del ámbito de una transacción MSDTC, debe configurar MSDTC tanto en el equipo que ejecuta el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y SQL Server. Además, debe agregar MSDTC a la lista de excepciones de Firewall de Windows. Esta sección proporciona información acerca de cómo realizar estas tareas en equipos que ejecutan el cliente de adaptador y SQL Server.  
  
> [!NOTE]
>  Realizar operaciones sobre el uso de SQL Server [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] siempre implica dos recursos: el adaptador que se conecta a SQL Server y el cuadro de mensaje de BizTalk que reside en el servidor de SQL. Por lo tanto, todas las operaciones realizan con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se realizan dentro del ámbito de una transacción MSDTC. Por lo tanto, para usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre debe habilitar MSDTC.  
  
> [!NOTE]
>  Para las operaciones donde el cliente del adaptador no escribe ningún dato en la base de datos de SQL Server, como una operación de selección, no conviene la sobrecarga adicional de llevar a cabo las operaciones dentro de una transacción. En tales casos, puede configurar la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para realizar las operaciones sin un contexto transaccional estableciendo la **UseAmbientTransaction** enlazar la propiedad a **false**. Para obtener más información acerca de la propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). En tales casos, no es necesario configurar MSDTC así.  
  
## <a name="configure-msdtc"></a>Configurar MSDTC  
  
1.  Abra **servicios de componentes**.  

    O bien, en **el administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **servicios de componentes**.  
  
2.  Expanda **servicios de componentes**, expanda **equipos**, expanda **Mi PC**, expanda **Coordinador de transacciones distribuidas**, Haga clic en **DTC Local**y seleccione **propiedades**.  
  
3.  Seleccione la pestaña **Seguridad** . En esta ficha, seleccione todos los elementos siguientes: 

  - **Acceso a DTC desde la red**
  - **Permitir a clientes remotos** 
  - **Permitir entrantes** 
  - **Permitir salientes** 
  - **No hay Authetnication necesario**
  
4.  Seleccione **Aceptar** para guardar los cambios.  
  
5.  Si se le pide que reinicie el servicio MSDTC, seleccione **Sí**. Una vez reiniciado el servicio MSDTC, cierre las propiedades y la MMC de servicios de componentes. 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>Agregar MSDTC a la lista de excepciones de Firewall de Windows  

> [!TIP] 
>  Coordinador de transacción distribuida de Microsoft (MSDTC) se pueden permitirse ya en el firewall. Si es así, se muestra como una regla de entrada. Si no aparece, use esta sección para permitir MSDTC. 

1.  Abra **Firewall de Windows**y seleccione **configuración avanzada** a la izquierda.  

    O bien, en **el administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **Firewall de Windows con seguridad avanzada**.  
  
2.  Haga clic en **reglas de entrada**y seleccione **nueva regla**.  
  
3.  En el asistente: 

    1. Seleccione **programa**y seleccione **siguiente**. 
    2. Establecer el **la ruta del programa** a `%SystemRoot%\system32\msdtc.exe`y seleccione **siguiente**.  
    3. **Permitir la conexión**y seleccione **siguiente**.
    4. Seleccione **dominio**y seleccione **siguiente**.
    5. Escriba cualquier nombre, como `MSDTC for Oracle EBS`y seleccione **finalizar**.
  
5.  Complete el asistente y cierre Firewall de Windows. 
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de SQL](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)