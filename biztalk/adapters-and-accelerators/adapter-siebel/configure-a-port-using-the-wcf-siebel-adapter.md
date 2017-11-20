---
title: Configurar un puerto mediante el adaptador de WCF-Siebel | Documentos de Microsoft
description: "Crear puertos de envío WCF-Siebel para usar el adaptador de aplicaciones Siebel eBusiness en BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6314104-c742-440c-b530-b5a82295353a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486e33b6c8f61a315548a84f145dc45824300710
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-port-using-the-wcf-siebel-adapter"></a><span data-ttu-id="7b46c-103">Configurar un puerto mediante el adaptador de WCF-Siebel</span><span class="sxs-lookup"><span data-stu-id="7b46c-103">Configure a port using the WCF-Siebel adapter</span></span>
<span data-ttu-id="7b46c-104">Cómo configurar puertos de envío WCF-Siebel para llevar a cabo las operaciones salientes en un sistema Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b46c-104">How to configure WCF-Siebel send ports to perform outbound operations on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7b46c-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7b46c-105">Prerequisites</span></span>  
<span data-ttu-id="7b46c-106">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7b46c-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="7b46c-107">Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span><span class="sxs-lookup"><span data-stu-id="7b46c-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-for-sending-messages-to-a-siebel-system"></a><span data-ttu-id="7b46c-108">Implementar los adaptadores para enviar mensajes a un sistema Siebel</span><span class="sxs-lookup"><span data-stu-id="7b46c-108">Deploy adapters for sending messages to a Siebel system</span></span>  
 <span data-ttu-id="7b46c-109">Realice los pasos siguientes para configurar un puerto de envío WCF-Siebel para enviar mensajes a un sistema Siebel con el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="7b46c-109">Perform the following steps to configure a WCF-Siebel send port for sending messages to a Siebel system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="7b46c-110">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="7b46c-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="7b46c-111">Agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="7b46c-111">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7b46c-112">Para obtener instrucciones, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="7b46c-112">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="7b46c-113">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="7b46c-113">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="7b46c-114">Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b46c-114">Expand the application under which you wish to deploy the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
5.  <span data-ttu-id="7b46c-115">Haga clic en **puertos de envío**, seleccione **nuevo**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre el servidor BizTalk Server y el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="7b46c-115">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the Siebel system.</span></span>  
  
6.  <span data-ttu-id="7b46c-116">En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7b46c-116">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7.  <span data-ttu-id="7b46c-117">Desde el **tipo** lista desplegable, seleccione el WCF-Siebel adaptador que agregó anteriormente y haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7b46c-117">From the **Type** drop-down list, select the WCF-Siebel adapter you added earlier and click **Configure**.</span></span>  
  
8.  <span data-ttu-id="7b46c-118">En el cuadro de diálogo Propiedades de transporte, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b46c-118">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="7b46c-119">Haga clic en el **General** , haga clic en el **configurar** botón y proporcione valores para los parámetros de conexión.</span><span class="sxs-lookup"><span data-stu-id="7b46c-119">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="7b46c-120">Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema Siebel URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="7b46c-120">For more information about the connection URI, see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="7b46c-121">En el **General** ficha la **acción** texto, escriba la acción para la operación.</span><span class="sxs-lookup"><span data-stu-id="7b46c-121">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="7b46c-122">Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) para obtener una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="7b46c-122">See [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) for a list of actions for each operation.</span></span> <span data-ttu-id="7b46c-123">Por ejemplo, la acción que se va a invocar la operación de inserción en el componente de negocio de la cuenta es:</span><span class="sxs-lookup"><span data-stu-id="7b46c-123">For example, the action to invoke the Insert operation on the Account business component is:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    3.  <span data-ttu-id="7b46c-124">Haga clic en el **enlace** pestaña y especificar valores para las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="7b46c-124">Click the **Binding** tab and specify values for the binding properties.</span></span> <span data-ttu-id="7b46c-125">Para obtener más información, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7b46c-125">For more information, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="7b46c-126">Haga clic en el **credenciales** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7b46c-126">Click the **Credentials** tab and do one of the following:</span></span>  
  
        -   <span data-ttu-id="7b46c-127">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="7b46c-127">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  
  
        -   <span data-ttu-id="7b46c-128">Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de ESSO.</span><span class="sxs-lookup"><span data-stu-id="7b46c-128">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  
  
         <span data-ttu-id="7b46c-129">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="7b46c-129">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="7b46c-130">Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b46c-130">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="7b46c-131">Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="7b46c-131">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="7b46c-132">Si ha elegido el puerto de envío unidireccional estático en el paso 5, especifique una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="7b46c-132">If you chose Static One-Way Send Port in step 5, specify a send pipeline.</span></span> <span data-ttu-id="7b46c-133">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7b46c-133">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="7b46c-134">Si ha elegido puerto de petición-respuesta estático en el paso 5, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="7b46c-134">If you chose Static Solicit-Response Port in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="7b46c-135">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7b46c-135">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="7b46c-136">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7b46c-136">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="7b46c-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b46c-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b46c-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b46c-138">See Also</span></span>  
[<span data-ttu-id="7b46c-139">Configurar manualmente un enlace de puerto físico para el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="7b46c-139">Manually configure a physical port binding to the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)