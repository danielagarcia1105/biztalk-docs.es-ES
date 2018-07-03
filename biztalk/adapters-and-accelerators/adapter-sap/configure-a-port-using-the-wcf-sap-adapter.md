---
title: Configurar un puerto mediante el adaptador de SAP de WCF de BizTalk | Microsoft Docs
description: Crear un puerto de SAP de WCF para enviar o recibir mensajes de SAP mediante el adaptador de mySAP en módulo de adaptador de BizTalk (BAP)
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
ms.openlocfilehash: 0a80c778e34505755a147dccf48e50ea9ea3a18d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992677"
---
# <a name="configure-a-port-using-the-wcf-sap-adapter"></a><span data-ttu-id="daba5-103">Configurar un puerto mediante el adaptador de SAP de WCF</span><span class="sxs-lookup"><span data-stu-id="daba5-103">Configure a port using the WCF-SAP adapter</span></span>
<span data-ttu-id="daba5-104">Este tema proporciona instrucciones sobre cómo configurar SAP de WCF de envío y puertos de recepción para realizar operaciones de entrada y salidas en el sistema de SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daba5-104">This topic provides instructions on how to configure WCF-SAP send and receive ports to perform outbound and inbound operations on SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="daba5-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="daba5-105">Prerequisites</span></span>  
<span data-ttu-id="daba5-106">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="daba5-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="daba5-107">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span><span class="sxs-lookup"><span data-stu-id="daba5-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a><span data-ttu-id="daba5-108">Implementar los adaptadores para enviar mensajes a SAP</span><span class="sxs-lookup"><span data-stu-id="daba5-108">Deploy adapters to send messages to SAP</span></span>  
<span data-ttu-id="daba5-109">Complete los pasos siguientes para configurar un SAP de WCF el puerto de envío para enviar mensajes al sistema de SAP mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="daba5-109">Complete the following steps to configure a WCF-SAP send port for sending messages to SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="daba5-110">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="daba5-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="daba5-111">Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="daba5-111">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="daba5-112">Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="daba5-112">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="daba5-113">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="daba5-113">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4. <span data-ttu-id="daba5-114">Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daba5-114">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
5. <span data-ttu-id="daba5-115">Haga clic en **puertos de envío**, apunte a **New**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre el servidor BizTalk Server y el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="daba5-115">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
6. <span data-ttu-id="daba5-116">En el **propiedades de puerto de envío** cuadro de diálogo el **General** , escriba un nombre para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="daba5-116">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7. <span data-ttu-id="daba5-117">Desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="daba5-117">From the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="daba5-118">En el cuadro de diálogo Propiedades de transporte, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="daba5-118">In the transport properties dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="daba5-119">Haga clic en el **General** pestaña, haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión.</span><span class="sxs-lookup"><span data-stu-id="daba5-119">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="daba5-120">Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="daba5-120">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="daba5-121">En el **General** ficha la **acción** texto, escriba la acción para la operación.</span><span class="sxs-lookup"><span data-stu-id="daba5-121">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="daba5-122">Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) para obtener una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="daba5-122">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) for a list of actions for each operation.</span></span> <span data-ttu-id="daba5-123">Por ejemplo, la acción que se invoca el RFC_CUSTOMER_GET sería:</span><span class="sxs-lookup"><span data-stu-id="daba5-123">For example, the action to invoke the RFC_CUSTOMER_GET would be:</span></span>  
  
      ```  
      http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
      ```  
  
   3. <span data-ttu-id="daba5-124">Haga clic en el **enlace** pestaña y especificar valores para enlazar las propiedades expuestas por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daba5-124">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="daba5-125">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="daba5-125">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="daba5-126">Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="daba5-126">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="daba5-127">Por ejemplo, operaciones relacionadas con entrada de enlace de propiedades no están disponibles al configurar un puerto de envío debido a operaciones de entrada requieren una configuración de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="daba5-127">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
   4. <span data-ttu-id="daba5-128">Haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="daba5-128">Click the **Credentials** tab and do one of the following:</span></span>  
  
   -   <span data-ttu-id="daba5-129">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="daba5-129">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
   -   <span data-ttu-id="daba5-130">Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="daba5-130">Select the **Use Single Sign-On** option, and specify an affiliate SSO application.</span></span>  
  
        <span data-ttu-id="daba5-131">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="daba5-131">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>  
  
        <span data-ttu-id="daba5-132">Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="daba5-132">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="daba5-133">Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="daba5-133">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="daba5-134">Si decide crear un **puerto de envío unidireccional estático** en el paso 5, especifique una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="daba5-134">If you chose to create a **Static One-Way Send Port** in step 5, specify a send pipeline.</span></span> <span data-ttu-id="daba5-135">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="daba5-135">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="daba5-136">Si decide crear un **puerto de petición-respuesta estático** en el paso 5, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="daba5-136">If you chose to create a **Static Solicit-Response Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="daba5-137">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="daba5-137">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="daba5-138">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="daba5-138">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="daba5-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="daba5-139">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a><span data-ttu-id="daba5-140">Implementar los adaptadores para recibir mensajes de SAP</span><span class="sxs-lookup"><span data-stu-id="daba5-140">Deploy adapters to receive messages from SAP</span></span>  
<span data-ttu-id="daba5-141">Complete los pasos siguientes para configurar un SAP de WCF-puerto de recepción para recibir mensajes de sistema de SAP mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="daba5-141">Complete the following steps to configure a WCF-SAP receive port for receiving messages from SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="daba5-142">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="daba5-142">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="daba5-143">Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="daba5-143">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="daba5-144">Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="daba5-144">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="daba5-145">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="daba5-145">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4. <span data-ttu-id="daba5-146">Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daba5-146">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
5. <span data-ttu-id="daba5-147">Haga clic en **puertos de recepción**, apunte a **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta** en función de la modo de comunicación entre el servidor BizTalk Server y el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="daba5-147">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port** depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
6. <span data-ttu-id="daba5-148">En el **propiedades de puerto de recepción** cuadro de diálogo el **General** , escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="daba5-148">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
7. <span data-ttu-id="daba5-149">En el **ubicaciones de recepción** , haga clic **New**.</span><span class="sxs-lookup"><span data-stu-id="daba5-149">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="daba5-150">El **propiedades de ubicación de recepción** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="daba5-150">The **Receive Location Properties** dialog box appears.</span></span>  
  
8. <span data-ttu-id="daba5-151">En el **propiedades de ubicación de recepción** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="daba5-151">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="daba5-152">Especifique un nombre para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="daba5-152">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="daba5-153">Desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="daba5-153">From the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
9. <span data-ttu-id="daba5-154">En el cuadro de diálogo Propiedades de transporte, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="daba5-154">In the transport properties dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="daba5-155">Haga clic en el **General** pestaña, haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión.</span><span class="sxs-lookup"><span data-stu-id="daba5-155">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="daba5-156">Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="daba5-156">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="daba5-157">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**.</span><span class="sxs-lookup"><span data-stu-id="daba5-157">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="daba5-158">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="daba5-158">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="daba5-159">Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="daba5-159">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="daba5-160">Por ejemplo, operaciones relacionadas con entrada de enlace de propiedades no están disponibles al configurar un puerto de envío debido a operaciones de entrada requieren una configuración de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="daba5-160">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
   3. <span data-ttu-id="daba5-161">Haga clic en el **otros** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="daba5-161">Click the **Other** tab, and do one of the following:</span></span>  
  
   4. <span data-ttu-id="daba5-162">Seleccione **cuenta de usuario**y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="daba5-162">Select **User account**, and specify the user name and password to connect to an SAP system.</span></span>  
  
   5. <span data-ttu-id="daba5-163">Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="daba5-163">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
       <span data-ttu-id="daba5-164">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="daba5-164">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>  
  
       <span data-ttu-id="daba5-165">Haga clic en **Aceptar** para volver a la **propiedades de ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="daba5-165">Click **OK** to return to the **Receive Location Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="daba5-166">Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="daba5-166">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
11. <span data-ttu-id="daba5-167">Si decide crear **puerto de recepción unidireccional** en el paso 5, especifique una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="daba5-167">If you chose to create **One-way Receive Port** in step 5, specify a receive pipeline.</span></span> <span data-ttu-id="daba5-168">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="daba5-168">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="daba5-169">Si decide crear **puerto de recepción de solicitud-respuesta** en el paso 5, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="daba5-169">If you chose to create **Request Response Receive Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="daba5-170">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="daba5-170">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="daba5-171">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="daba5-171">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
13. <span data-ttu-id="daba5-172">Haga clic en **Aceptar** en el **propiedades de ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="daba5-172">Click **OK** in the **Receive Location Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="daba5-173">Haga clic en **Aceptar** en el **propiedades de puerto de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="daba5-173">Click **OK** in the **Receive Port Properties** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="daba5-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="daba5-174">See also</span></span>
[<span data-ttu-id="daba5-175">Configurar manualmente un enlace de puerto físico para el adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="daba5-175">Manually configure a physical port binding to the SAP adapter</span></span>](manually-configure-a-physical-port-binding-to-the-sap-adapter.md)