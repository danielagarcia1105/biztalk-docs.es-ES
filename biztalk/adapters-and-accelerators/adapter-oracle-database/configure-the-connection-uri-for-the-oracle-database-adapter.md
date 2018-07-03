---
title: Configurar el URI de conexión para el adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at design time
- connection URI, specifying at run time
ms.assetid: 9f302b67-0bcc-44d1-9517-10d402873540
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 849adf16faa96726fb3d182930be8f4965eb180d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007213"
---
# <a name="configure-the-connection-uri-for-the-oracle-database-adapter"></a><span data-ttu-id="ada9e-102">Configurar el URI de conexión para el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ada9e-102">Configure the connection URI for the Oracle Database adapter</span></span>
<span data-ttu-id="ada9e-103">Un URI de conexión es una cadena de conexión que contiene los parámetros necesarios para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ada9e-103">A connection URI is a connection string that contains parameters required to connect to the Oracle database.</span></span> <span data-ttu-id="ada9e-104">Al usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar el URI para conectarse a la base de datos de Oracle para generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ada9e-104">While using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the URI to connect to the Oracle database to generate the metadata.</span></span> <span data-ttu-id="ada9e-105">Al configurar una orquestación mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar el URI para conectarse a la base de datos de Oracle para realizar operaciones.</span><span class="sxs-lookup"><span data-stu-id="ada9e-105">While configuring an orchestration using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the URI to connect to the Oracle database to perform operations.</span></span>  

## <a name="specifying-the-connection-uri-from-visual-studio"></a><span data-ttu-id="ada9e-106">Especificar la conexión URI desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ada9e-106">Specifying the Connection URI from Visual Studio</span></span>  
 <span data-ttu-id="ada9e-107">Desde Visual Studio, debe especificar las credenciales mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ada9e-107">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-specify-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="ada9e-108">Para especificar el URI de conexión mediante el complemento Consume Adapter Service</span><span class="sxs-lookup"><span data-stu-id="ada9e-108">To specify the Connection URI using Consume Adapter Service Add-in</span></span>  

1. <span data-ttu-id="ada9e-109">Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-109">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="ada9e-110">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ada9e-110">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="ada9e-111">Use</span><span class="sxs-lookup"><span data-stu-id="ada9e-111">Use this</span></span>    |             <span data-ttu-id="ada9e-112">Para</span><span class="sxs-lookup"><span data-stu-id="ada9e-112">To do this</span></span>             |
   |----------------|------------------------------------|
   | <span data-ttu-id="ada9e-113">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="ada9e-113">**Categories**</span></span> | <span data-ttu-id="ada9e-114">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-114">Click **Consume Adapter Service**.</span></span> |
   | <span data-ttu-id="ada9e-115">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="ada9e-115">**Templates**</span></span>  | <span data-ttu-id="ada9e-116">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-116">Click **Consume Adapter Service**.</span></span> |


3. <span data-ttu-id="ada9e-117">Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-117">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4. <span data-ttu-id="ada9e-118">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** , seleccione **oracleDBBinding**y haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-118">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and click **Configure**.</span></span>  

5. <span data-ttu-id="ada9e-119">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** pestaña y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle:</span><span class="sxs-lookup"><span data-stu-id="ada9e-119">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  

   -   <span data-ttu-id="ada9e-120">Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="ada9e-120">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

   -   <span data-ttu-id="ada9e-121">Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="ada9e-121">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

6. <span data-ttu-id="ada9e-122">Haga clic en el **propiedades de URI** pestaña y especificar valores para parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="ada9e-122">Click the **URI Properties** tab, and specify values for different parameters.</span></span> <span data-ttu-id="ada9e-123">Para obtener más información sobre el URI de conexión para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="ada9e-123">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  

7. <span data-ttu-id="ada9e-124">Haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que son necesarios antes de generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="ada9e-124">Click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="ada9e-125">Para obtener más información acerca de las propiedades de enlace, consulte [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="ada9e-125">For more information about binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  

8. <span data-ttu-id="ada9e-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-126">Click **OK**.</span></span>  

#### <a name="to-specify-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="ada9e-127">Para especificar el URI de conexión mediante el Asistente para agregar metadatos de adaptador</span><span class="sxs-lookup"><span data-stu-id="ada9e-127">To specify the Connection URI using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="ada9e-128">Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-128">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="ada9e-129">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ada9e-129">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="ada9e-130">Use</span><span class="sxs-lookup"><span data-stu-id="ada9e-130">Use this</span></span>    |           <span data-ttu-id="ada9e-131">Para</span><span class="sxs-lookup"><span data-stu-id="ada9e-131">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="ada9e-132">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="ada9e-132">**Categories**</span></span> |     <span data-ttu-id="ada9e-133">Haga clic en **agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-133">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="ada9e-134">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="ada9e-134">**Templates**</span></span>  | <span data-ttu-id="ada9e-135">Haga clic en **agregar metadatos de adaptador**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-135">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="ada9e-136">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-136">Click **Add**.</span></span> <span data-ttu-id="ada9e-137">Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ada9e-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="ada9e-138">En el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], seleccione **WCF-OracleDB**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-138">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleDB**.</span></span> <span data-ttu-id="ada9e-139">Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ada9e-139">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="ada9e-140">Si ya tiene un puerto de WCF-OracleDB configurado en BizTalk, seleccione el puerto desde el **puerto** lista.</span><span class="sxs-lookup"><span data-stu-id="ada9e-140">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="ada9e-141">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-141">Click **Next**.</span></span>  

6. <span data-ttu-id="ada9e-142">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** , seleccione **oracleDBBinding**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="ada9e-143">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** lista, seleccione **Username** y Especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle:</span><span class="sxs-lookup"><span data-stu-id="ada9e-143">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  

   -   <span data-ttu-id="ada9e-144">Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="ada9e-144">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

   -   <span data-ttu-id="ada9e-145">Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="ada9e-145">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

8. <span data-ttu-id="ada9e-146">Haga clic en el **propiedades de URI** pestaña y especificar valores para parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="ada9e-146">Click the **URI Properties** tab, and specify values for different parameters.</span></span> <span data-ttu-id="ada9e-147">Para obtener más información sobre el URI de conexión para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="ada9e-147">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  

9. <span data-ttu-id="ada9e-148">Haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que son necesarios antes de generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="ada9e-148">Click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="ada9e-149">Para obtener más información acerca de las propiedades de enlace, consulte [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="ada9e-149">For more information about binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  

10. <span data-ttu-id="ada9e-150">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-150">Click **OK**.</span></span>  

## <a name="specifying-the-connection-uri-from-the-biztalk-server-administration-console"></a><span data-ttu-id="ada9e-151">Especificar la conexión URI a partir de la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ada9e-151">Specifying the Connection URI from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="ada9e-152">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar las credenciales como parte de la configuración del puerto WCF-Custom o WCF-OracleDB.</span><span class="sxs-lookup"><span data-stu-id="ada9e-152">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the credentials as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  

#### <a name="to-specify-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="ada9e-153">Para especificar el URI de conexión para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="ada9e-153">To specify the Connection URI for the WCF-Custom Port</span></span>  

1. <span data-ttu-id="ada9e-154">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ada9e-154">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="ada9e-155">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-155">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="ada9e-156">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="ada9e-156">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="ada9e-157">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-157">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="ada9e-158">Para un puerto de envío en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ada9e-158">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="ada9e-159">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ada9e-159">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an Oracle database.</span></span>  

       -   <span data-ttu-id="ada9e-160">Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="ada9e-160">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

       -   <span data-ttu-id="ada9e-161">Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="ada9e-161">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

   -   <span data-ttu-id="ada9e-162">Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="ada9e-162">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

5. <span data-ttu-id="ada9e-163">Para un puerto de recepción, en el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **otros** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ada9e-163">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="ada9e-164">Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ada9e-164">Select **User account** option, and specify the user name and password to connect to an Oracle database.</span></span>  

       -   <span data-ttu-id="ada9e-165">Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="ada9e-165">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

       -   <span data-ttu-id="ada9e-166">Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="ada9e-166">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

   -   <span data-ttu-id="ada9e-167">Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="ada9e-167">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  

6. <span data-ttu-id="ada9e-168">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-168">Click **OK**.</span></span>  

#### <a name="to-specify-the-connection-uri-for-the-wcf-oracledb-port"></a><span data-ttu-id="ada9e-169">Para especificar el URI de conexión para el puerto de WCF-OracleDB</span><span class="sxs-lookup"><span data-stu-id="ada9e-169">To specify the Connection URI for the WCF-OracleDB port</span></span>  

1. <span data-ttu-id="ada9e-170">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ada9e-170">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="ada9e-171">Agregar el adaptador de WCF-OracleDB a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ada9e-171">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ada9e-172">Para obtener instrucciones, consulte [agregación del adaptador de base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="ada9e-172">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="ada9e-173">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-173">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="ada9e-174">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="ada9e-174">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="ada9e-175">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-OracleDB**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-175">In the port properties dialog box, from the **Type** drop-down list, select **WCF-OracleDB**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ada9e-176">Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-176">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="ada9e-177">En el cuadro de diálogo Propiedades de puerto, haga clic en el **enlace** ficha. Desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-177">In the port properties dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  

6. <span data-ttu-id="ada9e-178">Si va a crear un puerto de envío, en el cuadro de diálogo Propiedades de transporte, haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ada9e-178">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="ada9e-179">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ada9e-179">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the Oracle database.</span></span>  

       -   <span data-ttu-id="ada9e-180">Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="ada9e-180">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

       -   <span data-ttu-id="ada9e-181">Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="ada9e-181">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

   -   <span data-ttu-id="ada9e-182">Seleccione el **Use Single Sign-On** opción y especifique un inicio de sesión único empresarial (SSO) de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="ada9e-182">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

7. <span data-ttu-id="ada9e-183">Si va a crear un puerto de recepción, en el cuadro de diálogo Propiedades de transporte, haga clic en el **otros** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ada9e-183">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="ada9e-184">Seleccione **cuenta de usuario** opción y especifique el nombre de usuario y contraseña para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ada9e-184">Select **User account** option, and specify the user name and password to connect to the Oracle database.</span></span>  

       -   <span data-ttu-id="ada9e-185">Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="ada9e-185">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

       -   <span data-ttu-id="ada9e-186">Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="ada9e-186">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

   -   <span data-ttu-id="ada9e-187">Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="ada9e-187">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

8. <span data-ttu-id="ada9e-188">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ada9e-188">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ada9e-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="ada9e-189">See Also</span></span>  
<span data-ttu-id="ada9e-190">[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span><span class="sxs-lookup"><span data-stu-id="ada9e-190">[Building Blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span></span>  
 [<span data-ttu-id="ada9e-191">Conectarse a la base de datos de Oracle mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="ada9e-191">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)