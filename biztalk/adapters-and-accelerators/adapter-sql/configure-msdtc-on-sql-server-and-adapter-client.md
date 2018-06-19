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
# <a name="configure-msdtc-on-sql-server-and-adapter-client"></a><span data-ttu-id="f63d2-102">Configurar MSDTC en el cliente de SQL Server y el adaptador</span><span class="sxs-lookup"><span data-stu-id="f63d2-102">Configure MSDTC on SQL Server and adapter client</span></span>
<span data-ttu-id="f63d2-103">Las operaciones se realizan en SQL Server mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el modelo de servicio WCF o el modelo de canal WCF) se pueden realizar en un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="f63d2-103">The operations performed on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the WCF service model, or the WCF channel model) can be performed within a transaction scope.</span></span> <span data-ttu-id="f63d2-104">Si el programa de cliente tiene más de un recurso transaccional como parte de la misma transacción, la transacción obtiene elevada a una transacción MSDTC.</span><span class="sxs-lookup"><span data-stu-id="f63d2-104">If the client program has more than one transactional resource as part of the same transaction, the transaction gets elevated to an MSDTC transaction.</span></span> <span data-ttu-id="f63d2-105">Para habilitar el adaptador realizar operaciones dentro del ámbito de una transacción MSDTC, debe configurar MSDTC tanto en el equipo que ejecuta el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f63d2-105">To enable the adapter to perform operations within the scope of an MSDTC transaction, you must configure MSDTC both on the computer running the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and SQL Server.</span></span> <span data-ttu-id="f63d2-106">Además, debe agregar MSDTC a la lista de excepciones de Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="f63d2-106">Also, you must add MSDTC to the exceptions list of Windows Firewall.</span></span> <span data-ttu-id="f63d2-107">Esta sección proporciona información acerca de cómo realizar estas tareas en equipos que ejecutan el cliente de adaptador y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f63d2-107">This section provides information about how to perform these tasks on computers running the adapter client and SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f63d2-108">Realizar operaciones sobre el uso de SQL Server [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] siempre implica dos recursos: el adaptador que se conecta a SQL Server y el cuadro de mensaje de BizTalk que reside en el servidor de SQL.</span><span class="sxs-lookup"><span data-stu-id="f63d2-108">Performing operations on SQL Server using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] always involves two resources—the adapter connecting to SQL Server and the BizTalk Message Box residing on SQL Server.</span></span> <span data-ttu-id="f63d2-109">Por lo tanto, todas las operaciones realizan con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se realizan dentro del ámbito de una transacción MSDTC.</span><span class="sxs-lookup"><span data-stu-id="f63d2-109">Hence, all operations performed using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] are performed within the scope of an MSDTC transaction.</span></span> <span data-ttu-id="f63d2-110">Por lo tanto, para usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre debe habilitar MSDTC.</span><span class="sxs-lookup"><span data-stu-id="f63d2-110">So, to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always enable MSDTC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f63d2-111">Para las operaciones donde el cliente del adaptador no escribe ningún dato en la base de datos de SQL Server, como una operación de selección, no conviene la sobrecarga adicional de llevar a cabo las operaciones dentro de una transacción.</span><span class="sxs-lookup"><span data-stu-id="f63d2-111">For operations where the adapter client does not write any data to the SQL Server database, such as a Select operation, you might not want the additional overhead of performing the operations inside a transaction.</span></span> <span data-ttu-id="f63d2-112">En tales casos, puede configurar la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para realizar las operaciones sin un contexto transaccional estableciendo la **UseAmbientTransaction** enlazar la propiedad a **false**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-112">In such cases, you can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform operations without a transactional context by setting the **UseAmbientTransaction** binding property to **false**.</span></span> <span data-ttu-id="f63d2-113">Para obtener más información acerca de la propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f63d2-113">For more information about the binding property, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="f63d2-114">En tales casos, no es necesario configurar MSDTC así.</span><span class="sxs-lookup"><span data-stu-id="f63d2-114">In such cases, you do not need to configure MSDTC as well.</span></span>  
  
## <a name="configure-msdtc"></a><span data-ttu-id="f63d2-115">Configurar MSDTC</span><span class="sxs-lookup"><span data-stu-id="f63d2-115">Configure MSDTC</span></span>  
  
1.  <span data-ttu-id="f63d2-116">Abra **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-116">Open **Component Services**.</span></span>  

    <span data-ttu-id="f63d2-117">O bien, en **el administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-117">Or, In **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>  
  
2.  <span data-ttu-id="f63d2-118">Expanda **servicios de componentes**, expanda **equipos**, expanda **Mi PC**, expanda **Coordinador de transacciones distribuidas**, Haga clic en **DTC Local**y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-118">Expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="f63d2-119">Seleccione la pestaña **Seguridad** . En esta ficha, seleccione todos los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f63d2-119">Select the **Security** tab. In this tab, select all of the following:</span></span> 

  - <span data-ttu-id="f63d2-120">**Acceso a DTC desde la red**</span><span class="sxs-lookup"><span data-stu-id="f63d2-120">**Network DTC Access**</span></span>
  - <span data-ttu-id="f63d2-121">**Permitir a clientes remotos**</span><span class="sxs-lookup"><span data-stu-id="f63d2-121">**Allow Remote Clients**</span></span> 
  - <span data-ttu-id="f63d2-122">**Permitir entrantes**</span><span class="sxs-lookup"><span data-stu-id="f63d2-122">**Allow Inbound**</span></span> 
  - <span data-ttu-id="f63d2-123">**Permitir salientes**</span><span class="sxs-lookup"><span data-stu-id="f63d2-123">**Allow Outbound**</span></span> 
  - <span data-ttu-id="f63d2-124">**No hay Authetnication necesario**</span><span class="sxs-lookup"><span data-stu-id="f63d2-124">**No Authetnication Required**</span></span>
  
4.  <span data-ttu-id="f63d2-125">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="f63d2-125">Select **OK** to save your changes.</span></span>  
  
5.  <span data-ttu-id="f63d2-126">Si se le pide que reinicie el servicio MSDTC, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-126">If prompted to restarted the MSDTC service, select **Yes**.</span></span> <span data-ttu-id="f63d2-127">Una vez reiniciado el servicio MSDTC, cierre las propiedades y la MMC de servicios de componentes.</span><span class="sxs-lookup"><span data-stu-id="f63d2-127">After the MSDTC service is restarted, close the properties and the Component Services MMC.</span></span> 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a><span data-ttu-id="f63d2-128">Agregar MSDTC a la lista de excepciones de Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="f63d2-128">Add MSDTC to Windows Firewall exceptions list</span></span>  

> [!TIP] 
>  <span data-ttu-id="f63d2-129">Coordinador de transacción distribuida de Microsoft (MSDTC) se pueden permitirse ya en el firewall.</span><span class="sxs-lookup"><span data-stu-id="f63d2-129">Microsoft Distributed Tansaction Coordinator (MSDTC) may already be allowed in your firewall.</span></span> <span data-ttu-id="f63d2-130">Si es así, se muestra como una regla de entrada.</span><span class="sxs-lookup"><span data-stu-id="f63d2-130">If so, it is listed as an Inbound Rule.</span></span> <span data-ttu-id="f63d2-131">Si no aparece, use esta sección para permitir MSDTC.</span><span class="sxs-lookup"><span data-stu-id="f63d2-131">If it's not listed, use this section to allow MSDTC.</span></span> 

1.  <span data-ttu-id="f63d2-132">Abra **Firewall de Windows**y seleccione **configuración avanzada** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="f63d2-132">Open **Windows Firewall**, and select **Advanced Settings** on the left.</span></span>  

    <span data-ttu-id="f63d2-133">O bien, en **el administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **Firewall de Windows con seguridad avanzada**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-133">Or, In **Server Manager**, select **Tools**, and then select **Windows Firewall with Advanced Security**.</span></span>  
  
2.  <span data-ttu-id="f63d2-134">Haga clic en **reglas de entrada**y seleccione **nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-134">Right click **Inbound Rules**, and select **New Rule**.</span></span>  
  
3.  <span data-ttu-id="f63d2-135">En el asistente:</span><span class="sxs-lookup"><span data-stu-id="f63d2-135">In the wizard:</span></span> 

    1. <span data-ttu-id="f63d2-136">Seleccione **programa**y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-136">Select **Program**, and select **Next**.</span></span> 
    2. <span data-ttu-id="f63d2-137">Establecer el **la ruta del programa** a `%SystemRoot%\system32\msdtc.exe`y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-137">Set the **program path** to `%SystemRoot%\system32\msdtc.exe`, and select **Next**.</span></span>  
    3. <span data-ttu-id="f63d2-138">**Permitir la conexión**y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-138">**Allow the connection**, and select **Next**.</span></span>
    4. <span data-ttu-id="f63d2-139">Seleccione **dominio**y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-139">Select **Domain**, and select **Next**.</span></span>
    5. <span data-ttu-id="f63d2-140">Escriba cualquier nombre, como `MSDTC for Oracle EBS`y seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-140">Enter any name, such as `MSDTC for Oracle EBS`, and select **Finish**.</span></span>
  
5.  <span data-ttu-id="f63d2-141">Complete el asistente y cierre Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="f63d2-141">Complete the wizard, and close Windows Firewall.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f63d2-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="f63d2-142">See Also</span></span>  
[<span data-ttu-id="f63d2-143">Desarrollar las aplicaciones de SQL</span><span class="sxs-lookup"><span data-stu-id="f63d2-143">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)