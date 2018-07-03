---
title: Configurar un puerto mediante el adaptador WCF-custom y el adaptador de base de datos de Oracle | Microsoft Docs
description: Creación de envío WCF-custom y puertos de recepción para usar el adaptador de Oracle DB en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c99ff526-ad97-4095-812f-0ce88b071e7f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 513d848d9bf95e75b8b6b983dde7019ce24ecf46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006485"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter"></a><span data-ttu-id="90598-103">Configurar un puerto mediante el adaptador WCF-custom y el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="90598-103">Configure a port using the WCF-custom adapter and Oracle Database adapter</span></span>
<span data-ttu-id="90598-104">Configuración de envío WCF-Custom y puertos de recepción para realizar operaciones de entrada y salidas en la base de datos de Oracle mediante el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90598-104">How to configure WCF-Custom send and receive ports to perform outbound and inbound operations on the Oracle database using the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="90598-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="90598-105">Prerequisites</span></span>  
<span data-ttu-id="90598-106">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="90598-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="90598-107">Consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) para obtener instrucciones de permisos.</span><span class="sxs-lookup"><span data-stu-id="90598-107">See [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) for permissions guidance.</span></span>
  
## <a name="deploy-adapters-for-sending-messages-to-an-oracle-database"></a><span data-ttu-id="90598-108">Implementar los adaptadores para enviar mensajes a una base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="90598-108">Deploy adapters for sending messages to an Oracle database</span></span>  
  
1. <span data-ttu-id="90598-109">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="90598-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="90598-110">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="90598-110">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="90598-111">Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90598-111">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
4. <span data-ttu-id="90598-112">Haga clic en **puertos de envío**, apunte a **New**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="90598-112">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the Oracle database.</span></span>  
  
5. <span data-ttu-id="90598-113">En el **propiedades de puerto de envío** cuadro de diálogo el **General** , escriba un nombre para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="90598-113">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="90598-114">Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="90598-114">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7. <span data-ttu-id="90598-115">En el **propiedades de transporte WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90598-115">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="90598-116">Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="90598-116">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the Oracle database.</span></span> <span data-ttu-id="90598-117">Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="90598-117">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="90598-118">En el **General** ficha la **acción** texto, escriba la acción para la operación.</span><span class="sxs-lookup"><span data-stu-id="90598-118">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="90598-119">Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) para obtener una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="90598-119">See [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) for a list of actions for each operation.</span></span> <span data-ttu-id="90598-120">Por ejemplo, la acción para invocar la operación de inserción de una tabla de empleados en el esquema de recursos humanos en una base de datos de Oracle es:</span><span class="sxs-lookup"><span data-stu-id="90598-120">For example, the action to invoke the Insert operation an EMPLOYEE table under the HR schema in an Oracle database is:</span></span>  
  
      ```  
      http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
      ```  
  
   3. <span data-ttu-id="90598-121">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="90598-121">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span> <span data-ttu-id="90598-122">Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90598-122">You can specify the different binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="90598-123">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="90598-123">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
   4. <span data-ttu-id="90598-124">Haga clic en el **credenciales** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="90598-124">Click the **Credentials** tab and do one of the following:</span></span>  
  
      - <span data-ttu-id="90598-125">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="90598-125">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="90598-126">Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="90598-126">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="90598-127">Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="90598-127">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
      - <span data-ttu-id="90598-128">Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="90598-128">Select the **Use Single Sign-On** option, and specify an affiliate SSO application.</span></span>  
  
        <span data-ttu-id="90598-129">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de base de datos de Oracle y BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="90598-129">For more information about security with respect to BizTalk Server, see [Security with the Oracle Database adapter and BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span></span>  
  
        <span data-ttu-id="90598-130">Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90598-130">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8. <span data-ttu-id="90598-131">Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="90598-131">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="90598-132">Si eligió **puerto de envío unidireccional estático** en el paso 4, especifique una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="90598-132">If you chose **Static One-Way Send Port** in step 4, specify a send pipeline.</span></span> <span data-ttu-id="90598-133">Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.</span><span class="sxs-lookup"><span data-stu-id="90598-133">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="90598-134">Si eligió **puerto de petición-respuesta estático** en el paso 4, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="90598-134">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="90598-135">Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.</span><span class="sxs-lookup"><span data-stu-id="90598-135">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="90598-136">Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.</span><span class="sxs-lookup"><span data-stu-id="90598-136">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
11. <span data-ttu-id="90598-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90598-137">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-for-receiving-messages-from-an-oracle-database"></a><span data-ttu-id="90598-138">Implementar los adaptadores para recibir mensajes desde una base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="90598-138">Deploy adapters for receiving messages from an Oracle database</span></span>  
  
1. <span data-ttu-id="90598-139">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="90598-139">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="90598-140">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="90598-140">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="90598-141">Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90598-141">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
4. <span data-ttu-id="90598-142">Haga clic en **puertos de recepción**, apunte a **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, en función de la modo de comunicación entre el servidor BizTalk Server y la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="90598-142">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between BizTalk Server and the Oracle database.</span></span>  
  
5. <span data-ttu-id="90598-143">En el **propiedades de puerto de recepción** cuadro de diálogo el **General** , escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="90598-143">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6. <span data-ttu-id="90598-144">En el **ubicaciones de recepción** , haga clic **New**.</span><span class="sxs-lookup"><span data-stu-id="90598-144">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="90598-145">El **propiedades de ubicación de recepción** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="90598-145">The **Receive Location Properties** dialog box appears.</span></span>  
  
7. <span data-ttu-id="90598-146">En el **propiedades de ubicación de recepción** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90598-146">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="90598-147">Especifique un nombre para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="90598-147">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="90598-148">Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="90598-148">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="90598-149">En el **propiedades de transporte WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90598-149">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="90598-150">Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="90598-150">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the Oracle database.</span></span> <span data-ttu-id="90598-151">Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="90598-151">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="90598-152">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="90598-152">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span> <span data-ttu-id="90598-153">Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90598-153">You can specify the different binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="90598-154">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="90598-154">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
   3. <span data-ttu-id="90598-155">Haga clic en el **otros** pestaña y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="90598-155">Click the **Others** tab, and do one of the following:</span></span>  
  
      - <span data-ttu-id="90598-156">Seleccione **cuenta de usuario**y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="90598-156">Select **User account**, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="90598-157">Para conectar con las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="90598-157">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="90598-158">Para conectarse mediante la autenticación de Windows, escriba **/** en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="90598-158">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
      - <span data-ttu-id="90598-159">Seleccione **obtener credenciales de la aplicación afiliada** opción y especifique una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="90598-159">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
        <span data-ttu-id="90598-160">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, consulte [seguridad con el adaptador de base de datos de Oracle y BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="90598-160">For more information about security with respect to BizTalk Server, see [Security with the Oracle Database adapter and BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span></span>
  
        <span data-ttu-id="90598-161">Para volver a la **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90598-161">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="90598-162">Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="90598-162">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="90598-163">Si eligió **puerto de recepción unidireccional** en el paso 4, especifique una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="90598-163">If you chose **One-way Receive Port** in step 4, specify a receive pipeline.</span></span> <span data-ttu-id="90598-164">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="90598-164">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="90598-165">Si eligió **puerto de recepción de solicitud-respuesta** en el paso 4, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="90598-165">If you chose **Request Response Receive Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="90598-166">Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.</span><span class="sxs-lookup"><span data-stu-id="90598-166">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="90598-167">Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.</span><span class="sxs-lookup"><span data-stu-id="90598-167">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
12. <span data-ttu-id="90598-168">En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90598-168">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
13. <span data-ttu-id="90598-169">En el **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90598-169">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90598-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="90598-170">See Also</span></span>  
<span data-ttu-id="90598-171">[Configurar manualmente un enlace de puerto físico para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="90598-171">[Manually configure a physical port binding to the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md) </span></span>  
 [<span data-ttu-id="90598-172">Conectarse a la base de datos de Oracle mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="90598-172">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)