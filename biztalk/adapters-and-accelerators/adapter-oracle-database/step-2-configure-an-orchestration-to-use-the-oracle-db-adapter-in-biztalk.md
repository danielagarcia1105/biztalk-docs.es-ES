---
title: 'Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server para usar el adaptador de base de datos de Oracle | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 598b4ab0-ff22-4dfa-aa9c-774c60c90227
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0a8b8035b27babeacd6e5ade8c2cc40c8af2d75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007869"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-to-use-the-oracle-database-adapter"></a><span data-ttu-id="94f55-102">Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server para usar el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="94f55-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the Oracle Database adapter</span></span>
<span data-ttu-id="94f55-103">![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="94f55-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="94f55-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="94f55-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="94f55-105">**Objetivo:** en este paso, realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="94f55-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="94f55-106">Crear un WCF-Custom envío y recepción de puerto para enviar y recibir mensajes de la base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94f55-106">Create a WCF-Custom send-receive port to send and receive messages from the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="94f55-107">Configurar este puerto para utilizar las asignaciones que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="94f55-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
- <span data-ttu-id="94f55-108">Configurar la orquestación ha implementado en el último paso para usar el puerto de WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="94f55-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="94f55-109">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="94f55-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="94f55-110">Debe haber implementado la orquestación de BizTalk para el que desea configurar el puerto de WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="94f55-110">You must have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="94f55-111">Para crear un puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="94f55-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="94f55-112">Cuando se genere el esquema para una operación en la base de datos de Oracle mediante [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], un archivo de enlace también se agrega al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="94f55-112">When you generate schema for an operation on the Oracle database using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="94f55-113">Puede importar este archivo de enlace en el BizTalk aplicación para crear un WCF-Custom envío-puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="94f55-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="94f55-114">Para obtener instrucciones sobre cómo importar un archivo de enlace, consulte [importar enlaces](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f).</span><span class="sxs-lookup"><span data-stu-id="94f55-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f).</span></span>  
  
2. <span data-ttu-id="94f55-115">Después de importar el archivo de enlace, se crea un puerto de envío en el **puertos de envío** carpeta en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="94f55-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3. <span data-ttu-id="94f55-116">Haga clic en el puerto de WCF-Custom y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="94f55-116">Right-click the WCF-Custom port and click **Properties**.</span></span>  
  
4. <span data-ttu-id="94f55-117">En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en el **General** ficha. En el panel derecho, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="94f55-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="94f55-118">En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** pestaña y especifique las credenciales para conectarse a una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="94f55-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and specify the credentials to connect to an Oracle database.</span></span>  
  
6. <span data-ttu-id="94f55-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94f55-119">Click **OK**.</span></span>  
  
7. <span data-ttu-id="94f55-120">En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de entrada**.</span><span class="sxs-lookup"><span data-stu-id="94f55-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="94f55-121">En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **ResponseMap**.</span><span class="sxs-lookup"><span data-stu-id="94f55-121">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="94f55-122">![Configurar asignación de entrada](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")</span><span class="sxs-lookup"><span data-stu-id="94f55-122">![Configure inbound map](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")</span></span>  
  
8. <span data-ttu-id="94f55-123">En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de salida**.</span><span class="sxs-lookup"><span data-stu-id="94f55-123">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="94f55-124">En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **RequestMap**.</span><span class="sxs-lookup"><span data-stu-id="94f55-124">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
    <span data-ttu-id="94f55-125">![Configurar asignación de salida](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")</span><span class="sxs-lookup"><span data-stu-id="94f55-125">![Configure outbound map](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")</span></span>  
  
9. <span data-ttu-id="94f55-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94f55-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="94f55-127">Para configurar la aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="94f55-127">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="94f55-128">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y expanda la aplicación de BizTalk donde se implementa la orquestación.</span><span class="sxs-lookup"><span data-stu-id="94f55-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="94f55-129">Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="94f55-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="94f55-130">En el panel izquierdo, haga clic en el que se va a configurar la orquestación.</span><span class="sxs-lookup"><span data-stu-id="94f55-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="94f55-131">En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="94f55-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="94f55-132">En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="94f55-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="94f55-133">Seleccione el puerto de archivo donde se colocará un mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="94f55-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="94f55-134">La orquestación de BizTalk usarán el mensaje de solicitud y enviarla a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="94f55-134">The BizTalk orchestration will consume the request message and send it to the Oracle database.</span></span>  
  
   2. <span data-ttu-id="94f55-135">Seleccione el puerto de archivo donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="94f55-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the Oracle database.</span></span>  
  
   3. <span data-ttu-id="94f55-136">Seleccione el puerto de envío WCF-Custom que creó anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="94f55-136">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   4. <span data-ttu-id="94f55-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94f55-137">Click **OK**.</span></span>  
  
      <span data-ttu-id="94f55-138">Para obtener más información acerca de cómo configurar una aplicación, consulte "Cómo configurar una aplicación" en [ http://go.microsoft.com/fwlink/?LinkID=196961 ](http://go.microsoft.com/fwlink/?LinkID=196961).</span><span class="sxs-lookup"><span data-stu-id="94f55-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="94f55-139">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="94f55-139">Next Steps</span></span>  
 <span data-ttu-id="94f55-140">Ahora ha completado la migración de su proyecto de BizTalk vPrev para un proyecto de BizTalk que envía mensajes a la base de datos de Oracle con el basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94f55-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="94f55-141">Ahora debe probar la aplicación migrada de BizTalk mediante el envío de un mensaje de solicitud para realizar una operación de inserción en la base de datos de Oracle, como se describe en [paso 3: probar la aplicación migrada al adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="94f55-141">You must now test the migrated BizTalk application by sending a request message to perform an Insert operation on the Oracle database, as described in [Step 3: Test the migrated application to Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f55-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="94f55-142">See Also</span></span>  
 <span data-ttu-id="94f55-143">[Tutorial: Migración de proyectos de BizTalk](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span><span class="sxs-lookup"><span data-stu-id="94f55-143">[Tutorial: Migrating BizTalk Projects](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span></span>