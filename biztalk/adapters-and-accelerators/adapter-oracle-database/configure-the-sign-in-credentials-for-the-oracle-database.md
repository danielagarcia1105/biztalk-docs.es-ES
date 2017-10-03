---
title: "Configurar el inicio de sesión en las credenciales para la base de datos de Oracle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Enter the credentials
helpviewer_keywords:
- credentials, specifying at run time
- credentials, specifying at design time
ms.assetid: d8f62829-ce77-4d82-a411-2eeefb6fe75a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eda20ad4e04a9962e471ab98eb0bc5695b391007
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-sign-in-credentials-for-the-oracle-database"></a><span data-ttu-id="cd7b7-102">Configurar el inicio de sesión en las credenciales para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="cd7b7-102">Configure the sign in credentials for the Oracle Database</span></span>
<span data-ttu-id="cd7b7-103">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] requiere que los clientes de adaptador proporcionar las credenciales del cliente.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="cd7b7-104">El adaptador utiliza estas credenciales para autenticar al usuario con la base de datos de Oracle y para establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-104">The adapter uses these credentials to authenticate the user with the Oracle database and to establish a connection.</span></span>  
  
 <span data-ttu-id="cd7b7-105">Los clientes de adaptador pueden proporcionar las credenciales del cliente tanto al usar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y cuando se usa el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-105">Adapter clients can provide the client credentials both when using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and when using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="cd7b7-106">Al utilizar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], se necesitan credenciales para generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-106">When using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], credentials are required to generate the metadata.</span></span> <span data-ttu-id="cd7b7-107">Cuando se usa el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, las credenciales son necesarias para realizar operaciones en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-107">When using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, credentials are required to perform operations on the Oracle database.</span></span> <span data-ttu-id="cd7b7-108">Este tema proporciona información acerca de cómo especificar las credenciales del cliente en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-108">This topic provides information about specifying client credentials in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="specifying-client-credentials-from-visual-studio"></a><span data-ttu-id="cd7b7-109">Especifique las credenciales de cliente desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cd7b7-109">Specifying Client Credentials from Visual Studio</span></span>  
 <span data-ttu-id="cd7b7-110">Desde Visual Studio, debe especificar las credenciales mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd7b7-110">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-specify-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="cd7b7-111">Para especificar las credenciales mediante el complemento Consume Adapter Service</span><span class="sxs-lookup"><span data-stu-id="cd7b7-111">To specify credentials using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="cd7b7-112">Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-112">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="cd7b7-113">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd7b7-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="cd7b7-114">Use</span><span class="sxs-lookup"><span data-stu-id="cd7b7-114">Use this</span></span>|<span data-ttu-id="cd7b7-115">Para</span><span class="sxs-lookup"><span data-stu-id="cd7b7-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cd7b7-116">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="cd7b7-116">**Categories**</span></span>|<span data-ttu-id="cd7b7-117">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="cd7b7-118">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="cd7b7-118">**Templates**</span></span>|<span data-ttu-id="cd7b7-119">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-119">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="cd7b7-120">Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="cd7b7-121">En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** seleccione **oracleDBBinding**y haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="cd7b7-122">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha desde y hacia el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle:</span><span class="sxs-lookup"><span data-stu-id="cd7b7-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  
  
    -   <span data-ttu-id="cd7b7-123">Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-123">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
    -   <span data-ttu-id="cd7b7-124">Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-124">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
6.  <span data-ttu-id="cd7b7-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-125">Click **OK**.</span></span>  
  
#### <a name="to-specify-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="cd7b7-126">Para especificar las credenciales mediante el Asistente para agregar metadatos de adaptador</span><span class="sxs-lookup"><span data-stu-id="cd7b7-126">To specify credentials using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="cd7b7-127">Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-127">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="cd7b7-128">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd7b7-128">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="cd7b7-129">Use</span><span class="sxs-lookup"><span data-stu-id="cd7b7-129">Use this</span></span>|<span data-ttu-id="cd7b7-130">Para</span><span class="sxs-lookup"><span data-stu-id="cd7b7-130">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cd7b7-131">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="cd7b7-131">**Categories**</span></span>|<span data-ttu-id="cd7b7-132">Haga clic en **agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-132">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="cd7b7-133">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="cd7b7-133">**Templates**</span></span>|<span data-ttu-id="cd7b7-134">Haga clic en **agregar metadatos de adaptador**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-134">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="cd7b7-135">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-135">Click **Add**.</span></span> <span data-ttu-id="cd7b7-136">Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd7b7-136">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="cd7b7-137">En el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], seleccione **WCF-OracleDB**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-137">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleDB**.</span></span> <span data-ttu-id="cd7b7-138">Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-138">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cd7b7-139">Si ya tiene un puerto de WCF-OracleDB configurado en BizTalk, seleccione el puerto de la **puerto** lista.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-139">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="cd7b7-140">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-140">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="cd7b7-141">En el **Consume Adapter Service** cuadro de diálogo, desde el **selecciona un enlace** seleccione **oracleDBBinding**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-141">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="cd7b7-142">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** lista, seleccione **nombre de usuario** y Especifique el nombre de usuario y la contraseña para conectarse a la base de datos de Oracle:</span><span class="sxs-lookup"><span data-stu-id="cd7b7-142">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  
  
    -   <span data-ttu-id="cd7b7-143">Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-143">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
    -   <span data-ttu-id="cd7b7-144">Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-144">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
8.  <span data-ttu-id="cd7b7-145">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-145">Click **OK**.</span></span>  
  
## <a name="specifying-client-credentials-from-the-biztalk-server-administration-console"></a><span data-ttu-id="cd7b7-146">Especifique las credenciales de cliente desde la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="cd7b7-146">Specifying Client Credentials from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="cd7b7-147">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar las credenciales como parte de la configuración del puerto WCF-Custom o WCF-OracleDB.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-147">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the credentials as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  
  
#### <a name="to-specify-client-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="cd7b7-148">Para especificar las credenciales de cliente para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="cd7b7-148">To specify client credentials for the WCF-Custom Port</span></span>  
  
1.  <span data-ttu-id="cd7b7-149">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-149">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="cd7b7-150">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-150">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="cd7b7-151">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-151">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="cd7b7-152">En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-152">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="cd7b7-153">Para un puerto de envío en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cd7b7-153">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="cd7b7-154">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-154">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="cd7b7-155">Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-155">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="cd7b7-156">Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-156">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="cd7b7-157">Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-157">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
5.  <span data-ttu-id="cd7b7-158">Para un puerto de recepción, en el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **otros** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cd7b7-158">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="cd7b7-159">Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-159">Select **User account** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="cd7b7-160">Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-160">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="cd7b7-161">Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-161">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="cd7b7-162">Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-162">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
6.  <span data-ttu-id="cd7b7-163">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-163">Click **OK**.</span></span>  
  
#### <a name="to-specify-credentials-for-the-wcf-oracledb-port"></a><span data-ttu-id="cd7b7-164">Para especificar las credenciales para el puerto de WCF-OracleDB</span><span class="sxs-lookup"><span data-stu-id="cd7b7-164">To specify credentials for the WCF-OracleDB port</span></span>  
  
1.  <span data-ttu-id="cd7b7-165">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-165">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="cd7b7-166">Agregar el adaptador de WCF-OracleDB a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-166">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="cd7b7-167">Para obtener instrucciones, consulte [agregar el adaptador de la base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="cd7b7-167">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="cd7b7-168">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-168">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="cd7b7-169">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-169">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="cd7b7-170">En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-OracleDB**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-170">In the port properties dialog box, from the **Type** drop-down list, select **WCF-OracleDB**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd7b7-171">Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** ficha en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-171">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="cd7b7-172">En el cuadro de diálogo Propiedades de puerto, haga clic en el **enlace** ficha. Desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-172">In the port properties dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  
  
6.  <span data-ttu-id="cd7b7-173">Si va a crear un puerto de envío, en el cuadro de diálogo de propiedades de transporte, haga clic en el **credenciales** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cd7b7-173">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="cd7b7-174">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-174">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
        -   <span data-ttu-id="cd7b7-175">Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-175">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="cd7b7-176">Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-176">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="cd7b7-177">Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-177">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
7.  <span data-ttu-id="cd7b7-178">Si va a crear un puerto de recepción, en el cuadro de diálogo de propiedades de transporte, haga clic en el **otros** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cd7b7-178">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="cd7b7-179">Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-179">Select **User account** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
        -   <span data-ttu-id="cd7b7-180">Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-180">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="cd7b7-181">Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-181">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="cd7b7-182">Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-182">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
8.  <span data-ttu-id="cd7b7-183">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd7b7-183">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7b7-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd7b7-184">See Also</span></span>  
<span data-ttu-id="cd7b7-185">[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span><span class="sxs-lookup"><span data-stu-id="cd7b7-185">[Building Blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span></span>  
 [<span data-ttu-id="cd7b7-186">Conectarse a la base de datos de Oracle mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="cd7b7-186">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)