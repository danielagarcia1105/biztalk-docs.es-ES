---
title: Configurar el inicio de sesión en las credenciales para el Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, specify credentials for the Siebel system at run time
- credentials, specifying
- how to, specify credentials for the Siebel system at design time
ms.assetid: a9fef2ba-c38e-44f7-84a3-b6a95d4dc210
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca773a4e7cd5c1d600f82b3af7b471929cff212
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971861"
---
# <a name="configure-the-sign-in-credentials-for-the-siebel"></a><span data-ttu-id="ae4bb-102">Configurar el inicio de sesión en las credenciales para el Siebel</span><span class="sxs-lookup"><span data-stu-id="ae4bb-102">Configure the sign in credentials for the Siebel</span></span>
<span data-ttu-id="ae4bb-103">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] requiere que los clientes de adaptador proporcionar las credenciales del cliente.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="ae4bb-104">El adaptador usa estas credenciales para autenticar al usuario con el sistema de Siebel y para establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-104">The adapter uses these credentials to authenticate the user with the Siebel system and to establish a connection.</span></span>  

 <span data-ttu-id="ae4bb-105">Los clientes del adaptador pueden proporcionar el cliente las credenciales en tiempo de diseño o tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-105">Adapter clients can provide the client credentials either at design time or run time.</span></span> <span data-ttu-id="ae4bb-106">En tiempo de diseño, se necesitan credenciales para generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-106">At design time, credentials are required to generate the metadata.</span></span> <span data-ttu-id="ae4bb-107">En tiempo de ejecución, se necesitan credenciales para realizar operaciones en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-107">At run time, credentials are required to perform operations on the Siebel system.</span></span> <span data-ttu-id="ae4bb-108">Esta sección proporciona información sobre cómo especificar las credenciales del cliente en tiempo de diseño y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-108">This section provides information about specifying client credentials at design time and run time.</span></span>  

## <a name="enter-the-client-credentials-at-design-time"></a><span data-ttu-id="ae4bb-109">Escriba las credenciales del cliente en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ae4bb-109">Enter the client credentials at design time</span></span>  
 <span data-ttu-id="ae4bb-110">Para el tiempo de diseño, debe especificar las credenciales mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae4bb-110">For design time, you must specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="enter-client-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="ae4bb-111">Escriba las credenciales del cliente mediante el complemento Consume Adapter Service</span><span class="sxs-lookup"><span data-stu-id="ae4bb-111">Enter client credentials using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="ae4bb-112">Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-112">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="ae4bb-113">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae4bb-113">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="ae4bb-114">Use</span><span class="sxs-lookup"><span data-stu-id="ae4bb-114">Use this</span></span>|<span data-ttu-id="ae4bb-115">Para</span><span class="sxs-lookup"><span data-stu-id="ae4bb-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ae4bb-116">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="ae4bb-116">**Categories**</span></span>|<span data-ttu-id="ae4bb-117">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="ae4bb-118">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="ae4bb-118">**Templates**</span></span>|<span data-ttu-id="ae4bb-119">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-119">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="ae4bb-120">Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="ae4bb-121">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** , seleccione **siebelBinding**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **siebelBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="ae4bb-122">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** pestaña y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse al sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

6.  <span data-ttu-id="ae4bb-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-123">Click **OK**.</span></span>  

#### <a name="enter-client-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="ae4bb-124">Escriba las credenciales del cliente mediante el Asistente para agregar metadatos de adaptador</span><span class="sxs-lookup"><span data-stu-id="ae4bb-124">Enter client credentials using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="ae4bb-125">Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-125">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="ae4bb-126">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae4bb-126">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="ae4bb-127">Use</span><span class="sxs-lookup"><span data-stu-id="ae4bb-127">Use this</span></span>    |           <span data-ttu-id="ae4bb-128">Para</span><span class="sxs-lookup"><span data-stu-id="ae4bb-128">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="ae4bb-129">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="ae4bb-129">**Categories**</span></span> |     <span data-ttu-id="ae4bb-130">Haga clic en **agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-130">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="ae4bb-131">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="ae4bb-131">**Templates**</span></span>  | <span data-ttu-id="ae4bb-132">Haga clic en **agregar metadatos de adaptador**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-132">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="ae4bb-133">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-133">Click **Add**.</span></span> <span data-ttu-id="ae4bb-134">Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae4bb-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="ae4bb-135">En el Asistente para agregar adaptador, seleccione **WCF-Siebel**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-135">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="ae4bb-136">Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-136">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="ae4bb-137">Si ya tiene un puerto de WCF-Siebel configurado en BizTalk, seleccione el puerto desde el **puerto** lista.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-137">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="ae4bb-138">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-138">Click **Next**.</span></span>  

6. <span data-ttu-id="ae4bb-139">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** , seleccione **siebelBinding**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **siebelBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="ae4bb-140">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** pestaña y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse al sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-140">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

8. <span data-ttu-id="ae4bb-141">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-141">Click **OK**.</span></span>  

## <a name="enter-client-credentials-at-run-time"></a><span data-ttu-id="ae4bb-142">Escriba las credenciales del cliente en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ae4bb-142">Enter client credentials at run time</span></span>  
 <span data-ttu-id="ae4bb-143">Para el tiempo de ejecución, debe especificar las credenciales del cliente como parte de la configuración del puerto WCF-Custom o WCF-Siebel en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-143">For run time, you must specify the client credentials as part of the WCF-Custom or WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

#### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="ae4bb-144">Escriba las credenciales para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="ae4bb-144">Enter credentials for the WCF-Custom port</span></span>  

1. <span data-ttu-id="ae4bb-145">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-145">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="ae4bb-146">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío** .</span><span class="sxs-lookup"><span data-stu-id="ae4bb-146">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="ae4bb-147">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-147">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="ae4bb-148">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-148">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="ae4bb-149">Para un puerto de envío en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ae4bb-149">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="ae4bb-150">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-150">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   -   <span data-ttu-id="ae4bb-151">Seleccione el **Use Single Sign-On** opción y especifique una aplicación de afiliado ESSO.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-151">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

5. <span data-ttu-id="ae4bb-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-152">Click **OK**.</span></span>  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]<span data-ttu-id="ae4bb-153"> También es compatible con el sistema empresarial Single Sign-On (ESSO).</span><span class="sxs-lookup"><span data-stu-id="ae4bb-153"> also supports the Enterprise Single Sign-On (ESSO) system.</span></span> <span data-ttu-id="ae4bb-154">Solo es aplicable en el escenario de BizTalk, en el que el adaptador de WCF es consciente de las aplicaciones afiliadas ESSO ESSO.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-154">ESSO is only applicable in the BizTalk scenario, in which the WCF adapter is aware of ESSO affiliate applications.</span></span> <span data-ttu-id="ae4bb-155">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="ae4bb-155">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>

#### <a name="enter-credentials-for-the-wcf-siebel-port"></a><span data-ttu-id="ae4bb-156">Escriba las credenciales para el puerto de WCF-Siebel</span><span class="sxs-lookup"><span data-stu-id="ae4bb-156">Enter credentials for the WCF-Siebel port</span></span>  

1. <span data-ttu-id="ae4bb-157">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-157">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="ae4bb-158">Agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-158">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ae4bb-159">Para obtener instrucciones, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="ae4bb-159">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="ae4bb-160">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío** .</span><span class="sxs-lookup"><span data-stu-id="ae4bb-160">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="ae4bb-161">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-161">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="ae4bb-162">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el puerto de WCF-Siebel que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-162">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel port you added earlier, and then click **Configure**.</span></span>  

5. <span data-ttu-id="ae4bb-163">Para un puerto de envío, en el cuadro de diálogo Propiedades de transporte, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ae4bb-163">For a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="ae4bb-164">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-164">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   -   <span data-ttu-id="ae4bb-165">Seleccione el **Use Single Sign-On** opción y especifique una aplicación de afiliado ESSO.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-165">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

6. <span data-ttu-id="ae4bb-166">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-166">Click **OK**.</span></span>  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]<span data-ttu-id="ae4bb-167"> También es compatible con el sistema empresarial Single Sign-On (ESSO).</span><span class="sxs-lookup"><span data-stu-id="ae4bb-167"> also supports the Enterprise Single Sign-On (ESSO) system.</span></span> <span data-ttu-id="ae4bb-168">Solo es aplicable en el escenario de BizTalk, en el que el adaptador de WCF es consciente de las aplicaciones afiliadas ESSO ESSO.</span><span class="sxs-lookup"><span data-stu-id="ae4bb-168">ESSO is only applicable in the BizTalk scenario, in which the WCF adapter is aware of ESSO affiliate applications.</span></span> <span data-ttu-id="ae4bb-169">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="ae4bb-169">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae4bb-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae4bb-170">See Also</span></span>  
[<span data-ttu-id="ae4bb-171">Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="ae4bb-171">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)