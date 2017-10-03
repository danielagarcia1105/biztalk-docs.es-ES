---
title: 'Paso 4: Enviar una solicitud de 3A4 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 2d812cbc-51bc-48d5-b0b2-3698d33664ec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2436d33033163b32c4ead0fdab807b7db0b0158f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-submitting-a-3a4-request"></a><span data-ttu-id="6755d-102">Paso 4: Enviar una solicitud de 3A4</span><span class="sxs-lookup"><span data-stu-id="6755d-102">Step 4: Submitting a 3A4 Request</span></span>
<span data-ttu-id="6755d-103">En este paso, se preparará y enviará una solicitud con el proceso de interfaz de socio (PIP) para un 3A4 - pedido de compra de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6755d-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A4 - Request Purchase Order.</span></span> <span data-ttu-id="6755d-104">Este PIP permite a una organización de comprador enviar una solicitud de pedido de compra a un proveedor.</span><span class="sxs-lookup"><span data-stu-id="6755d-104">This PIP enables a buyer organization to submit a purchase order request to a supplier.</span></span> <span data-ttu-id="6755d-105">Por lo general, se solicita la 3A4 - pedido de compra de solicitud después de ejecutar una consulta de la disponibilidad de producto mediante el 3A2 - solicitud precio y disponibilidad PIP.</span><span class="sxs-lookup"><span data-stu-id="6755d-105">Generally, you request the 3A4 - Request Purchase Order after running a product availability query using the 3A2 - Request Price and Availability PIP.</span></span> <span data-ttu-id="6755d-106">El PIP 3A4 es una PIP asincrónica que envía confirmaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="6755d-106">The 3A4 PIP is an asynchronous PIP that sends receipt acknowledgements.</span></span>  
  
 <span data-ttu-id="6755d-107">![&#60; No hay ningún cambio &#62; ] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span><span class="sxs-lookup"><span data-stu-id="6755d-107">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span></span>  
  
### <a name="to-submit-a-3a4---request-purchase-order"></a><span data-ttu-id="6755d-108">Para enviar un 3A4 - solicitud de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="6755d-108">To submit a 3A4 - Request Purchase Order</span></span>  
  
1.  <span data-ttu-id="6755d-109">En el equipo de Fabrikam, en Internet Explorer, busque y abra http://localhost/LOBWebApplication/default.aspx.</span><span class="sxs-lookup"><span data-stu-id="6755d-109">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="6755d-110">En la página **Enviar mensaje** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6755d-110">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="6755d-111">**Use esto**</span><span class="sxs-lookup"><span data-stu-id="6755d-111">**Use this**</span></span>|<span data-ttu-id="6755d-112">**Para ello**</span><span class="sxs-lookup"><span data-stu-id="6755d-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="6755d-113">**Organización principal**</span><span class="sxs-lookup"><span data-stu-id="6755d-113">**Home Organization**</span></span>|<span data-ttu-id="6755d-114">Escriba **FABRIKAM**.</span><span class="sxs-lookup"><span data-stu-id="6755d-114">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="6755d-115">**Organización de socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="6755d-115">**Partner Organization**</span></span>|<span data-ttu-id="6755d-116">Tipo de **Contoso**.</span><span class="sxs-lookup"><span data-stu-id="6755d-116">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="6755d-117">**Código PIP**</span><span class="sxs-lookup"><span data-stu-id="6755d-117">**Pip Code**</span></span>|<span data-ttu-id="6755d-118">Tipo de **3A4**.</span><span class="sxs-lookup"><span data-stu-id="6755d-118">Type **3A4**.</span></span>|  
    |<span data-ttu-id="6755d-119">**Versión de PIP**</span><span class="sxs-lookup"><span data-stu-id="6755d-119">**Pip Version**</span></span>|<span data-ttu-id="6755d-120">Tipo de **V02.02.00**.</span><span class="sxs-lookup"><span data-stu-id="6755d-120">Type **V02.02.00**.</span></span>|  
    |<span data-ttu-id="6755d-121">**Id. de instancia de PIP**</span><span class="sxs-lookup"><span data-stu-id="6755d-121">**Pip Instance ID**</span></span>|<span data-ttu-id="6755d-122">Tipo de **3A4_Test**.</span><span class="sxs-lookup"><span data-stu-id="6755d-122">Type **3A4_Test**.</span></span> <span data-ttu-id="6755d-123">**Importante:** para evitar errores de Id. de mensaje duplicado, debe asegurarse de que el **Id. de instancia de Pip** es único para cada mensaje que envíe.</span><span class="sxs-lookup"><span data-stu-id="6755d-123">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip Instance ID** is unique for each message that you submit.</span></span> <span data-ttu-id="6755d-124">Si ejecuta la prueba de 3A4 en el futuro, tendrá que cambiar este campo.</span><span class="sxs-lookup"><span data-stu-id="6755d-124">If you run the 3A4 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="6755d-125">**Categoría de mensaje**</span><span class="sxs-lookup"><span data-stu-id="6755d-125">**Message Category**</span></span>|<span data-ttu-id="6755d-126">Escriba **Acción**.</span><span class="sxs-lookup"><span data-stu-id="6755d-126">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="6755d-127">Con el Bloc de notas u otro editor de texto, abra el archivo 3A4_Request.xml en el \< *unidad*>: \Program BizTalk \<versión > Accelerator for RosettaNet\SDK\LOBApplication\ Carpeta SampleInstances y, a continuación, copie y pegue el contenido en el **contenido de servicio** campo LOBWebApplication.</span><span class="sxs-lookup"><span data-stu-id="6755d-127">Using Notepad or another text editor, open the 3A4_Request.xml file in the \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="6755d-128">Haga clic en **enviar** para enviar la solicitud 3A4 en el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="6755d-128">Click **Submit** to submit the 3A4 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="6755d-129">Para comprobar que la comunicación es correcta en el equipo de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="6755d-129">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="6755d-130">En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="6755d-130">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6755d-131">En primer lugar debe recibir un mensaje de 25 de categoría lo que significa una confirmación de recepción desde el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="6755d-131">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="6755d-132">A continuación, debería recibir un mensaje de categoría 50 que es el mensaje de respuesta desde el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="6755d-132">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="6755d-133">Un mensaje de categoría -99 indica un error.</span><span class="sxs-lookup"><span data-stu-id="6755d-133">A category -99 message signifies an error.</span></span> <span data-ttu-id="6755d-134">Puede usar **Visor de eventos** para determinar el mensaje de error real.</span><span class="sxs-lookup"><span data-stu-id="6755d-134">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="6755d-135">Para comprobar que la comunicación es correcta en el equipo de Contoso</span><span class="sxs-lookup"><span data-stu-id="6755d-135">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="6755d-136">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="6755d-136">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="6755d-137">En el cuadro de diálogo **Conectarse al servidor** , en el cuadro **SQL Server** , escriba **localhost**, seleccione **Autenticación de Windows**y, después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="6755d-137">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="6755d-138">En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6755d-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="6755d-139">En el \<tabla > cuadro de diálogo de texto, seleccione **BTARNDATA** en la lista.</span><span class="sxs-lookup"><span data-stu-id="6755d-139">In the \<table> text dialog box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="6755d-140">En la ventana de SQL, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="6755d-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="6755d-141">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="6755d-141">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="6755d-142">En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="6755d-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6755d-143">En primer lugar debe recibir un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="6755d-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="6755d-144">A continuación, debería recibir un mensaje de 25 de categoría lo que significa el mensaje de confirmación de acknowledegment.</span><span class="sxs-lookup"><span data-stu-id="6755d-144">You should then receive a category 25 message signifying the receipt acknowledegment message.</span></span>  
  
8.  <span data-ttu-id="6755d-145">En la ventana de SQL, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="6755d-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="6755d-146">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="6755d-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="6755d-147">En la ventana de consulta, en la **resultados** panel, compruebe que ve un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="6755d-147">In the Query window, in the **Results** pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6755d-148">Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="6755d-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="6755d-149">También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="6755d-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6755d-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="6755d-150">See Also</span></span>  
 <span data-ttu-id="6755d-151">[Tutorial de doble acción](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="6755d-151">[Double Action Tutorial](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span></span>  
 [<span data-ttu-id="6755d-152">Flujo de mensajes de BTARN</span><span class="sxs-lookup"><span data-stu-id="6755d-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)