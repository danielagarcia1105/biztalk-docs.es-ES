---
title: 'Paso 3: Enviar una solicitud de 3A2 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 09f22be8-6d7d-48bf-862b-73248bae0506
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 312e5980636d211f1e023331826e016eb141eb4b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-submitting-a-3a2-request"></a><span data-ttu-id="e2e2d-102">Paso 3: Enviar una solicitud de 3A2</span><span class="sxs-lookup"><span data-stu-id="e2e2d-102">Step 3: Submitting a 3A2 Request</span></span>
<span data-ttu-id="e2e2d-103">En este paso, se preparará y enviará una solicitud con el proceso de interfaz de socio (PIP) para un 3A2 - solicitud precio y disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A2 - Request Price and Availability.</span></span> <span data-ttu-id="e2e2d-104">Este PIP permite a una organización de comprador obtener información sobre un determinado producto, como el precio y el número de unidades disponibles.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-104">This PIP enables a buyer organization to obtain information about a certain product, such as price and number of available units.</span></span> <span data-ttu-id="e2e2d-105">El comprador, a continuación, puede procesar esta información a través de las reglas de negocios para determinar si se debe adquirir el producto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-105">The buyer can then process that information through business rules to determine whether to purchase the product from the supplier.</span></span>  
  
### <a name="to-submit-a-3a2---request-price-and-availability"></a><span data-ttu-id="e2e2d-106">Para enviar un 3A2 - solicitud de precio y disponibilidad</span><span class="sxs-lookup"><span data-stu-id="e2e2d-106">To submit a 3A2 - Request Price and Availability</span></span>  
  
1.  <span data-ttu-id="e2e2d-107">En el equipo de Fabrikam, en Internet Explorer, busque y abra http://localhost/LOBWebApplication/default.aspx.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="e2e2d-108">En la página **Enviar mensaje** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2e2d-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="e2e2d-109">Use</span><span class="sxs-lookup"><span data-stu-id="e2e2d-109">Use this</span></span>|<span data-ttu-id="e2e2d-110">Para</span><span class="sxs-lookup"><span data-stu-id="e2e2d-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e2e2d-111">**Organización principal**</span><span class="sxs-lookup"><span data-stu-id="e2e2d-111">**Home Organization**</span></span>|<span data-ttu-id="e2e2d-112">Escriba **FABRIKAM**.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="e2e2d-113">**Organización de socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="e2e2d-113">**Partner Organization**</span></span>|<span data-ttu-id="e2e2d-114">Tipo de **Contoso**.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-114">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="e2e2d-115">**Código PIP**</span><span class="sxs-lookup"><span data-stu-id="e2e2d-115">**Pip Code**</span></span>|<span data-ttu-id="e2e2d-116">Tipo de **3A2**.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-116">Type **3A2**.</span></span> <span data-ttu-id="e2e2d-117">**Importante:** para evitar errores de Id. de mensaje duplicado, debe asegurarse de que el **Pip** es único para cada mensaje que envíe.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-117">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip** is unique for each message that you submit.</span></span> <span data-ttu-id="e2e2d-118">Si ejecuta la prueba de 3A2 en el futuro, tendrá que cambiar este campo.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-118">If you run the 3A2 test in the future, you have to change this field.</span></span>|  
    |<span data-ttu-id="e2e2d-119">**Versión de PIP**</span><span class="sxs-lookup"><span data-stu-id="e2e2d-119">**Pip Version**</span></span>|<span data-ttu-id="e2e2d-120">Tipo de **R02.00.00A**.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-120">Type **R02.00.00A**.</span></span>|  
    |<span data-ttu-id="e2e2d-121">**Id. de instancia de PIP**</span><span class="sxs-lookup"><span data-stu-id="e2e2d-121">**Pip Instance ID**</span></span>|<span data-ttu-id="e2e2d-122">Tipo de **3A2_Test**.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-122">Type **3A2_Test**.</span></span>|  
    |<span data-ttu-id="e2e2d-123">**Categoría de mensaje**</span><span class="sxs-lookup"><span data-stu-id="e2e2d-123">**Message Category**</span></span>|<span data-ttu-id="e2e2d-124">Escriba **Acción**.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="e2e2d-125">Con el Bloc de notas u otro editor de texto, abra el 3A2_Request.xml de archivo en el  *\<unidad\>*: \ Programa de programa\Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances carpeta y, a continuación, copie y pegue el contenido en el **contenido de servicio** campo LOBWebApplication.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-125">Using Notepad or another text editor, open the file 3A2_Request.xml in the *\<drive\>*:\ Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="e2e2d-126">Haga clic en **enviar** para enviar la solicitud de 3A2 al equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-126">Click **Submit** to submit the 3A2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="e2e2d-127">Para comprobar que la comunicación es correcta en el equipo de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="e2e2d-127">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="e2e2d-128">En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-128">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2e2d-129">En primer lugar debe recibir un mensaje de 25 de categoría lo que significa una confirmación de recepción desde el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-129">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="e2e2d-130">A continuación, debería recibir un mensaje de categoría 50 que es el mensaje de respuesta desde el equipo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-130">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="e2e2d-131">Un mensaje de categoría -99 indica un error.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-131">A category -99 message signifies an error.</span></span> <span data-ttu-id="e2e2d-132">Puede usar **Visor de eventos** para determinar el mensaje de error real.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-132">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="e2e2d-133">Para comprobar que la comunicación es correcta en el equipo de Contoso</span><span class="sxs-lookup"><span data-stu-id="e2e2d-133">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="e2e2d-134">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-134">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="e2e2d-135">En el cuadro de diálogo **Conectarse al servidor** , en el cuadro **SQL Server** , escriba **localhost**, seleccione **Autenticación de Windows**y, después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-135">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="e2e2d-136">En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-136">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="e2e2d-137">En el \<tabla\> cuadro de texto, seleccione **BTARNDATA** en la lista.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-137">In the \<table\> text box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="e2e2d-138">En la ventana de SQL, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="e2e2d-138">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="e2e2d-139">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-139">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="e2e2d-140">En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-140">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2e2d-141">En primer lugar debe recibir un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-141">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="e2e2d-142">A continuación, debería recibir un mensaje de 25 de categoría lo que significa el mensaje de confirmación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-142">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="e2e2d-143">En la ventana de SQL, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="e2e2d-143">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="e2e2d-144">Haga clic en **Ejecutar** para ejecutar la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-144">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="e2e2d-145">En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-145">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2e2d-146">Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-146">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="e2e2d-147">También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="e2e2d-147">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e2d-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2e2d-148">See Also</span></span>  
 <span data-ttu-id="e2e2d-149">[Paso 4: Enviar una solicitud de 3A4](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span><span class="sxs-lookup"><span data-stu-id="e2e2d-149">[Step 4: Submitting a 3A4 Request](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span></span>  
 [<span data-ttu-id="e2e2d-150">Flujo de mensajes en BTARN</span><span class="sxs-lookup"><span data-stu-id="e2e2d-150">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)