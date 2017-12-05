---
title: Crear un precio y disponibilidad de solicitud con el ejemplo Fabrikam | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: private process tutorial, creating requests
ms.assetid: 6e4f4589-8f01-4b9e-93ee-c9371f32e04a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0619dc77496fd1547505221ff2f437bf486fb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-price-and-availability-request-with-the-fabrikam-sample"></a><span data-ttu-id="52980-102">Crear un precio y una solicitud de disponibilidad con el ejemplo de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="52980-102">Creating a Price and Availability Request with the Fabrikam Sample</span></span>
<span data-ttu-id="52980-103">En este paso, creará una solicitud de precio y disponibilidad 3A2 mediante la herramienta de LOBWebApplication.</span><span class="sxs-lookup"><span data-stu-id="52980-103">In this step, you create a 3A2 Price and Availability request using the LOBWebApplication tool.</span></span>  
  
### <a name="to-submit-a-3a2-price-and-availability-request-to-contoso"></a><span data-ttu-id="52980-104">Para enviar una solicitud de precio y disponibilidad 3A2 a Contoso</span><span class="sxs-lookup"><span data-stu-id="52980-104">To submit a 3A2 Price and Availability request to Contoso</span></span>  
  
1.  <span data-ttu-id="52980-105">En el Explorador de Internet, vaya a http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx.</span><span class="sxs-lookup"><span data-stu-id="52980-105">In Internet Explorer, move to http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="52980-106">En el **LOBWebApplication** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52980-106">On the **LOBWebApplication** page, do the following:</span></span>  
  
    |<span data-ttu-id="52980-107">Use</span><span class="sxs-lookup"><span data-stu-id="52980-107">Use this</span></span>|<span data-ttu-id="52980-108">Para</span><span class="sxs-lookup"><span data-stu-id="52980-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="52980-109">**Organización principal**</span><span class="sxs-lookup"><span data-stu-id="52980-109">**Home Organization**</span></span>|<span data-ttu-id="52980-110">Escriba **FABRIKAM**.</span><span class="sxs-lookup"><span data-stu-id="52980-110">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="52980-111">**Organización de socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="52980-111">**Partner Organization**</span></span>|<span data-ttu-id="52980-112">Escriba **CONTOSO**.</span><span class="sxs-lookup"><span data-stu-id="52980-112">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="52980-113">**Código PIP**</span><span class="sxs-lookup"><span data-stu-id="52980-113">**PIP Code**</span></span>|<span data-ttu-id="52980-114">Tipo de **3A2**.</span><span class="sxs-lookup"><span data-stu-id="52980-114">Type **3A2**.</span></span>|  
    |<span data-ttu-id="52980-115">**Versión PIP**</span><span class="sxs-lookup"><span data-stu-id="52980-115">**PIP Version**</span></span>|<span data-ttu-id="52980-116">Tipo de **R02.00.00A**.</span><span class="sxs-lookup"><span data-stu-id="52980-116">Type **R02.00.00A**.</span></span>|  
    |<span data-ttu-id="52980-117">**Categoría de mensaje**</span><span class="sxs-lookup"><span data-stu-id="52980-117">**Message Category**</span></span>|<span data-ttu-id="52980-118">Escriba **Acción**.</span><span class="sxs-lookup"><span data-stu-id="52980-118">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="52980-119">Con el Bloc de notas u otro editor de texto, abra el **3A2_Request.xml** archivo en C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\LOBApplication\SampleInstancesfolder Copie y pegue el texto en el **contenido de servicio** campo en la herramienta de LOBWebApplication.</span><span class="sxs-lookup"><span data-stu-id="52980-119">Using Notepad or another text editor, open the **3A2_Request.xml** file in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstancesfolder and copy and paste the text into the **Service Content** field in the LOBWebApplication tool.</span></span>  
  
4.  <span data-ttu-id="52980-120">Haga clic en **enviar** para enviar la solicitud de 3A2 a Contoso.</span><span class="sxs-lookup"><span data-stu-id="52980-120">Click **Submit** to submit the 3A2 request to Contoso.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="52980-121">Para comprobar que la comunicación es correcta en el equipo de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="52980-121">To verify successful communication on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="52980-122">En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="52980-122">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52980-123">En primer lugar debe recibir un mensaje de 25 de categoría lo que significa una confirmación de recepción desde el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="52980-123">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="52980-124">A continuación, debería recibir un mensaje de categoría 50 que es el mensaje de respuesta desde el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="52980-124">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="52980-125">Un mensaje de categoría -99 indica un error.</span><span class="sxs-lookup"><span data-stu-id="52980-125">A category -99 message signifies an error.</span></span> <span data-ttu-id="52980-126">Puede usar **Visor de eventos** para determinar el mensaje de error real.</span><span class="sxs-lookup"><span data-stu-id="52980-126">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
2.  <span data-ttu-id="52980-127">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="52980-127">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
3.  <span data-ttu-id="52980-128">En el cuadro de diálogo servidor, conectar con en el **SQL Server** , escriba **localhost**, seleccione **autenticación de Windows**y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="52980-128">In the Connect to Server dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="52980-129">En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="52980-129">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="52980-130">En el  **\<tabla\> texto** cuadro de diálogo, seleccione **BTARNDATA** en la lista.</span><span class="sxs-lookup"><span data-stu-id="52980-130">In the **\<table\> text** dialog box, select **BTARNDATA** from the list.</span></span>  
  
6.  <span data-ttu-id="52980-131">En el **SQL** ventana, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="52980-131">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
7.  <span data-ttu-id="52980-132">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="52980-132">Click **Execute** to run the SQL statement.</span></span>  
  
8.  <span data-ttu-id="52980-133">En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="52980-133">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52980-134">Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="52980-134">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="52980-135">También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="52980-135">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span> <span data-ttu-id="52980-136">También puede usar el campo ServiceContent para comprobar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="52980-136">You can also use the ServiceContent field to verify the response.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="52980-137">Para comprobar que la comunicación es correcta en el equipo de Contoso</span><span class="sxs-lookup"><span data-stu-id="52980-137">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="52980-138">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="52980-138">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="52980-139">En el cuadro de diálogo servidor, conectar con en el **SQL Server** , escriba **localhost**, seleccione **autenticación de Windows**y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="52980-139">In the Connect to Server dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="52980-140">En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="52980-140">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="52980-141">En el  **\<tabla\> texto** cuadro de diálogo, seleccione **BTARNDATA** en la lista.</span><span class="sxs-lookup"><span data-stu-id="52980-141">In the **\<table\> text** dialog box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="52980-142">En el **SQL** ventana, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="52980-142">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="52980-143">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="52980-143">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="52980-144">En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="52980-144">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52980-145">En primer lugar debe recibir un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="52980-145">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="52980-146">A continuación, debería recibir un mensaje de 25 de categoría lo que significa el mensaje de confirmación de recepción.</span><span class="sxs-lookup"><span data-stu-id="52980-146">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="52980-147">En el **SQL** ventana, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="52980-147">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="52980-148">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="52980-148">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="52980-149">En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="52980-149">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52980-150">Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="52980-150">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="52980-151">También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="52980-151">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52980-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="52980-152">See Also</span></span>  
 [<span data-ttu-id="52980-153">Tutorial de procesos privados</span><span class="sxs-lookup"><span data-stu-id="52980-153">Private Process Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-process-tutorial.md)