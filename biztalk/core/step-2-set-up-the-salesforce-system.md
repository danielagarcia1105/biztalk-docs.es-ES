---
title: 'Paso 2: Configurar el sistema Salesforce | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a4b09fb-70a7-4eec-b1e3-f05de0e84df1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65a1c741103b9c8f1e9493b7bd2aa56eef8cf18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-set-up-the-salesforce-system"></a><span data-ttu-id="15127-102">Paso 2: Configurar el sistema Salesforce</span><span class="sxs-lookup"><span data-stu-id="15127-102">Step 2: Set up the Salesforce System</span></span>
<span data-ttu-id="15127-103">En este paso, configurará Salesforce para enviar notificaciones cuando se cierre una oportunidad satisfactoriamente.</span><span class="sxs-lookup"><span data-stu-id="15127-103">In this step, you configure Salesforce to send notifications when an opportunity is successfully closed.</span></span> <span data-ttu-id="15127-104">Para poder enviar notificaciones, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="15127-104">Before you can send notifications, you need to perform the following steps:</span></span>  
  
-   <span data-ttu-id="15127-105">Crear una cuenta en Salesforce</span><span class="sxs-lookup"><span data-stu-id="15127-105">Create an account in Salesforce.</span></span> <span data-ttu-id="15127-106">Una cuenta representa un cliente para Northwind.</span><span class="sxs-lookup"><span data-stu-id="15127-106">An account represents a customer for Northwind.</span></span>  
  
-   <span data-ttu-id="15127-107">Crear una oportunidad para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="15127-107">Create an opportunity for the account.</span></span> <span data-ttu-id="15127-108">Una oportunidad representa una oportunidad de venta potencial con el cliente.</span><span class="sxs-lookup"><span data-stu-id="15127-108">An opportunity represents a prospective sales opportunity with the customer.</span></span> <span data-ttu-id="15127-109">Como parte de la oportunidad, agregará también los detalles de productos en los que el cliente está interesado.</span><span class="sxs-lookup"><span data-stu-id="15127-109">As part of the opportunity, you also add the product details that the customer is interested in.</span></span>  
  
-   <span data-ttu-id="15127-110">Crear un flujo de trabajo en Salesforce.</span><span class="sxs-lookup"><span data-stu-id="15127-110">Create a workflow in Salesforce.</span></span>  
  
-   <span data-ttu-id="15127-111">Crear una definición de aplicación conectada a Salesforce.</span><span class="sxs-lookup"><span data-stu-id="15127-111">Create a Salesforce connected application definition.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15127-112">En este tema se asume que ya tiene una cuenta de desarrollador de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="15127-112">The steps in this topic assume that you already have a Salesforce developer account.</span></span> <span data-ttu-id="15127-113">Para crear una nueva cuenta de desarrollador en Salesforce, vaya a [http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424).</span><span class="sxs-lookup"><span data-stu-id="15127-113">To create a new developer account in Salesforce, go to [http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424).</span></span>  
  
### <a name="to-create-an-account-in-salesforce"></a><span data-ttu-id="15127-114">Para crear una cuenta en Salesforce</span><span class="sxs-lookup"><span data-stu-id="15127-114">To create an Account in Salesforce</span></span>  
  
1.  <span data-ttu-id="15127-115">Inicie sesión en el portal Salesforce.com con sus credenciales de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="15127-115">Log on to the Salesforce.com portal using your developer credentials.</span></span>  
  
2.  <span data-ttu-id="15127-116">En el portal, haga clic en el **cuentas** ficha y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="15127-116">On the portal, click the **Accounts** tab, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="15127-117">En el **nueva cuenta** , proporcione valores para los distintos campos.</span><span class="sxs-lookup"><span data-stu-id="15127-117">On the **New Account** page, provide values for the various fields.</span></span> <span data-ttu-id="15127-118">Especificar un valor para **nombre de la cuenta** es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="15127-118">Specifying a value for **Account Name** is mandatory.</span></span> <span data-ttu-id="15127-119">Para este tutorial, especifique el nombre de cuenta como `Customer1`.</span><span class="sxs-lookup"><span data-stu-id="15127-119">For this tutorial, specify the account name as `Customer1`.</span></span>  
  
4.  <span data-ttu-id="15127-120">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="15127-120">Click **Save**.</span></span>  
  
### <a name="to-create-an-opportunity-for-the-customer"></a><span data-ttu-id="15127-121">Para crear una oportunidad para el cliente</span><span class="sxs-lookup"><span data-stu-id="15127-121">To create an Opportunity for the customer</span></span>  
  
1.  <span data-ttu-id="15127-122">En el portal Salesforce.com, haga clic en el **oportunidades** ficha.</span><span class="sxs-lookup"><span data-stu-id="15127-122">On the Salesforce.com portal, click the **Opportunities** tab.</span></span>  
  
2.  <span data-ttu-id="15127-123">En el **oportunidades recientes** sección, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="15127-123">In the **Recent Opportunities** section, click **New**.</span></span>  
  
3.  <span data-ttu-id="15127-124">En la página Oportunidad nueva, especifique los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="15127-124">In the New Opportunity page, specify the following values:</span></span>  
  
    1.  <span data-ttu-id="15127-125">Especifique un **nombre de la oportunidad**, por ejemplo, `Opportunity with Customer 1`.</span><span class="sxs-lookup"><span data-stu-id="15127-125">Specify an **Opportunity Name**, for example, `Opportunity with Customer 1`.</span></span>  
  
    2.  <span data-ttu-id="15127-126">Especifique el **nombre de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="15127-126">Specify the **Account Name**.</span></span> <span data-ttu-id="15127-127">Este nombre representa la cuenta con la que está asociada esta oportunidad.</span><span class="sxs-lookup"><span data-stu-id="15127-127">This represents the account with which this opportunity is associated.</span></span> <span data-ttu-id="15127-128">Para este tutorial, establezca la cuenta `Customer1`.</span><span class="sxs-lookup"><span data-stu-id="15127-128">For this tutorial, set the Account to `Customer1`.</span></span> <span data-ttu-id="15127-129">Esta cuenta se crea en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="15127-129">You created this account in the previous procedure.</span></span>  
  
    3.  <span data-ttu-id="15127-130">Especifique un **fecha de cierre**.</span><span class="sxs-lookup"><span data-stu-id="15127-130">Specify a **Close Date**.</span></span> <span data-ttu-id="15127-131">Esta es la fecha en la que debería cerrarse la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="15127-131">This represents the date by which the opportunity should be closed.</span></span>  
  
    4.  <span data-ttu-id="15127-132">Especifique un **fase**.</span><span class="sxs-lookup"><span data-stu-id="15127-132">Specify a **Stage**.</span></span> <span data-ttu-id="15127-133">Este valor denota la etapa actual para la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="15127-133">This denotes the current stage for the opportunity.</span></span> <span data-ttu-id="15127-134">Comenzar con, puede establecer la oportunidad en cualquier valor, por ejemplo, **necesita análisis**.</span><span class="sxs-lookup"><span data-stu-id="15127-134">To start with, you can set the opportunity to anything, for example, **Needs Analysis**.</span></span>  
  
         <span data-ttu-id="15127-135">![Crear una oportunidad en Salesforce](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span><span class="sxs-lookup"><span data-stu-id="15127-135">![Create an opportunity in Salesforce](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="15127-136">Asegúrese de que no establece la etapa en **Closed Won** comenzar con.</span><span class="sxs-lookup"><span data-stu-id="15127-136">Make sure you do not set the stage to **Closed Won** to start with.</span></span> <span data-ttu-id="15127-137">Para el escenario de este tutorial, cada vez que se establece la etapa **Closed Won** se envía una notificación a un extremo de retransmisión [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15127-137">For the scenario in this tutorial, every time the stage is set to **Closed Won** a notification is sent to a relay endpoint on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span> <span data-ttu-id="15127-138">No hemos configurado esa parte de la solución, por lo que no debe preparar el terreno **Closed Won**.</span><span class="sxs-lookup"><span data-stu-id="15127-138">We haven’t set up that part of the solution yet, so you should not set the stage to **Closed Won**.</span></span>  
  
    5.  <span data-ttu-id="15127-139">Especificar valores para otros campos opcionales y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="15127-139">Specify values for other optional fields and then click **Save**.</span></span>  
  
    6.  <span data-ttu-id="15127-140">En la página oportunidad para Customer1, en la **productos** sección, haga clic en **agregar producto**.</span><span class="sxs-lookup"><span data-stu-id="15127-140">On the Opportunity page for Customer1, under the **Products** section, click **Add Product**.</span></span>  
  
    7.  <span data-ttu-id="15127-141">En la lista de productos, seleccione los productos que el cliente está interesado en y, a continuación, haga clic en **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="15127-141">From the list of products, select the products that the customer is interested in, and then click **Select**.</span></span>  
  
    8.  <span data-ttu-id="15127-142">Para cada producto seleccionado, especifique una cantidad que el cliente desee y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="15127-142">For each selected product, specify a quantity that the customer wants, and then click **Save**.</span></span>  
  
         <span data-ttu-id="15127-143">![Agregar productos a una oportunidad](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="15127-143">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
## <a name="create-a-salesforce-workflow"></a><span data-ttu-id="15127-144">Crear un flujo de trabajo en Salesforce</span><span class="sxs-lookup"><span data-stu-id="15127-144">Create a Salesforce Workflow</span></span>  
 <span data-ttu-id="15127-145">En este paso, crearemos un flujo de trabajo para enviar una notificación cada vez que se cierre una oportunidad satisfactoriamente.</span><span class="sxs-lookup"><span data-stu-id="15127-145">In this step we create a workflow to send out a notification every time an opportunity is closed successfully.</span></span> <span data-ttu-id="15127-146">La notificación tiene el formato de un mensaje SOAP y se envía a un extremo de retransmisión hospedado en [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15127-146">The notification is in the form of a SOAP message and is sent to a relay endpoint hosted on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span>  
  
#### <a name="to-create-a-workflow-for-opportunities"></a><span data-ttu-id="15127-147">Para crear un flujo de trabajo para oportunidades</span><span class="sxs-lookup"><span data-stu-id="15127-147">To create a workflow for opportunities</span></span>  
  
1.  <span data-ttu-id="15127-148">En el portal de Salesforce, haga clic en el nombre de inicio de sesión en la esquina superior derecha de la página y, a continuación, haga clic en **el programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="15127-148">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2.  <span data-ttu-id="15127-149">En el panel izquierdo, bajo **el programa de instalación de la aplicación**, expanda **crear**, expanda **flujo de trabajo y aprobaciones**y, a continuación, haga clic en **reglas de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="15127-149">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15127-150">Si abre la página Reglas de flujo de trabajo por primera vez, se le mostrará información para que comprenda cómo funcionan los flujos de trabajo en Salesforce.</span><span class="sxs-lookup"><span data-stu-id="15127-150">If you are opening the Workflow Rules page for the first time, you will be presented with some information to understand how workflows work in Salesforce.</span></span> <span data-ttu-id="15127-151">Lea la información y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="15127-151">Read through the information and then click **Continue**.</span></span>  
  
3.  <span data-ttu-id="15127-152">En el **todas las reglas de flujo de trabajo** página, haga clic en **nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="15127-152">On the **All Workflow Rules** page, click **New Rule**.</span></span>  
  
4.  <span data-ttu-id="15127-153">Desde el **seleccionar un objeto de** lista, haga clic en **oportunidad**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="15127-153">From the **Select Object** list, click **Opportunity**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="15127-154">En la página siguiente, especifique estos datos:</span><span class="sxs-lookup"><span data-stu-id="15127-154">In the next page, specify the following:</span></span>  
  
    1.  <span data-ttu-id="15127-155">Establecer el **nombre de regla** como `Closed Opportunity`.</span><span class="sxs-lookup"><span data-stu-id="15127-155">Set the **Rule Name** as `Closed Opportunity`.</span></span>  
  
    2.  <span data-ttu-id="15127-156">Establecer el **criterios de evaluación** como **creado y cada vez que es modificado para cumplir los criterios**.</span><span class="sxs-lookup"><span data-stu-id="15127-156">Set the **Evaluation Criteria** as **created, and any time it’s edited to subsequently meet criteria**.</span></span>  
  
    3.  <span data-ttu-id="15127-157">Para el **criterios de la regla**, establezca ejecutar la regla cuando el **se cumplen los criterios**.</span><span class="sxs-lookup"><span data-stu-id="15127-157">For the **Rule Criteria**, set to run the rule when the **criteria are met**.</span></span>  
  
    4.  <span data-ttu-id="15127-158">Establecer **campo** a **oportunidad: fase**, **operador** a **es igual a**, y **valor** a `Closed Won`.</span><span class="sxs-lookup"><span data-stu-id="15127-158">Set **Field** to **Opportunity: Stage**, **Operator** to **equals**, and **Value** to `Closed Won`.</span></span>  
  
         <span data-ttu-id="15127-159">![Crear un flujo de trabajo de Salesforce](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span><span class="sxs-lookup"><span data-stu-id="15127-159">![Create a Salesforce workflow](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span></span>  
  
    5.  <span data-ttu-id="15127-160">Haga clic en **Guardar & siguiente**.</span><span class="sxs-lookup"><span data-stu-id="15127-160">Click **Save & Next**.</span></span>  
  
6.  <span data-ttu-id="15127-161">Defina la acción del flujo de trabajo para la regla nueva:</span><span class="sxs-lookup"><span data-stu-id="15127-161">Define the workflow action for the new rule:</span></span>  
  
    1.  <span data-ttu-id="15127-162">En el **especificar acciones de flujo de trabajo** página, haga clic en **Agregar acción de flujo de trabajo** botón y, a continuación, haga clic en **nuevo mensaje saliente**.</span><span class="sxs-lookup"><span data-stu-id="15127-162">On the **Specify Workflow Actions** page, click **Add Workflow Action** button and then click **New Outbound Message**.</span></span>  
  
    2.  <span data-ttu-id="15127-163">Establecer el **nombre** y **nombre único** campos a `NewOp1`.</span><span class="sxs-lookup"><span data-stu-id="15127-163">Set the **Name** and **Unique Name** fields to `NewOp1`.</span></span>  
  
    3.  <span data-ttu-id="15127-164">Especifique una descripción, como por ejemplo, el `Message sent when an opportunity is successfully closed`.</span><span class="sxs-lookup"><span data-stu-id="15127-164">Specify a description, such as, the `Message sent when an opportunity is successfully closed`.</span></span>  
  
    4.  <span data-ttu-id="15127-165">Especifique el **dirección URL del extremo** como `https://btssalesforce.servicebus.windows.net/notifications/opportunity`.</span><span class="sxs-lookup"><span data-stu-id="15127-165">Specify the **Endpoint URL** as `https://btssalesforce.servicebus.windows.net/notifications/opportunity`.</span></span>  
  
         <span data-ttu-id="15127-166">En este caso, **btssalesforce** es su [!INCLUDE[sb](../includes/sb-md.md)] espacio de nombres que ha creado en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="15127-166">Here, **btssalesforce** is your [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created in earlier steps.</span></span> <span data-ttu-id="15127-167">**/Notifications/opportunity/** representa la retransmisión que creamos en pasos posteriores de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="15127-167">**/notifications/opportunity/** represents the relay that we will create in later steps of this tutorial.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="15127-168">Debe especificar el espacio de nombres de [!INCLUDE[sb](../includes/sb-md.md)] que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="15127-168">You must specify the [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created earlier.</span></span>  
  
    5.  <span data-ttu-id="15127-169">Asegúrese de que el **componente protegido** casilla está desactivada y el **enviar Id. de sesión** está activada la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="15127-169">Make sure the **Protected Component** check box is clear and the **Send Session ID** check box is checked.</span></span>  
  
    6.  <span data-ttu-id="15127-170">Para **campos de oportunidad para enviar** seleccione los campos relevantes en el **campos disponibles** lista y, a continuación, haga clic en el **agregar** botón.</span><span class="sxs-lookup"><span data-stu-id="15127-170">For **Opportunity fields to send** select the relevant fields from the **Available Fields** list and then click the **Add** button.</span></span>  
  
    7.  <span data-ttu-id="15127-171">Haga clic en **guardar** y, a continuación, haga clic en **realiza**.</span><span class="sxs-lookup"><span data-stu-id="15127-171">Click **Save** and then click **Done**.</span></span>  
  
    8.  <span data-ttu-id="15127-172">En el panel izquierdo, bajo **el programa de instalación de la aplicación**, expanda **crear**, expanda **flujo de trabajo y aprobaciones**y, a continuación, haga clic en **reglas de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="15127-172">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span> <span data-ttu-id="15127-173">Compruebe que la **oportunidad cerrada** regla está en la lista.</span><span class="sxs-lookup"><span data-stu-id="15127-173">Verify that the **Closed Opportunity** rule is listed there.</span></span> <span data-ttu-id="15127-174">En el **acción** columna para la **oportunidad cerrada** de regla, haga clic en **activar** para activar la regla.</span><span class="sxs-lookup"><span data-stu-id="15127-174">Under the **Action** column for the **Closed Opportunity** rule, click **Activate** to activate the rule.</span></span>  
  
## <a name="create-a-salesforce-connected-application"></a><span data-ttu-id="15127-175">Crear una aplicación conectada a Salesforce</span><span class="sxs-lookup"><span data-stu-id="15127-175">Create a Salesforce Connected Application</span></span>  
 <span data-ttu-id="15127-176">Al crear una definición de aplicación conectada, se genera un conjunto de claves necesarias para solicitar tokens OAuth para obtener acceso y conectarse a Salesforce.</span><span class="sxs-lookup"><span data-stu-id="15127-176">Creating a connected application definition generates a set of keys required to request OAuth tokens to access to connect to Salesforce.</span></span> <span data-ttu-id="15127-177">En los últimos pasos de este tutorial, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] será la aplicación conectada que consulta a Salesforce usando la definición de aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="15127-177">In the later stages of this tutorial, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will be the connected application that queries Salesforce using the connected application definition.</span></span>  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a><span data-ttu-id="15127-178">Para crear una aplicación conectada para Salesforce</span><span class="sxs-lookup"><span data-stu-id="15127-178">To create a connected application for Salesforce</span></span>  
  
1.  <span data-ttu-id="15127-179">En el portal de Salesforce, haga clic en el nombre de inicio de sesión en la esquina superior derecha de la página y, a continuación, haga clic en **el programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="15127-179">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2.  <span data-ttu-id="15127-180">En el panel izquierdo, bajo **el programa de instalación de la aplicación**, expanda **crear**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="15127-180">In the left pane, under **App Setup**, expand **Create**, and then expand **Apps**.</span></span> <span data-ttu-id="15127-181">En el **aplicaciones** página, en la **aplicaciones conectadas** sección, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="15127-181">On the **Apps** page, under the **Connected Apps** section, click **New**.</span></span>  
  
3.  <span data-ttu-id="15127-182">En el **nueva aplicación conectada** página, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15127-182">In the **New Connection App** page, specify the following:</span></span>  
  
    1.  <span data-ttu-id="15127-183">Para **nombre de aplicación conectada**, especifique `BizTalk_Salesforce`.</span><span class="sxs-lookup"><span data-stu-id="15127-183">For **Connected App Name**, specify `BizTalk_Salesforce`.</span></span>  
  
    2.  <span data-ttu-id="15127-184">Para **nombre del desarrollador**, especifique el registro en nombre.</span><span class="sxs-lookup"><span data-stu-id="15127-184">For **Developer Name**, specify your log on name.</span></span>  
  
    3.  <span data-ttu-id="15127-185">Para **correo electrónico de contacto**, especifique su correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="15127-185">For **Contact Email**, specify your e-mail.</span></span>  
  
    4.  <span data-ttu-id="15127-186">Para **dirección URL de devolución de llamada**, especifique una dirección URL válida.</span><span class="sxs-lookup"><span data-stu-id="15127-186">For **Callback URL**, specify a valid URL.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="15127-187">Debido al modo en que nos autenticamos en Salesforce en este escenario, el valor que especifique aquí no se usa.</span><span class="sxs-lookup"><span data-stu-id="15127-187">Because of the way we authenticate with Salesforce in this scenario, the value you specify here is not used.</span></span>  
  
    5.  <span data-ttu-id="15127-188">En **ámbitos de OAuth disponibles**, seleccione **acceso completo**, **realizar solicitudes en su nombre en cualquier momento**, y **acceso y administrar datos**y, a continuación, haga clic en el **agregar** botón para moverlos a la **seleccionado ámbitos de OAuth**.</span><span class="sxs-lookup"><span data-stu-id="15127-188">Under **Available OAuth Scopes**, select **Full access**, **Perform requests on your behalf at any time**, and **Access and manage your data** and then click the **Add** button to move them into the **Selected OAuth Scopes**.</span></span>  
  
    6.  <span data-ttu-id="15127-189">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="15127-189">Click **Save**.</span></span> <span data-ttu-id="15127-190">La página que aparece contiene información sobre la **clave de consumidor** y **secreto de consumidor**.</span><span class="sxs-lookup"><span data-stu-id="15127-190">The page that appears contains information about the **Consumer Key** and **Consumer Secret**.</span></span> <span data-ttu-id="15127-191">Debe tomar nota de estos valores.</span><span class="sxs-lookup"><span data-stu-id="15127-191">You must make a note of these values.</span></span> <span data-ttu-id="15127-192">Los necesitará para conectarse a Salesforce desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15127-192">You will need these values while connecting to Salesforce from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
         <span data-ttu-id="15127-193">![Teclas de acceso de Salesforce](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span><span class="sxs-lookup"><span data-stu-id="15127-193">![Keys for Salesforce access](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span></span>  
  
4.  <span data-ttu-id="15127-194">Finalmente, genere un token de seguridad necesario para conectarse a Salesforce desde ubicaciones de red desconocidas.</span><span class="sxs-lookup"><span data-stu-id="15127-194">Finally, generate a security token required for connecting to Salesforce from unknown network locations.</span></span>  
  
    1.  <span data-ttu-id="15127-195">En el panel izquierdo del portal de Salesforce, en **configuración Personal**, expanda **información Personal**y, a continuación, haga clic en **restablecer mi Token de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="15127-195">On the left pane of the Salesforce portal, under **Personal Setup**, expand **Personal Information**, and then click **Reset My Security Token**.</span></span>  
  
    2.  <span data-ttu-id="15127-196">Lea la advertencia y, a continuación, haga clic en **restablecer Token de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="15127-196">Read the warning and then click **Reset Security Token**.</span></span>  
  
    3.  <span data-ttu-id="15127-197">Debería recibir el token de seguridad en la dirección de correo electrónico que especificó cuando creó su cuenta de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="15127-197">You should receive the security token at the e-mail address you specified while creating your Salesforce account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15127-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="15127-198">See Also</span></span>  
 [<span data-ttu-id="15127-199">Tutorial: 6: Integración de BizTalk Server 2013 con Salesforce</span><span class="sxs-lookup"><span data-stu-id="15127-199">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)