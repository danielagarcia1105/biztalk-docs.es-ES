---
title: Configurar un puerto con un adaptador SAP de WCF de BizTalk | Documentos de Microsoft
description: Crear un puerto de SAP de WCF para enviar o recibir mensajes de SAP mediante el adaptador de mySAP en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 420683f8-2516-4c65-895d-fe535824d450
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 967ad68fb32cb8787ae02d4e6fe878c5bb78da2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218740"
---
# <a name="configure-a-port-using-the-wcf-sap-adapter"></a><span data-ttu-id="0a961-103">Configurar un puerto con un adaptador SAP de WCF</span><span class="sxs-lookup"><span data-stu-id="0a961-103">Configure a port using the WCF-SAP adapter</span></span>
<span data-ttu-id="0a961-104">Este tema proporciona instrucciones sobre cómo configurar WCF SAP de envío y puertos de recepción para realizar operaciones entrantes y salientes en el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a961-104">This topic provides instructions on how to configure WCF-SAP send and receive ports to perform outbound and inbound operations on SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a961-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0a961-105">Prerequisites</span></span>  
<span data-ttu-id="0a961-106">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0a961-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="0a961-107">Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span><span class="sxs-lookup"><span data-stu-id="0a961-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a><span data-ttu-id="0a961-108">Implementar los adaptadores para enviar mensajes a SAP</span><span class="sxs-lookup"><span data-stu-id="0a961-108">Deploy adapters to send messages to SAP</span></span>  
<span data-ttu-id="0a961-109">Complete los pasos siguientes para configurar un SAP WCF puerto de envío para enviar mensajes al sistema SAP mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0a961-109">Complete the following steps to configure a WCF-SAP send port for sending messages to SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="0a961-110">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0a961-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="0a961-111">Agregar el adaptador SAP de WCF para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0a961-111">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="0a961-112">Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="0a961-112">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="0a961-113">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="0a961-113">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="0a961-114">Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a961-114">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
5.  <span data-ttu-id="0a961-115">Haga clic en **puertos de envío**, seleccione **nuevo**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre el servidor BizTalk Server y el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="0a961-115">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
6.  <span data-ttu-id="0a961-116">En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="0a961-116">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7.  <span data-ttu-id="0a961-117">Desde el **tipo** la lista desplegable, seleccione el adaptador de WCF-SAP que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="0a961-117">From the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="0a961-118">En el cuadro de diálogo Propiedades de transporte, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a961-118">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0a961-119">Haga clic en el **General** , haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión.</span><span class="sxs-lookup"><span data-stu-id="0a961-119">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="0a961-120">Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="0a961-120">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="0a961-121">En el **General** ficha la **acción** texto, escriba la acción para la operación.</span><span class="sxs-lookup"><span data-stu-id="0a961-121">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="0a961-122">Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) para obtener una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="0a961-122">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) for a list of actions for each operation.</span></span> <span data-ttu-id="0a961-123">Por ejemplo, la acción que se invoca el RFC_CUSTOMER_GET sería:</span><span class="sxs-lookup"><span data-stu-id="0a961-123">For example, the action to invoke the RFC_CUSTOMER_GET would be:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
        ```  
  
    3.  <span data-ttu-id="0a961-124">Haga clic en el **enlace** pestaña y especificar valores para enlazar propiedades expuestas por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a961-124">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="0a961-125">Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0a961-125">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0a961-126">Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a961-126">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="0a961-127">Por ejemplo, operaciones relacionadas para entrada de propiedades de enlace no están disponibles al configurar un puerto de envío dado que las operaciones de entrada requieren una configuración de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a961-127">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
    4.  <span data-ttu-id="0a961-128">Haga clic en el **credenciales** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0a961-128">Click the **Credentials** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="0a961-129">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="0a961-129">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="0a961-130">Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="0a961-130">Select the **Use Single Sign-On** option, and specify an affiliate SSO application.</span></span>  
  
         <span data-ttu-id="0a961-131">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="0a961-131">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>  
  
         <span data-ttu-id="0a961-132">Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a961-132">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="0a961-133">Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="0a961-133">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="0a961-134">Si decide crear un **puerto de envío unidireccional estático** en el paso 5, especifique una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="0a961-134">If you chose to create a **Static One-Way Send Port** in step 5, specify a send pipeline.</span></span> <span data-ttu-id="0a961-135">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0a961-135">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="0a961-136">Si decide crear un **puerto de petición-respuesta estático** en el paso 5, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a961-136">If you chose to create a **Static Solicit-Response Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="0a961-137">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0a961-137">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="0a961-138">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0a961-138">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="0a961-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a961-139">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a><span data-ttu-id="0a961-140">Implementar los adaptadores para recibir mensajes de SAP</span><span class="sxs-lookup"><span data-stu-id="0a961-140">Deploy adapters to receive messages from SAP</span></span>  
<span data-ttu-id="0a961-141">Complete los pasos siguientes para configurar un SAP WCF puerto de recepción para recibir mensajes de sistema SAP mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0a961-141">Complete the following steps to configure a WCF-SAP receive port for receiving messages from SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="0a961-142">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0a961-142">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="0a961-143">Agregar el adaptador SAP de WCF para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0a961-143">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="0a961-144">Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="0a961-144">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="0a961-145">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="0a961-145">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="0a961-146">Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a961-146">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
5.  <span data-ttu-id="0a961-147">Haga clic en **puertos de recepción**, seleccione **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta** en función de la modo de comunicación entre el servidor BizTalk Server y el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="0a961-147">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port** depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
6.  <span data-ttu-id="0a961-148">En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a961-148">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
7.  <span data-ttu-id="0a961-149">En el **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0a961-149">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="0a961-150">El **propiedades de la ubicación de recepción** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0a961-150">The **Receive Location Properties** dialog box appears.</span></span>  
  
8.  <span data-ttu-id="0a961-151">En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a961-151">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0a961-152">Especifique un nombre para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a961-152">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="0a961-153">Desde el **tipo** la lista desplegable, seleccione el adaptador de WCF-SAP que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="0a961-153">From the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
9. <span data-ttu-id="0a961-154">En el cuadro de diálogo Propiedades de transporte, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a961-154">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0a961-155">Haga clic en el **General** , haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión.</span><span class="sxs-lookup"><span data-stu-id="0a961-155">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="0a961-156">Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="0a961-156">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="0a961-157">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**.</span><span class="sxs-lookup"><span data-stu-id="0a961-157">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="0a961-158">Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0a961-158">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0a961-159">Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a961-159">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="0a961-160">Por ejemplo, operaciones relacionadas para entrada de propiedades de enlace no están disponibles al configurar un puerto de envío dado que las operaciones de entrada requieren una configuración de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a961-160">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
    3.  <span data-ttu-id="0a961-161">Haga clic en el **otros** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0a961-161">Click the **Other** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="0a961-162">Seleccione **cuenta de usuario**y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="0a961-162">Select **User account**, and specify the user name and password to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="0a961-163">Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="0a961-163">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
         <span data-ttu-id="0a961-164">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="0a961-164">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>  
  
         <span data-ttu-id="0a961-165">Haga clic en **Aceptar** para volver a la **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0a961-165">Click **OK** to return to the **Receive Location Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="0a961-166">Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="0a961-166">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
11. <span data-ttu-id="0a961-167">Si decide crear **puerto de recepción unidireccional** en el paso 5, especifique una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a961-167">If you chose to create **One-way Receive Port** in step 5, specify a receive pipeline.</span></span> <span data-ttu-id="0a961-168">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0a961-168">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="0a961-169">Si decide crear **puerto de recepción de solicitud-respuesta** en el paso 5, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a961-169">If you chose to create **Request Response Receive Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="0a961-170">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0a961-170">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="0a961-171">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0a961-171">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
13. <span data-ttu-id="0a961-172">Haga clic en **Aceptar** en el **propiedades de la ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0a961-172">Click **OK** in the **Receive Location Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="0a961-173">Haga clic en **Aceptar** en el **propiedades de puerto de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0a961-173">Click **OK** in the **Receive Port Properties** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a961-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a961-174">See also</span></span>
[<span data-ttu-id="0a961-175">Configurar manualmente un enlace de puerto físico para el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="0a961-175">Manually configure a physical port binding to the SAP adapter</span></span>](manually-configure-a-physical-port-binding-to-the-sap-adapter.md)