---
title: 'Paso 2: Enviar un 0c4 consulta | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: ce50b892-c87c-414a-94c5-b40947fec68f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c621b6891b816f72603202bd6f2214882eb4b5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-submitting-a-0c4-query"></a><span data-ttu-id="a08ae-102">Paso 2: Enviar un 0c consultar 4</span><span class="sxs-lookup"><span data-stu-id="a08ae-102">Step 2: Submitting a 0C4 Query</span></span>
<span data-ttu-id="a08ae-103">En este paso, preparará y enviará una solicitud mediante el proceso de interfaz de socio (PIP) 0C4: consulta sincrónica de prueba.</span><span class="sxs-lookup"><span data-stu-id="a08ae-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 0C4 - Synchronous Test Query.</span></span> <span data-ttu-id="a08ae-104">RosettaNet define este PIP para asegurarse de que un canal de comunicación sincrónica funciona correctamente entre dos organizaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="a08ae-104">RosettaNet defines this PIP to make sure a successful synchronous communication channel is working correctly between two different organizations.</span></span> <span data-ttu-id="a08ae-105">Dado que este PIP tiene un patrón de comunicación sincrónica, [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] no envía confirmaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="a08ae-105">Because this PIP has a synchronous communication pattern, [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] does not send receipt acknowledgements.</span></span> <span data-ttu-id="a08ae-106">Este PIP sigue el mismo patrón que otros PIP sincrónicos de doble acción, como el PIP 2A9: consulta de información técnica del producto.</span><span class="sxs-lookup"><span data-stu-id="a08ae-106">This PIP follows the same pattern as other synchronous double action PIPs, such as PIP 2A9 - Query Technical Product Information.</span></span>  
  
### <a name="to-submit-a-0c4---synchronous-test-query"></a><span data-ttu-id="a08ae-107">Para enviar un 0C4: consulta sincrónica de prueba</span><span class="sxs-lookup"><span data-stu-id="a08ae-107">To submit a 0C4 - Synchronous Test Query</span></span>  
  
1.  <span data-ttu-id="a08ae-108">En el equipo de Fabrikam, en Internet Explorer, busque y abra http://localhost/LOBWebApplication/default.aspx.</span><span class="sxs-lookup"><span data-stu-id="a08ae-108">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="a08ae-109">En la página **Enviar mensaje** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a08ae-109">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="a08ae-110">Use</span><span class="sxs-lookup"><span data-stu-id="a08ae-110">Use this</span></span>|<span data-ttu-id="a08ae-111">Para</span><span class="sxs-lookup"><span data-stu-id="a08ae-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a08ae-112">**Organización principal**</span><span class="sxs-lookup"><span data-stu-id="a08ae-112">**Home Organization**</span></span>|<span data-ttu-id="a08ae-113">Escriba **FABRIKAM**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-113">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="a08ae-114">**Organización de socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="a08ae-114">**Partner Organization**</span></span>|<span data-ttu-id="a08ae-115">Escriba **CONTOSO**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-115">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="a08ae-116">**Código PIP**</span><span class="sxs-lookup"><span data-stu-id="a08ae-116">**Pip Code**</span></span>|<span data-ttu-id="a08ae-117">Escriba **0C4**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-117">Type **0C4**.</span></span>|  
    |<span data-ttu-id="a08ae-118">**Versión de PIP**</span><span class="sxs-lookup"><span data-stu-id="a08ae-118">**Pip Version**</span></span>|<span data-ttu-id="a08ae-119">Escriba **R01.02**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-119">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="a08ae-120">**Id. de instancia de PIP**</span><span class="sxs-lookup"><span data-stu-id="a08ae-120">**Pip Instance ID**</span></span>|<span data-ttu-id="a08ae-121">Escriba **0C4_Test**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-121">Type **0C4_Test**.</span></span> <span data-ttu-id="a08ae-122">**Importante:** para evitar errores de Id. de mensaje duplicado, debe asegurarse de que el **PIP** es único para cada mensaje que envíe.</span><span class="sxs-lookup"><span data-stu-id="a08ae-122">**Important:**  To avoid duplicate message ID errors, you must make sure that the **PIP** is unique for each message that you submit.</span></span> <span data-ttu-id="a08ae-123">Si ejecuta la prueba 0C4 en el futuro, tendrá que cambiar este campo.</span><span class="sxs-lookup"><span data-stu-id="a08ae-123">If you run the 0C4 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="a08ae-124">**Categoría de mensaje**</span><span class="sxs-lookup"><span data-stu-id="a08ae-124">**Message Category**</span></span>|<span data-ttu-id="a08ae-125">Escriba **Acción**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-125">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="a08ae-126">Con el Bloc de notas u otro editor de texto, abra el archivo 0c4_request.XML situado en la  *\<unidad\>*: \Program BizTalk 2009 Accelerator para la carpeta RosettaNet\SDK\LOBApplication\SampleInstances, y, a continuación, copie y pegue el contenido en el **contenido de servicio** campo LOBWebApplication.</span><span class="sxs-lookup"><span data-stu-id="a08ae-126">Using Notepad or another text editor, open the 0C4_Request.xml file in the *\<drive\>*:\Program Files\Microsoft BizTalk 2009 Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="a08ae-127">Haga clic en **Enviar** para enviar la consulta 0C4 al equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="a08ae-127">Click **Submit** to submit the 0C4 query to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="a08ae-128">Para comprobar que la comunicación es correcta en el equipo de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="a08ae-128">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="a08ae-129">En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="a08ae-129">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a08ae-130">Debería recibir un mensaje de categoría 50, que es el mensaje de respuesta del equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="a08ae-130">You should receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="a08ae-131">Un mensaje de categoría -99 indica un error.</span><span class="sxs-lookup"><span data-stu-id="a08ae-131">A category -99 message signifies an error.</span></span> <span data-ttu-id="a08ae-132">Puede utilizar el Visor de eventos para determinar cuál es el mensaje de error real.</span><span class="sxs-lookup"><span data-stu-id="a08ae-132">You can use the Event Viewer to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="a08ae-133">Para comprobar que la comunicación es correcta en el equipo de Contoso</span><span class="sxs-lookup"><span data-stu-id="a08ae-133">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="a08ae-134">Haga clic en **Inicio**, seleccione **Todos los programas**, elija **Microsoft SQL Server**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-134">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="a08ae-135">En el cuadro de diálogo **Conectarse al servidor** , en el cuadro **SQL Server** , escriba **localhost**, seleccione **Autenticación de Windows**y, después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-135">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a08ae-136">Si el Agente SQL Server no está iniciado, haga clic con el botón secundario sobre él y después haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-136">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="a08ae-137">En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="a08ae-137">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="a08ae-138">En el \<tabla\> cuadro de texto, seleccione **BTARNDATA** en la lista.</span><span class="sxs-lookup"><span data-stu-id="a08ae-138">In the \<table\> text box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="a08ae-139">En la ventana de SQL, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="a08ae-139">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="a08ae-140">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="a08ae-140">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="a08ae-141">En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="a08ae-141">In the Query window, in the Results pane, verify that you see one incoming message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a08ae-142">Debería ver un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="a08ae-142">You should see a category 10 message that represents the original request that the Fabrikam computer sent.</span></span>  
  
8.  <span data-ttu-id="a08ae-143">En la ventana de SQL, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="a08ae-143">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="a08ae-144">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="a08ae-144">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="a08ae-145">En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="a08ae-145">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a08ae-146">Debería ver un mensaje de categoría 50 que representa la respuesta de Contoso a la consulta PIP 0C4 enviada por Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="a08ae-146">You should see a category 50 message that represents the Contoso response to the PIP 0C4 query that Fabrikam sent.</span></span> <span data-ttu-id="a08ae-147">En un escenario de doble acción sincrónico, el equipo de respuesta no envía una confirmación al equipo iniciador en respuesta al mensaje de consulta inicial.</span><span class="sxs-lookup"><span data-stu-id="a08ae-147">In a double action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial query message.</span></span> <span data-ttu-id="a08ae-148">El mensaje de respuesta sirve como confirmación.</span><span class="sxs-lookup"><span data-stu-id="a08ae-148">The response message serves as the acknowledgement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08ae-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="a08ae-149">See Also</span></span>  
 <span data-ttu-id="a08ae-150">[Paso 3: Enviar una solicitud de 3A2](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md) </span><span class="sxs-lookup"><span data-stu-id="a08ae-150">[Step 3: Submitting a 3A2 Request](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md) </span></span>  
 [<span data-ttu-id="a08ae-151">Flujo de mensajes en BTARN</span><span class="sxs-lookup"><span data-stu-id="a08ae-151">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)