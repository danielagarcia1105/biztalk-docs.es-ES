---
title: Configurar un puerto mediante el adaptador WCF-custom y el adaptador de la base de datos de Oracle | Documentos de Microsoft
description: Crear envío WCF-custom y puertos de recepción para usar el adaptador de base de datos de Oracle en el servidor BizTalk Server
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
ms.openlocfilehash: a7831ab57e7cae268aa1f47f380c69ef854b092b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215860"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter"></a><span data-ttu-id="2ffaf-103">Configurar un puerto mediante el adaptador WCF-custom y el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="2ffaf-103">Configure a port using the WCF-custom adapter and Oracle Database adapter</span></span>
<span data-ttu-id="2ffaf-104">Cómo configurar el envío de WCF-Custom y puertos de recepción para realizar operaciones de entrada y salidas en la base de datos de Oracle mediante el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ffaf-104">How to configure WCF-Custom send and receive ports to perform outbound and inbound operations on the Oracle database using the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2ffaf-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2ffaf-105">Prerequisites</span></span>  
<span data-ttu-id="2ffaf-106">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="2ffaf-107">Vea [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) para obtener instrucciones de permisos.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-107">See [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) for permissions guidance.</span></span>
  
## <a name="deploy-adapters-for-sending-messages-to-an-oracle-database"></a><span data-ttu-id="2ffaf-108">Implementar los adaptadores para enviar mensajes a una base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="2ffaf-108">Deploy adapters for sending messages to an Oracle database</span></span>  
  
1.  <span data-ttu-id="2ffaf-109">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="2ffaf-110">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-110">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="2ffaf-111">Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ffaf-111">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="2ffaf-112">Haga clic en **puertos de envío**, seleccione **New**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-112">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the Oracle database.</span></span>  
  
5.  <span data-ttu-id="2ffaf-113">En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-113">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="2ffaf-114">Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-114">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="2ffaf-115">En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ffaf-115">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="2ffaf-116">Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-116">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the Oracle database.</span></span> <span data-ttu-id="2ffaf-117">Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="2ffaf-117">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="2ffaf-118">En el **General** ficha la **acción** texto, escriba la acción para la operación.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-118">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="2ffaf-119">Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) para obtener una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-119">See [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) for a list of actions for each operation.</span></span> <span data-ttu-id="2ffaf-120">Por ejemplo, la acción que se va a invocar la operación de inserción de una tabla de empleados en el esquema de recursos humanos en una base de datos de Oracle es:</span><span class="sxs-lookup"><span data-stu-id="2ffaf-120">For example, the action to invoke the Insert operation an EMPLOYEE table under the HR schema in an Oracle database is:</span></span>  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
        ```  
  
    3.  <span data-ttu-id="2ffaf-121">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-121">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span> <span data-ttu-id="2ffaf-122">Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ffaf-122">You can specify the different binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="2ffaf-123">Para obtener más información acerca de las propiedades de enlace, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2ffaf-123">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="2ffaf-124">Haga clic en el **credenciales** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2ffaf-124">Click the **Credentials** tab and do one of the following:</span></span>  
  
        -   <span data-ttu-id="2ffaf-125">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-125">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
            -   <span data-ttu-id="2ffaf-126">Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-126">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
            -   <span data-ttu-id="2ffaf-127">Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-127">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
        -   <span data-ttu-id="2ffaf-128">Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de SSO.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-128">Select the **Use Single Sign-On** option, and specify an affiliate SSO application.</span></span>  
  
         <span data-ttu-id="2ffaf-129">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de la base de datos de Oracle y BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="2ffaf-129">For more information about security with respect to BizTalk Server, see [Security with the Oracle Database adapter and BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span></span>  
  
         <span data-ttu-id="2ffaf-130">Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-130">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="2ffaf-131">Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-131">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="2ffaf-132">Si ha elegido **puerto de envío unidireccional estático** en el paso 4, especifique una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-132">If you chose **Static One-Way Send Port** in step 4, specify a send pipeline.</span></span> <span data-ttu-id="2ffaf-133">Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-133">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="2ffaf-134">Si ha elegido **puerto de petición-respuesta estático** en el paso 4, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-134">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="2ffaf-135">Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-135">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="2ffaf-136">Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-136">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
11. <span data-ttu-id="2ffaf-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-137">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-for-receiving-messages-from-an-oracle-database"></a><span data-ttu-id="2ffaf-138">Implementar los adaptadores para recibir mensajes desde una base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="2ffaf-138">Deploy adapters for receiving messages from an Oracle database</span></span>  
  
1.  <span data-ttu-id="2ffaf-139">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-139">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="2ffaf-140">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-140">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="2ffaf-141">Expanda la aplicación en la que desea implementar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ffaf-141">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="2ffaf-142">Haga clic en **puertos de recepción**, seleccione **New**y haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, en función de la modo de comunicación entre el servidor BizTalk Server y la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-142">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between BizTalk Server and the Oracle database.</span></span>  
  
5.  <span data-ttu-id="2ffaf-143">En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-143">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="2ffaf-144">En el **ubicaciones de recepción** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-144">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="2ffaf-145">El **propiedades de la ubicación de recepción** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-145">The **Receive Location Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="2ffaf-146">En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ffaf-146">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="2ffaf-147">Especifique un nombre para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-147">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="2ffaf-148">Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-148">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="2ffaf-149">En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ffaf-149">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="2ffaf-150">Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-150">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the Oracle database.</span></span> <span data-ttu-id="2ffaf-151">Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="2ffaf-151">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="2ffaf-152">Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-152">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span> <span data-ttu-id="2ffaf-153">Puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ffaf-153">You can specify the different binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="2ffaf-154">Para obtener más información acerca de las propiedades de enlace, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2ffaf-154">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
    3.  <span data-ttu-id="2ffaf-155">Haga clic en el **otros** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2ffaf-155">Click the **Others** tab, and do one of the following:</span></span>  
  
        -   <span data-ttu-id="2ffaf-156">Seleccione **cuenta de usuario**y especifique el nombre de usuario y contraseña para conectarse a una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-156">Select **User account**, and specify the user name and password to connect to an Oracle database.</span></span>  
  
            -   <span data-ttu-id="2ffaf-157">Para conectarse utilizando las credenciales de la base de datos de Oracle, escriba las credenciales de base de datos en el **nombre de usuario** y **contraseña** cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-157">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
            -   <span data-ttu-id="2ffaf-158">Para conectarse mediante la autenticación de Windows, escriba  **/**  en el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-158">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
        -   <span data-ttu-id="2ffaf-159">Seleccione **obtener credenciales de aplicación afiliada** opción y especifique una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-159">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
         <span data-ttu-id="2ffaf-160">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de la base de datos de Oracle y BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="2ffaf-160">For more information about security with respect to BizTalk Server, see [Security with the Oracle Database adapter and BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span></span>
  
         <span data-ttu-id="2ffaf-161">Para volver a la **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-161">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="2ffaf-162">Desde el **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-162">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="2ffaf-163">Si ha elegido **puerto de recepción unidireccional** en el paso 4, especifique una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-163">If you chose **One-way Receive Port** in step 4, specify a receive pipeline.</span></span> <span data-ttu-id="2ffaf-164">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-164">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="2ffaf-165">Si ha elegido **puerto de recepción de solicitud-respuesta** en el paso 4, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-165">If you chose **Request Response Receive Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="2ffaf-166">Desde el **canalización de recepción** lista desplegable, seleccione la canalización que corresponde a XMLReceive.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-166">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="2ffaf-167">Desde el **canalización de envío** lista desplegable, seleccione la canalización que corresponde a XMLTransmit.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-167">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
12. <span data-ttu-id="2ffaf-168">En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-168">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
13. <span data-ttu-id="2ffaf-169">En el **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-169">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ffaf-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ffaf-170">See Also</span></span>  
<span data-ttu-id="2ffaf-171">[Configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="2ffaf-171">[Manually configure a physical port binding to the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md) </span></span>  
 [<span data-ttu-id="2ffaf-172">Conectarse a la base de datos de Oracle mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="2ffaf-172">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)