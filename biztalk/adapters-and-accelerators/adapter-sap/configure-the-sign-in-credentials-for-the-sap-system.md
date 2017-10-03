---
title: "Configurar el inicio de sesión en las credenciales para el sistema SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb41106b-b673-4fcf-a56e-6208e3113469
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a6ace75f66bb7fdd4cfb3362f7d019ab99d73bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-sign-in-credentials-for-the-sap-system"></a><span data-ttu-id="97094-102">Configurar el inicio de sesión en las credenciales para el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="97094-102">Configure the sign in credentials for the SAP system</span></span>
<span data-ttu-id="97094-103">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requiere que los clientes de adaptador proporcionar las credenciales del cliente.</span><span class="sxs-lookup"><span data-stu-id="97094-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="97094-104">El adaptador utiliza estas credenciales para autenticar al usuario con el sistema SAP y para establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="97094-104">The adapter uses these credentials to authenticate the user with the SAP system and to establish a connection.</span></span>  
  
 <span data-ttu-id="97094-105">Los clientes de adaptador pueden proporcionar al cliente tanto las credenciales en tiempo de diseño o tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="97094-105">Adapter clients can provide the client credentials both at design time or run time.</span></span> <span data-ttu-id="97094-106">En tiempo de diseño, se necesitan credenciales para generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="97094-106">At design time, credentials are required to generate the metadata.</span></span> <span data-ttu-id="97094-107">En tiempo de ejecución, se necesitan credenciales para realizar operaciones en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="97094-107">At run time, credentials are required to perform operations on the SAP system.</span></span> <span data-ttu-id="97094-108">Esta sección proporciona información acerca de cómo especificar las credenciales del cliente en tiempo de diseño y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="97094-108">This section provides information about specifying client credentials at design time and run time.</span></span>  
  
## <a name="enter-the-client-credentials-at-design-time"></a><span data-ttu-id="97094-109">Escriba las credenciales del cliente en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="97094-109">Enter the client credentials at design time</span></span>  
 <span data-ttu-id="97094-110">Para tiempo de diseño, puede especificar las credenciales mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97094-110">For design time, you can specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="enter-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="97094-111">Escriba las credenciales mediante el complemento Consume Adapter Service</span><span class="sxs-lookup"><span data-stu-id="97094-111">Enter credentials using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="97094-112">Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="97094-112">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="97094-113">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="97094-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="97094-114">Use</span><span class="sxs-lookup"><span data-stu-id="97094-114">Use this</span></span>|<span data-ttu-id="97094-115">Para</span><span class="sxs-lookup"><span data-stu-id="97094-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="97094-116">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="97094-116">**Categories**</span></span>|<span data-ttu-id="97094-117">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="97094-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="97094-118">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="97094-118">**Templates**</span></span>|<span data-ttu-id="97094-119">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="97094-119">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="97094-120">Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="97094-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="97094-121">En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** seleccione **sapBinding**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="97094-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="97094-122">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha desde y hacia el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="97094-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
6.  <span data-ttu-id="97094-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97094-123">Click **OK**.</span></span>  
  
### <a name="enter-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="97094-124">Escriba las credenciales mediante el Asistente para agregar metadatos de adaptador</span><span class="sxs-lookup"><span data-stu-id="97094-124">Enter credentials using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="97094-125">Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="97094-125">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="97094-126">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="97094-126">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="97094-127">Use</span><span class="sxs-lookup"><span data-stu-id="97094-127">Use this</span></span>|<span data-ttu-id="97094-128">Para</span><span class="sxs-lookup"><span data-stu-id="97094-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="97094-129">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="97094-129">**Categories**</span></span>|<span data-ttu-id="97094-130">Haga clic en **agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="97094-130">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="97094-131">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="97094-131">**Templates**</span></span>|<span data-ttu-id="97094-132">Haga clic en **agregar metadatos de adaptador**.</span><span class="sxs-lookup"><span data-stu-id="97094-132">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="97094-133">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="97094-133">Click **Add**.</span></span> <span data-ttu-id="97094-134">Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97094-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="97094-135">En el Asistente para agregar adaptador, seleccione **WCF SAP**.</span><span class="sxs-lookup"><span data-stu-id="97094-135">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="97094-136">Seleccione el equipo donde está instalado el servidor BizTalk Server y el nombre de la base de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="97094-136">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="97094-137">Si ya tiene un puerto de SAP de WCF configurado en BizTalk, seleccione el puerto de la **puerto** lista.</span><span class="sxs-lookup"><span data-stu-id="97094-137">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="97094-138">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="97094-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="97094-139">En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** seleccione **sapBinding**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="97094-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="97094-140">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha desde y hacia el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="97094-140">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
8.  <span data-ttu-id="97094-141">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97094-141">Click **OK**.</span></span>  
  
## <a name="enter-client-credentials-at-run-time"></a><span data-ttu-id="97094-142">Escriba las credenciales del cliente en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="97094-142">Enter client credentials at run time</span></span>  
 <span data-ttu-id="97094-143">Para tiempo de ejecución, puede especificar las credenciales del cliente como parte de la configuración del puerto WCF-Custom o WCF-SAP en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="97094-143">For run time, you can specify the client credentials as part of the WCF-Custom or WCF-SAP port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="97094-144">Escriba las credenciales para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="97094-144">Enter credentials for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="97094-145">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="97094-145">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="97094-146">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="97094-146">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="97094-147">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="97094-147">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="97094-148">En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="97094-148">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="97094-149">Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** ficha en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="97094-149">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="97094-150">Para un puerto de envío en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="97094-150">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="97094-151">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="97094-151">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="97094-152">Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="97094-152">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
5.  <span data-ttu-id="97094-153">Para un puerto de recepción, en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **otros** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="97094-153">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="97094-154">Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="97094-154">Select **User account** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="97094-155">Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="97094-155">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
6.  <span data-ttu-id="97094-156">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97094-156">Click **OK**.</span></span>  
  
### <a name="enter-credentials-for-the-wcf-sap-port"></a><span data-ttu-id="97094-157">Escriba las credenciales para el puerto de SAP de WCF</span><span class="sxs-lookup"><span data-stu-id="97094-157">Enter credentials for the WCF-SAP port</span></span>  
  
1.  <span data-ttu-id="97094-158">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="97094-158">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="97094-159">Agregar el adaptador SAP de WCF para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="97094-159">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="97094-160">Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="97094-160">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="97094-161">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="97094-161">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="97094-162">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="97094-162">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="97094-163">En el cuadro de diálogo de propiedades de puerto de la **tipo** la lista desplegable, seleccione el adaptador de WCF-SAP que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="97094-163">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="97094-164">Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** ficha en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="97094-164">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="97094-165">Si va a crear un puerto de envío, en el cuadro de diálogo de propiedades de transporte, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="97094-165">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="97094-166">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="97094-166">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="97094-167">Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="97094-167">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
6.  <span data-ttu-id="97094-168">Si va a crear un puerto de recepción, en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **otros** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="97094-168">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="97094-169">Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="97094-169">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="97094-170">Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="97094-170">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
7.  <span data-ttu-id="97094-171">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97094-171">Click **OK**.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]<span data-ttu-id="97094-172">También es compatible con el sistema de inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="97094-172"> also supports the Enterprise Single Sign-On (SSO) system.</span></span> <span data-ttu-id="97094-173">SSO sólo es aplicable en el escenario de BizTalk, en el que el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] es consciente de las aplicaciones afiliadas SSO.</span><span class="sxs-lookup"><span data-stu-id="97094-173">SSO is only applicable in the BizTalk scenario, in which the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] is aware of SSO affiliate applications.</span></span> <span data-ttu-id="97094-174">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="97094-174">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="97094-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="97094-175">See Also</span></span>  
[<span data-ttu-id="97094-176">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="97094-176">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)