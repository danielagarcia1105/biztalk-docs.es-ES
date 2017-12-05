---
title: Recibir IDOC de SAP en un contexto transaccional usando el servidor BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactional context
- IDOCs, receiving in a transactional context using BizTalk Server
ms.assetid: 6a01bb82-7292-4b70-8ad7-996d389a9365
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8903b6010555b3c7c6aba9a07e12c9204bcf19c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server"></a><span data-ttu-id="07cb5-102">Recibir IDOC de SAP en un contexto transaccional usando el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="07cb5-102">Receive IDOCs from SAP in a Transactional Context using BizTalk Server</span></span>
<span data-ttu-id="07cb5-103">Recibir IDOC en un contexto transaccional es similar a la recepción de tRFCs en un contexto transaccional.</span><span class="sxs-lookup"><span data-stu-id="07cb5-103">Receiving IDOC in a transactional context is similar to receiving tRFCs in a transactional context.</span></span> <span data-ttu-id="07cb5-104">En tal caso, el IDOC recibido desde el sistema SAP contiene un TID como parte de la  *\<TransactionalRfcOperationIdentifier\>*  elemento.</span><span class="sxs-lookup"><span data-stu-id="07cb5-104">In such a case, the IDOC received from the SAP system contains a TID as part of the *\<TransactionalRfcOperationIdentifier\>* element.</span></span> <span data-ttu-id="07cb5-105">Este TID se conserva en una base de datos SQL por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="07cb5-105">This TID is persisted in a SQL database by the adapter.</span></span> <span data-ttu-id="07cb5-106">Si el código ABAP en el sistema SAP que envía el IDOC tiene una instrucción "COMMIT WORK", se elimina el TID de la base de datos SQL después de una respuesta se envía al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="07cb5-106">If the ABAP code in the SAP system that sends the IDOC has a "COMMIT WORK" statement, the TID is deleted from the SQL database after a response is sent back to the SAP system.</span></span>  
  
 <span data-ttu-id="07cb5-107">La orquestación necesita para recibir un IDOC es similar con independencia de si se recibe el IDOC en un contexto transaccional o no.</span><span class="sxs-lookup"><span data-stu-id="07cb5-107">The orchestration required to receive an IDOC is similar irrespective of whether the IDOC is received in a transactional context or not.</span></span> <span data-ttu-id="07cb5-108">Vea [recibir IDOC desde SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="07cb5-108">See [Receive IDOCs from SAP by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md).</span></span> <span data-ttu-id="07cb5-109">Sin embargo, debe realizar ciertas tareas adicionales para asegurarse de que se recibe lo IDOC en un contexto transaccional.</span><span class="sxs-lookup"><span data-stu-id="07cb5-109">However, you need to perform certain additional tasks to make sure the IDOCs are received in a transactional context.</span></span>  
  
1.  <span data-ttu-id="07cb5-110">En tiempo de diseño, generar el esquema para un IDOC que desea recibir.</span><span class="sxs-lookup"><span data-stu-id="07cb5-110">At design time, generate the schema for an IDOC that you want to receive.</span></span>  
  
2.  <span data-ttu-id="07cb5-111">En tiempo de ejecución, asegúrese de establecer la propiedad de enlace **TidDatabaseConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="07cb5-111">At run time, make sure you set the binding property **TidDatabaseConnectionString**.</span></span> <span data-ttu-id="07cb5-112">Esta propiedad toma la cadena de conexión para conectarse a una base de datos SQL para almacenar el TID.</span><span class="sxs-lookup"><span data-stu-id="07cb5-112">This property takes the connection string to connect to a SQL database to store the TID.</span></span> <span data-ttu-id="07cb5-113">Una cadena de conexión de ejemplo sería:</span><span class="sxs-lookup"><span data-stu-id="07cb5-113">A sample connection string would look like:</span></span>  
  
    ```  
    Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
    ```  
  
     <span data-ttu-id="07cb5-114">Para obtener más información acerca de la propiedad de enlace y cómo configurarlo, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="07cb5-114">For more information about the binding property and how to set it, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="07cb5-115">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para instalación instala una instancia de SQL en el script, SapAdapter-DbScript-Install.sql, que se debe ejecutar el Administrador de SQL Server para crear una base de datos y los objetos de base de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07cb5-115">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard installs a SQL script, SapAdapter-DbScript-Install.sql, which must be run by the SQL Server administrator to create a database and the database objects in SQL Server.</span></span> <span data-ttu-id="07cb5-116">La secuencia de comandos se instala normalmente en  *\<unidad de instalación\>*: programa FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07cb5-116">The script is typically installed at *\<installation drive\>*:Program FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
    >   
    >  <span data-ttu-id="07cb5-117">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza estos objetos para conservar el TID.</span><span class="sxs-lookup"><span data-stu-id="07cb5-117">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses these objects to persist the TIDs.</span></span> <span data-ttu-id="07cb5-118">Por lo tanto, el Administrador de SQL Server debe asegurarse de que el nombre de usuario proporcionar como parte de la cadena de conexión tiene privilegios suficientes para ejecutar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="07cb5-118">So, the SQL Server administrator must ensure that the user name provide as part of the connection string has sufficient privileges to execute the stored procedures.</span></span> <span data-ttu-id="07cb5-119">También puede optar por la autenticación de Windows siempre que el usuario de Windows tenga permisos suficientes para ejecutar procedimientos almacenados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="07cb5-119">You can also opt for Windows authentication provided the Windows user has sufficient permissions to execute stored procedures in the database.</span></span>  
  
3.  <span data-ttu-id="07cb5-120">Asegúrese de que MSDTC está habilitado en el equipo donde está instalado el adaptador.</span><span class="sxs-lookup"><span data-stu-id="07cb5-120">Make sure MSDTC is enabled on the computer where the adapter is installed.</span></span> <span data-ttu-id="07cb5-121">Realice los pasos siguientes para habilitar MSDTC.</span><span class="sxs-lookup"><span data-stu-id="07cb5-121">Perform the following steps to enable MSDTC.</span></span>  
  
    1.  <span data-ttu-id="07cb5-122">Inicie el complemento de MMC Servicios de componentes.</span><span class="sxs-lookup"><span data-stu-id="07cb5-122">Start the Component Services MMC snap-in.</span></span>  
  
    2.  <span data-ttu-id="07cb5-123">En el complemento MMC Servicios de componentes, en el panel izquierdo expanda **servicios de componentes**, expanda **equipos**, haga clic en **Mi PC**y haga clic en  **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="07cb5-123">In the Component Services MMC snap-in, from the left pane expand **Component Services**, expand **Computers**, right-click **My Computer**, and click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="07cb5-124">En el **propiedades de Mi PC** cuadro de diálogo, haga clic en el **MSDTC** ficha.</span><span class="sxs-lookup"><span data-stu-id="07cb5-124">In the **My Computer Properties** dialog box, click the **MSDTC** tab.</span></span>  
  
    4.  <span data-ttu-id="07cb5-125">En el **configuración de transacción** sección, haga clic en el **configuración de seguridad** botón.</span><span class="sxs-lookup"><span data-stu-id="07cb5-125">In the **Transaction Configuration** section, click the **Security Configuration** button.</span></span>  
  
    5.  <span data-ttu-id="07cb5-126">En el **configuración de seguridad** cuadro de diálogo, seleccione la **acceso de red DTC** casilla de verificación y dentro de ella, seleccione la **Permitir clientes remotos** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="07cb5-126">In the **Security Configuration** dialog box, select the **Network DTC Access** check box and within that, select the **Allow Remote Clients** check box.</span></span>  
  
    6.  <span data-ttu-id="07cb5-127">En el **comunicación con el Administrador de transacciones** sección, seleccione la **Permitir entrantes** y **Permitir salientes** casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="07cb5-127">In the **Transaction Manager Communication** section, select the **Allow Inbound** and **Allow Outbound** check boxes.</span></span>  
  
    7.  <span data-ttu-id="07cb5-128">En el **configuración de seguridad** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="07cb5-128">In the **Security Configuration** dialog box, click **OK**.</span></span>  
  
    8.  <span data-ttu-id="07cb5-129">Haga clic en **Sí** en el cuadro de diálogo que le informa que se reiniciará el servicio MSDTC.</span><span class="sxs-lookup"><span data-stu-id="07cb5-129">Click **Yes** in the dialog box informing that the MSDTC service will be restarted.</span></span> <span data-ttu-id="07cb5-130">Una vez reiniciado el servicio MSDTC, haga clic en **Aceptar** en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="07cb5-130">After the MSDTC service is restarted, click **OK** on the dialog box.</span></span>  
  
    9. <span data-ttu-id="07cb5-131">En el **propiedades de Mi PC** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="07cb5-131">In the **My Computer Properties** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="07cb5-132">Agregar MSDTC a la lista de excepciones de Firewall de Windows, si todavía no ha agregado.</span><span class="sxs-lookup"><span data-stu-id="07cb5-132">Add MSDTC to the Windows Firewall exception list, if not already added.</span></span> <span data-ttu-id="07cb5-133">Ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="07cb5-133">Run the following command.</span></span>  
  
    ```  
    netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="07cb5-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="07cb5-134">See Also</span></span>  
[<span data-ttu-id="07cb5-135">Desarrollar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="07cb5-135">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)