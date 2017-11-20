---
title: 'Paso 1: Enviar solicitud un 0c 2 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 698c4a43-20b9-46b7-ab66-1dfa24232024
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 089ad320f9363e1a3284af863512c89bcb67167d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-submitting-a-0c2-request"></a><span data-ttu-id="4af47-102">Paso 1: Enviar un 0c solicitar 2</span><span class="sxs-lookup"><span data-stu-id="4af47-102">Step 1: Submitting a 0C2 Request</span></span>
<span data-ttu-id="4af47-103">En este paso, se preparará y enviará una solicitud con el proceso de interfaz de socio (PIP) para un 0c 2 - solicitud asincrónica de prueba.</span><span class="sxs-lookup"><span data-stu-id="4af47-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for an 0C2 - Asynchronous Test Request.</span></span> <span data-ttu-id="4af47-104">Este PIP garantiza que un canal de comunicación asincrónica funciona correctamente entre dos organizaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="4af47-104">This PIP ensures that an asynchronous communication channel is working correctly between two different organizations.</span></span> <span data-ttu-id="4af47-105">Este PIP sigue el mismo patrón que otros PIP de doble acción asincrónica, como el 3A4 - solicitud PIP de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="4af47-105">This PIP follows the same pattern as other asynchronous double action PIPs, such as the 3A4 - Request Purchase Order PIP.</span></span>  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a><span data-ttu-id="4af47-106">Para enviar un 0c 2 - solicitud asincrónica de prueba</span><span class="sxs-lookup"><span data-stu-id="4af47-106">To submit a 0C2 - Asynchronous Test Request</span></span>  
  
1.  <span data-ttu-id="4af47-107">En el equipo de Fabrikam, en Internet Explorer, busque y abra http://localhost/LOBWebApplication/default.aspx.</span><span class="sxs-lookup"><span data-stu-id="4af47-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="4af47-108">En la página **Enviar mensaje** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4af47-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="4af47-109">Use</span><span class="sxs-lookup"><span data-stu-id="4af47-109">Use this</span></span>|<span data-ttu-id="4af47-110">Para</span><span class="sxs-lookup"><span data-stu-id="4af47-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4af47-111">**Organización principal**</span><span class="sxs-lookup"><span data-stu-id="4af47-111">**Home Organization**</span></span>|<span data-ttu-id="4af47-112">Escriba **FABRIKAM**.</span><span class="sxs-lookup"><span data-stu-id="4af47-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="4af47-113">**Organización de socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="4af47-113">**Partner Organization**</span></span>|<span data-ttu-id="4af47-114">Escriba **CONTOSO**.</span><span class="sxs-lookup"><span data-stu-id="4af47-114">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="4af47-115">**Código PIP**</span><span class="sxs-lookup"><span data-stu-id="4af47-115">**Pip Code**</span></span>|<span data-ttu-id="4af47-116">Tipo de **0c2**.</span><span class="sxs-lookup"><span data-stu-id="4af47-116">Type **0C2**.</span></span>|  
    |<span data-ttu-id="4af47-117">**Versión de PIP**</span><span class="sxs-lookup"><span data-stu-id="4af47-117">**Pip Version**</span></span>|<span data-ttu-id="4af47-118">Escriba **R01.02**.</span><span class="sxs-lookup"><span data-stu-id="4af47-118">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="4af47-119">**Id. de instancia de PIP**</span><span class="sxs-lookup"><span data-stu-id="4af47-119">**Pip Instance ID**</span></span>|<span data-ttu-id="4af47-120">Tipo de **0C2_Test**.</span><span class="sxs-lookup"><span data-stu-id="4af47-120">Type **0C2_Test**.</span></span> <span data-ttu-id="4af47-121">**Importante:** debe asegurarse de que el **PIP** es único para cada mensaje que se envía para evitar errores de Id. de mensaje duplicado.</span><span class="sxs-lookup"><span data-stu-id="4af47-121">**Important:**  You must make sure that the **PIP** is unique for each message that you submit to avoid duplicate message ID errors.</span></span> <span data-ttu-id="4af47-122">Si ejecuta el 0 C 2 probar en el futuro, tendrá que cambiar este campo.</span><span class="sxs-lookup"><span data-stu-id="4af47-122">If you run the 0C2 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="4af47-123">**Categoría de mensaje**</span><span class="sxs-lookup"><span data-stu-id="4af47-123">**Message Category**</span></span>|<span data-ttu-id="4af47-124">Escriba **Acción**.</span><span class="sxs-lookup"><span data-stu-id="4af47-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="4af47-125">Con el Bloc de notas u otro editor de texto, abra el archivo 0C2_Request.xml en el \< *unidad*>: \Program BizTalk \<versión > Accelerator for RosettaNet\SDK\LOBApplication\ Carpeta SampleInstances y, a continuación, copie y pegue el contenido en el **contenido de servicio** campo LOBWebApplication.</span><span class="sxs-lookup"><span data-stu-id="4af47-125">Using Notepad or another text editor, open the 0C2_Request.xml file in the \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4af47-126">Para eliminar el texto existente en el campo de contenido de servicio de la forma de enviar el mensaje, coloque el cursor al principio del texto, mantenga presionada la **MAYÚS** y **Ctrl** botones, haga clic en **final** y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4af47-126">To delete the existing text in the Service Content field of the Submit Message form, place the cursor at the beginning of the text, press and hold the **Shift** and **Ctrl** buttons, click **End**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="4af47-127">Haga clic en **enviar** para enviar el 0 C 2 solicite para el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="4af47-127">Click **Submit** to submit the 0C2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="4af47-128">Para comprobar que la comunicación es correcta en el equipo de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4af47-128">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="4af47-129">En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="4af47-129">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4af47-130">En primer lugar debe recibir un mensaje de 25 de categoría lo que significa una confirmación de recepción desde el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="4af47-130">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="4af47-131">A continuación, debería recibir un mensaje de categoría 50 que es el mensaje de respuesta desde el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="4af47-131">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="4af47-132">Un mensaje de categoría -99 indica un error.</span><span class="sxs-lookup"><span data-stu-id="4af47-132">A category -99 message signifies an error.</span></span> <span data-ttu-id="4af47-133">Puede usar **Visor de eventos** para determinar el mensaje de error real.</span><span class="sxs-lookup"><span data-stu-id="4af47-133">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="4af47-134">Para comprobar que la comunicación es correcta en el equipo de Contoso</span><span class="sxs-lookup"><span data-stu-id="4af47-134">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="4af47-135">Haga clic en **Inicio**, seleccione **Todos los programas**, elija **Microsoft SQL Server**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="4af47-135">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="4af47-136">En el cuadro de diálogo **Conectarse al servidor** , en el cuadro **SQL Server** , escriba **localhost**, seleccione **Autenticación de Windows**y, después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="4af47-136">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4af47-137">Si el Agente SQL Server no está iniciado, haga clic con el botón secundario sobre él y después haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="4af47-137">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="4af47-138">En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4af47-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="4af47-139">En el \<tabla > cuadro de diálogo de texto, seleccione **BTARNDATA** en la lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4af47-139">In the \<table> text dialog box, select **BTARNDATA** from the list, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="4af47-140">En la ventana de SQL, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="4af47-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="4af47-141">En el **consulta** menú, haga clic en **Execute** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="4af47-141">On the **Query** menu, click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="4af47-142">En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="4af47-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4af47-143">En primer lugar debe recibir un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="4af47-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="4af47-144">A continuación, debería recibir un mensaje de 25 de categoría lo que significa el mensaje de confirmación de recepción.</span><span class="sxs-lookup"><span data-stu-id="4af47-144">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="4af47-145">En la ventana de SQL, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="4af47-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="4af47-146">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="4af47-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="4af47-147">En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="4af47-147">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4af47-148">Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="4af47-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="4af47-149">También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="4af47-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af47-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="4af47-150">See Also</span></span>  
 <span data-ttu-id="4af47-151">[Paso 2: Enviar un 0c consultar 4](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span><span class="sxs-lookup"><span data-stu-id="4af47-151">[Step 2: Submitting a 0C4 Query](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span></span>  
 [<span data-ttu-id="4af47-152">Flujo de mensajes de BTARN</span><span class="sxs-lookup"><span data-stu-id="4af47-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)