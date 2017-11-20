---
title: Recibir llamadas de tRFC entrada de SAP mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving using BizTalk Server
- tRFCs, sample
ms.assetid: 500eedea-3d27-478c-a64c-903a1fa2b02f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3ad06768a5156b71d4d0da77b778f22d3d09fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-inbound-trfc-calls-from-sap-using-biztalk-server"></a><span data-ttu-id="3f950-102">Recibir llamadas de tRFC entrada de SAP con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3f950-102">Receive Inbound tRFC Calls from SAP using BizTalk Server</span></span>
<span data-ttu-id="3f950-103">Una llamada al servidor de tRFC es una llamada de servidor RFC transaccional.</span><span class="sxs-lookup"><span data-stu-id="3f950-103">A tRFC server call is a transactional RFC server call.</span></span> <span data-ttu-id="3f950-104">La orquestación necesita para recibir una solicitud de cambio en un contexto transaccional es similar a la orquestación para recibir cualquier otro RFC entrante enviado desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3f950-104">The orchestration required to receive an RFC in a transactional context is similar to the orchestration to receive any other inbound RFC sent from an SAP system.</span></span> <span data-ttu-id="3f950-105">Sin embargo, debe realizar ciertas tareas adicionales para asegurarse de que se reciben las RFC en un contexto transaccional.</span><span class="sxs-lookup"><span data-stu-id="3f950-105">However, you need to perform certain additional tasks to make sure the RFCs are received in a transactional context.</span></span> <span data-ttu-id="3f950-106">Para obtener más información acerca de la recepción de una solicitud de cambio entrante desde el sistema SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [recibir llamadas entrantes de RFC de SAP mediante el uso de BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="3f950-106">For more information about receiving an inbound RFC from the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Receive Inbound RFC Calls from SAP by using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).</span></span> <span data-ttu-id="3f950-107">Para obtener más información acerca de cómo los [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite recibir llamadas de tRFC entrante desde un sistema SAP, consulte [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="3f950-107">For more information about how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports receiving inbound tRFC calls from an SAP system, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
 <span data-ttu-id="3f950-108">Recibir un tRFC entrante enviado desde un sistema SAP es similar a la recepción de una solicitud de cambio de entrada, con las siguientes diferencias:</span><span class="sxs-lookup"><span data-stu-id="3f950-108">Receiving an inbound tRFC sent from an SAP system is similar to receiving an inbound RFC, with the following differences:</span></span>  
  
1.  <span data-ttu-id="3f950-109">En tiempo de ejecución, al generar el esquema, asegúrese de seleccionar el tRFC desde el **TRFC** nodo.</span><span class="sxs-lookup"><span data-stu-id="3f950-109">At design time, while generating the schema, make sure you select the tRFC from under the **TRFC** node.</span></span>  
  
2.  <span data-ttu-id="3f950-110">En tiempo de ejecución, asegúrese de establecer la propiedad de enlace **TidDatabaseConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="3f950-110">At run time, make sure you set the binding property **TidDatabaseConnectionString**.</span></span> <span data-ttu-id="3f950-111">Esta propiedad toma la cadena de conexión para conectarse a una base de datos SQL para almacenar el TID.</span><span class="sxs-lookup"><span data-stu-id="3f950-111">This property takes the connection string to connect to a SQL database to store the TID.</span></span> <span data-ttu-id="3f950-112">Una cadena de conexión de ejemplo sería:</span><span class="sxs-lookup"><span data-stu-id="3f950-112">A sample connection string would look like:</span></span>  
  
    ```  
    Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
    ```  
  
     <span data-ttu-id="3f950-113">Para obtener más información acerca de la propiedad de enlace y cómo configurarlo, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3f950-113">For more information about the binding property and how to set it, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3f950-114">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para instalación instala una instancia de SQL en el script, SapAdapter-DbScript-Install.sql, que se debe ejecutar el Administrador de SQL Server para crear una base de datos y los objetos de base de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3f950-114">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard installs a SQL script, SapAdapter-DbScript-Install.sql, which must be run by the SQL Server administrator to create a database and the database objects in SQL Server.</span></span> <span data-ttu-id="3f950-115">La secuencia de comandos se instala normalmente en  *\<unidad de instalación >: programa FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]* .</span><span class="sxs-lookup"><span data-stu-id="3f950-115">The script is typically installed at *\<installation drive>:Program FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]*.</span></span>  
    >   
    >  <span data-ttu-id="3f950-116">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza estos objetos para conservar el TID.</span><span class="sxs-lookup"><span data-stu-id="3f950-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses these objects to persist the TIDs.</span></span> <span data-ttu-id="3f950-117">Por lo tanto, el Administrador de SQL Server debe asegurarse de que el nombre de usuario proporcionar como parte de la cadena de conexión tiene privilegios suficientes para ejecutar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="3f950-117">So, the SQL Server administrator must ensure that the user name provide as part of the connection string has sufficient privileges to execute the stored procedures.</span></span> <span data-ttu-id="3f950-118">También puede optar por la autenticación de Windows siempre que el usuario de Windows tenga permisos suficientes para ejecutar procedimientos almacenados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3f950-118">You can also opt for Windows authentication provided the Windows user has sufficient permissions to execute stored procedures in the database.</span></span>  
  
3.  <span data-ttu-id="3f950-119">Asegúrese de que MSDTC está habilitado en el equipo donde está instalado el adaptador.</span><span class="sxs-lookup"><span data-stu-id="3f950-119">Make sure MSDTC is enabled on the computer where the adapter is installed.</span></span> <span data-ttu-id="3f950-120">Realice los pasos siguientes para habilitar MSDTC.</span><span class="sxs-lookup"><span data-stu-id="3f950-120">Perform the following steps to enable MSDTC.</span></span>  
  
    1.  <span data-ttu-id="3f950-121">Inicie el complemento de MMC Servicios de componentes.</span><span class="sxs-lookup"><span data-stu-id="3f950-121">Start the Component Services MMC snap-in.</span></span>  
  
    2.  <span data-ttu-id="3f950-122">En el complemento MMC Servicios de componentes, en el panel izquierdo expanda **servicios de componentes**, expanda **equipos**, haga clic en **Mi PC**y haga clic en  **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3f950-122">In the Component Services MMC snap-in, from the left pane expand **Component Services**, expand **Computers**, right-click **My Computer**, and click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="3f950-123">En el **propiedades de Mi PC** cuadro de diálogo, haga clic en el **MSDTC** ficha.</span><span class="sxs-lookup"><span data-stu-id="3f950-123">In the **My Computer Properties** dialog box, click the **MSDTC** tab.</span></span>  
  
    4.  <span data-ttu-id="3f950-124">En el **configuración de transacción** sección, haga clic en el **configuración de seguridad** botón.</span><span class="sxs-lookup"><span data-stu-id="3f950-124">In the **Transaction Configuration** section, click the **Security Configuration** button.</span></span>  
  
    5.  <span data-ttu-id="3f950-125">En el **configuración de seguridad** cuadro de diálogo, seleccione la **acceso de red DTC** casilla de verificación y dentro de ella, seleccione la **Permitir clientes remotos** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="3f950-125">In the **Security Configuration** dialog box, select the **Network DTC Access** check box and within that, select the **Allow Remote Clients** check box.</span></span>  
  
    6.  <span data-ttu-id="3f950-126">En el **comunicación con el Administrador de transacciones** sección, seleccione la **Permitir entrantes** y **Permitir salientes** casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="3f950-126">In the **Transaction Manager Communication** section, select the **Allow Inbound** and **Allow Outbound** check boxes.</span></span>  
  
    7.  <span data-ttu-id="3f950-127">En el **configuración de seguridad** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f950-127">In the **Security Configuration** dialog box, click **OK**.</span></span>  
  
    8.  <span data-ttu-id="3f950-128">Haga clic en **Sí** en el cuadro de diálogo que le informa que se reiniciará el servicio MSDTC.</span><span class="sxs-lookup"><span data-stu-id="3f950-128">Click **Yes** in the dialog box informing that the MSDTC service will be restarted.</span></span> <span data-ttu-id="3f950-129">Una vez reiniciado el servicio MSDTC, haga clic en **Aceptar** en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3f950-129">After the MSDTC service is restarted, click **OK** on the dialog box.</span></span>  
  
    9. <span data-ttu-id="3f950-130">En el **propiedades de Mi PC** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f950-130">In the **My Computer Properties** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="3f950-131">Agregar MSDTC a la lista de excepciones de Firewall de Windows, si todavía no ha agregado.</span><span class="sxs-lookup"><span data-stu-id="3f950-131">Add MSDTC to the Windows Firewall exception list, if not already added.</span></span> <span data-ttu-id="3f950-132">Ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="3f950-132">Run the following command.</span></span>  
  
    ```  
    netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="3f950-133">Una llamada de tRFC entrante se usa al recibir IDOC desde el sistema SAP en un contexto "transaccional".</span><span class="sxs-lookup"><span data-stu-id="3f950-133">An inbound tRFC call is used while receiving IDOCs from the SAP system in a "transactional" context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f950-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f950-134">See Also</span></span>  
[<span data-ttu-id="3f950-135">Desarrollar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3f950-135">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)