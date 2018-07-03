---
title: 'Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server mediante el adaptador de SQL | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6152560-5ff0-4bdc-818c-e906b9642f52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6293758d9891d86e137d07e9735ce37162d6a96b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984029"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-using-the-sql-adapter"></a><span data-ttu-id="3602a-102">Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server mediante el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="3602a-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console using the SQL adapter</span></span>
<span data-ttu-id="3602a-103">![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="3602a-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="3602a-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="3602a-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="3602a-105">**Objetivo:** en este paso, realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="3602a-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="3602a-106">Crear un WCF-Custom envío y recepción de puerto para enviar y recibir mensajes de la base de datos de SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3602a-106">Create a WCF-Custom send-receive port to send and receive messages from the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3602a-107">Configurar este puerto para utilizar las asignaciones que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="3602a-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
- <span data-ttu-id="3602a-108">Configurar la orquestación ha implementado en el paso anterior para usar el puerto de WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="3602a-108">Configure the orchestration you deployed in the previous step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3602a-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3602a-109">Prerequisites</span></span>  
 <span data-ttu-id="3602a-110">Debe haber implementado la orquestación de BizTalk para el que desea configurar el puerto de WCF-Custom, como se describe en [paso 1: modificar el proyecto vPrev de BizTalk mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="3602a-110">You should have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port as described in [Step 1: Modify the vPrev BizTalk Project using the SQL adapter](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md).</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="3602a-111">Para crear un puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="3602a-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="3602a-112">Cuando se genere el esquema para una operación en la base de datos de SQL Server mediante [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], un archivo de enlace también se agrega al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3602a-112">When you generate schema for an operation on the SQL Server database using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="3602a-113">Puede importar este archivo de enlace en el BizTalk aplicación para crear un WCF-Custom envío-puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="3602a-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="3602a-114">Para obtener instrucciones sobre cómo importar un archivo de enlace, consulte [importar enlaces](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53).</span><span class="sxs-lookup"><span data-stu-id="3602a-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53).</span></span>  
  
2. <span data-ttu-id="3602a-115">Después de importar el archivo de enlace, se crea un puerto de envío en el **puertos de envío** carpeta en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="3602a-115">After you import the binding file, a send port is created under the **Send Ports** folder in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
3. <span data-ttu-id="3602a-116">Haga clic en el puerto de WCF-Custom y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3602a-116">Right-click the WCF-Custom port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="3602a-117">En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en el **General** ficha. En el panel derecho, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="3602a-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="3602a-118">En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha, especifique las credenciales para conectarse a una base de datos de SQL Server y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3602a-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, specify the credentials to connect to a SQL Server database, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="3602a-119">En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de entrada**.</span><span class="sxs-lookup"><span data-stu-id="3602a-119">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="3602a-120">En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **ResponseMap**.</span><span class="sxs-lookup"><span data-stu-id="3602a-120">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="3602a-121">![Configurar asignación de entrada](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")</span><span class="sxs-lookup"><span data-stu-id="3602a-121">![Configure inbound map](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")</span></span>  
  
7. <span data-ttu-id="3602a-122">En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de salida**.</span><span class="sxs-lookup"><span data-stu-id="3602a-122">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="3602a-123">En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **RequestMap**.</span><span class="sxs-lookup"><span data-stu-id="3602a-123">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
    <span data-ttu-id="3602a-124">![Configurar asignación de salida](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")</span><span class="sxs-lookup"><span data-stu-id="3602a-124">![Configure outbound map](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")</span></span>  
  
8. <span data-ttu-id="3602a-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3602a-125">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="3602a-126">Para configurar la aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3602a-126">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="3602a-127">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación de BizTalk donde se implementa la orquestación.</span><span class="sxs-lookup"><span data-stu-id="3602a-127">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="3602a-128">Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="3602a-128">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="3602a-129">En el panel izquierdo, haga clic en el que se va a configurar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="3602a-129">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="3602a-130">En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3602a-130">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="3602a-131">En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="3602a-131">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
   1.  <span data-ttu-id="3602a-132">Seleccione el puerto de archivo donde se colocará un mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="3602a-132">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="3602a-133">La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3602a-133">The BizTalk orchestration will consume the request message and send it to the SQL Server database.</span></span>  
  
   2.  <span data-ttu-id="3602a-134">Seleccione el puerto de archivo donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3602a-134">Select the file port where the BizTalk orchestration will drop the response message containing the response from the SQL Server database.</span></span>  
  
   3.  <span data-ttu-id="3602a-135">Seleccione el puerto de envío WCF-Custom que creó anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="3602a-135">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   4.  <span data-ttu-id="3602a-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3602a-136">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3602a-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3602a-137">Next Steps</span></span>  
 <span data-ttu-id="3602a-138">Ahora ha completado la migración de su proyecto de BizTalk vPrev para un proyecto de BizTalk que envía mensajes a la base de datos de SQL Server con el basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3602a-138">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the SQL Server database using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3602a-139">Ahora debe probar la aplicación migrada de BizTalk mediante el envío de un mensaje de solicitud para realizar una operación de inserción en la base de datos de SQL Server, como se describe en [paso 3: probar la aplicación migrados que usa el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="3602a-139">You must now test the migrated BizTalk application by sending a request message to perform an Insert operation on the SQL Server database, as described in [Step 3: Test the Migrated Application that uses the SQL adapter](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3602a-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="3602a-140">See Also</span></span>  
 [<span data-ttu-id="3602a-141">Tutorial 1: Migrar proyectos de BizTalk para el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="3602a-141">Tutorial 1: Migrate BizTalk Projects to the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)