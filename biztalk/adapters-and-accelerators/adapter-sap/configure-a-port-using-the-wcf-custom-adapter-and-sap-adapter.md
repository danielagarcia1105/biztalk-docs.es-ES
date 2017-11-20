---
title: Configurar un puerto mediante el adaptador WCF-custom y el adaptador SAP en BizTalk | Documentos de Microsoft
description: "Crear un puerto personalizado de WCF para enviar o recibir mensajes de SAP mediante el adaptador de mySAP en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3962456-e9ac-4575-8266-b35e892dd428
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66770264e2f76a589080cf86476448c2716b8897
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sap-adapter"></a><span data-ttu-id="4a40f-103">Configurar un puerto mediante el adaptador de WCF-custom y el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="4a40f-103">Configure a port using the WCF-custom adapter and SAP adapter</span></span>
<span data-ttu-id="4a40f-104">Este tema proporciona instrucciones sobre cómo configurar el envío de WCF-Custom y puertos de recepción para realizar operaciones entrantes y salientes en el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a40f-104">This topic provides instructions on how to configure WCF-Custom send and receive ports to perform outbound and inbound operations on SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4a40f-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4a40f-105">Prerequisites</span></span>  
<span data-ttu-id="4a40f-106">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4a40f-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="4a40f-107">Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos de usuario mínimos de seguridad](../../core/minimum-security-user-rights.md).</span><span class="sxs-lookup"><span data-stu-id="4a40f-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security User Rights](../../core/minimum-security-user-rights.md).</span></span> 
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a><span data-ttu-id="4a40f-108">Implementar los adaptadores para enviar mensajes a SAP</span><span class="sxs-lookup"><span data-stu-id="4a40f-108">Deploy adapters to send messages to SAP</span></span>  
<span data-ttu-id="4a40f-109">Complete los pasos siguientes para configurar un WCF-Custom puerto de envío para enviar mensajes al sistema SAP mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="4a40f-109">Complete the following steps to configure a WCF-Custom send port for sending messages to SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="4a40f-110">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="4a40f-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="4a40f-111">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="4a40f-112">Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a40f-112">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="4a40f-113">Haga clic en **puertos de envío**, seleccione **nuevo**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre el servidor BizTalk Server y el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a40f-113">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
5.  <span data-ttu-id="4a40f-114">En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="4a40f-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="4a40f-115">Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="4a40f-116">En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a40f-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="4a40f-117">Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a40f-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the SAP system.</span></span> <span data-ttu-id="4a40f-118">Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="4a40f-118">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="4a40f-119">En el **General** ficha la **acción** texto, escriba la acción para la operación.</span><span class="sxs-lookup"><span data-stu-id="4a40f-119">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="4a40f-120">Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) para obtener una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="4a40f-120">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) for a list of actions for each operation.</span></span> <span data-ttu-id="4a40f-121">Por ejemplo, la acción que se invoca el RFC_CUSTOMER_GET sería:</span><span class="sxs-lookup"><span data-stu-id="4a40f-121">For example, the action to invoke the RFC_CUSTOMER_GET would be:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
        ```  
  
    3.  <span data-ttu-id="4a40f-122">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-122">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="4a40f-123">Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a40f-123">You can specify the different binding properties exposed by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="4a40f-124">Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4a40f-124">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="4a40f-125">Haga clic en el **credenciales** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4a40f-125">Click the **Credentials** tab and do one of the following:</span></span>  
  
        -   <span data-ttu-id="4a40f-126">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a40f-126">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
        -   <span data-ttu-id="4a40f-127">Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="4a40f-127">Select the **Use Single Sign-On** option, and specify an affiliate SSO application.</span></span>  
  
             <span data-ttu-id="4a40f-128">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="4a40f-128">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>
  
             <span data-ttu-id="4a40f-129">Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-129">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="4a40f-130">Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-130">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="4a40f-131">Si ha elegido el puerto de envío unidireccional estático en el paso 4, especifique una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="4a40f-131">If you chose Static One-Way Send Port in step 4, specify a send pipeline.</span></span> <span data-ttu-id="4a40f-132">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4a40f-132">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="4a40f-133">Si ha elegido **puerto de petición-respuesta estático** en el paso 4, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="4a40f-133">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="4a40f-134">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4a40f-134">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="4a40f-135">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4a40f-135">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="4a40f-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-136">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a><span data-ttu-id="4a40f-137">Implementar los adaptadores para recibir mensajes de SAP</span><span class="sxs-lookup"><span data-stu-id="4a40f-137">Deploy adapters to receive messages from SAP</span></span>
<span data-ttu-id="4a40f-138">Complete los pasos siguientes para configurar un WCF-Custom puerto de recepción para recibir mensajes de sistema SAP mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="4a40f-138">Complete the following steps to configure a WCF-Custom receive port for receiving messages from SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="4a40f-139">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="4a40f-139">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="4a40f-140">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-140">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="4a40f-141">Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a40f-141">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="4a40f-142">Haga clic en **puertos de recepción**, seleccione **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta** en función de la modo de comunicación entre el servidor BizTalk Server y el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a40f-142">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port** depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
5.  <span data-ttu-id="4a40f-143">En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="4a40f-143">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="4a40f-144">En el **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-144">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="4a40f-145">El **propiedades de la ubicación de recepción** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4a40f-145">The **Receive Location Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="4a40f-146">En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a40f-146">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="4a40f-147">Especifique un nombre para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="4a40f-147">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="4a40f-148">Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-148">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="4a40f-149">En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a40f-149">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="4a40f-150">Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a40f-150">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the SAP system.</span></span> <span data-ttu-id="4a40f-151">Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="4a40f-151">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="4a40f-152">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-152">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="4a40f-153">Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4a40f-153">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    3.  <span data-ttu-id="4a40f-154">Haga clic en el **otros** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4a40f-154">Click the **Others** tab, and do one of the following:</span></span>  
  
        -   <span data-ttu-id="4a40f-155">Seleccione **cuenta de usuario**y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a40f-155">Select **User account**, and specify the user name and password to connect to an SAP system.</span></span>  
  
        -   <span data-ttu-id="4a40f-156">Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="4a40f-156">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
             <span data-ttu-id="4a40f-157">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="4a40f-157">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>
  
             <span data-ttu-id="4a40f-158">Haga clic en **Aceptar** para volver a la **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4a40f-158">Click **OK** to return to the **Receive Location Properties** dialog box.</span></span>  
  
9. <span data-ttu-id="4a40f-159">Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="4a40f-159">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="4a40f-160">Si ha elegido **puerto de recepción unidireccional** en el paso 4, especifique una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="4a40f-160">If you chose **One-way Receive Port** in step 4, specify a receive pipeline.</span></span> <span data-ttu-id="4a40f-161">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4a40f-161">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="4a40f-162">Si ha elegido **puerto de recepción de solicitud-respuesta** en el paso 4, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="4a40f-162">If you chose **Request Response Receive Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="4a40f-163">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4a40f-163">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="4a40f-164">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4a40f-164">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
12. <span data-ttu-id="4a40f-165">Haga clic en **Aceptar i**n el **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4a40f-165">Click **OK i**n the **Receive Location Properties** dialog box.</span></span>  
  
13. <span data-ttu-id="4a40f-166">Haga clic en **Aceptar** en el **propiedades de puerto de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4a40f-166">Click **OK** in the **Receive Port Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a40f-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a40f-167">See Also</span></span>  
[<span data-ttu-id="4a40f-168">Configurar manualmente un enlace de puerto físico para el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="4a40f-168">Manually configure a physical port binding to the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)