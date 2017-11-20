---
title: Configurar un puerto mediante el adaptador WCF-custom y el adaptador de Siebel en BizTalk | Documentos de Microsoft
description: "Crear envío WCF-custom y puertos de recepción para usar el adaptador de aplicaciones Siebel eBusiness en BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53c5ee07-36ae-474b-9241-8b53c9066ca1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 485bfaf7bd958528630e96a64ca0129a56ec330d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-siebel-adapter"></a><span data-ttu-id="ff9d1-103">Configurar un puerto mediante el adaptador WCF-custom y el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="ff9d1-103">Configure a port using the WCF-custom adapter and Siebel adapter</span></span>
<span data-ttu-id="ff9d1-104">Este tema proporciona instrucciones sobre cómo configurar WCF-Custom puertos de envío para realizar operaciones de salida en un sistema Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff9d1-104">This topic provides instructions on how to configure WCF-Custom send ports to perform outbound operations on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ff9d1-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ff9d1-105">Prerequisites</span></span>  
<span data-ttu-id="ff9d1-106">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="ff9d1-107">Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span><span class="sxs-lookup"><span data-stu-id="ff9d1-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploying-adapters-for-sending-messages-to-a-siebel-system"></a><span data-ttu-id="ff9d1-108">Implementación de adaptadores para enviar mensajes a un sistema Siebel</span><span class="sxs-lookup"><span data-stu-id="ff9d1-108">Deploying Adapters for Sending Messages to a Siebel System</span></span>  
 <span data-ttu-id="ff9d1-109">Realice los pasos siguientes para configurar un puerto de envío WCF-Custom para enviar mensajes a un sistema Siebel con el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-109">Perform the following steps to configure a WCF-Custom send port for sending messages to a Siebel system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 
1.  <span data-ttu-id="ff9d1-110">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="ff9d1-111">En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="ff9d1-112">Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff9d1-112">Expand the application under which you wish to deploy the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="ff9d1-113">Haga clic en **puertos de envío**, seleccione **nuevo**y seleccione un tipo de puerto que desea configurar según el modo de comunicación entre el servidor BizTalk Server y el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-113">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the Siebel system.</span></span>  
  
5.  <span data-ttu-id="ff9d1-114">En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="ff9d1-115">Desde el **tipo** lista desplegable, seleccione **WCF-Custom** y haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-115">From the **Type** drop-down list, select **WCF-Custom** and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="ff9d1-116">En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff9d1-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ff9d1-117">Haga clic en el **General** pestaña y en la **dirección (URI)** campo para especificar el URI de conexión para conectarse a un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-117">Click the **General** tab and in the **Address (URI)** field specify the connection URI to connect to a Siebel system.</span></span> <span data-ttu-id="ff9d1-118">Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema Siebel URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="ff9d1-118">For more information about the connection URI, see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="ff9d1-119">En el **General** ficha la **acción** texto, escriba la acción para la operación.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-119">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="ff9d1-120">Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) para obtener una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-120">See [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) for a list of actions for each operation.</span></span> <span data-ttu-id="ff9d1-121">Por ejemplo, la acción que se va a invocar la operación de inserción en el componente de negocio de la cuenta es:</span><span class="sxs-lookup"><span data-stu-id="ff9d1-121">For example, the action to invoke the Insert operation on the Account business component is:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    3.  <span data-ttu-id="ff9d1-122">Haga clic en el **enlace** ficha desde y hacia el **BindingType** lista desplegable, seleccione **siebelBinding**.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-122">Click the **Binding** tab and from the **Binding Type** drop-down list, select **siebelBinding**.</span></span> <span data-ttu-id="ff9d1-123">También puede especificar las propiedades de enlace diferente expuestas por la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff9d1-123">You can also specify the different binding properties exposed by the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="ff9d1-124">Para obtener más información, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ff9d1-124">For more information, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="ff9d1-125">Haga clic en el **credenciales** ficha y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ff9d1-125">Click the **Credentials** tab and do one of the following:</span></span>  
  
        -   <span data-ttu-id="ff9d1-126">Seleccione el **no use Single Sign-On** opción y especifique el nombre de usuario y contraseña para conectarse a un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-126">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  
  
        -   <span data-ttu-id="ff9d1-127">Seleccione el **Use Single Sign-On** opción y especifique una aplicación afiliada de ESSO.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-127">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  
  
         <span data-ttu-id="ff9d1-128">Para obtener más información acerca de la seguridad con respecto a BizTalk Server, vea [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="ff9d1-128">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="ff9d1-129">Para volver a la **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-129">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="ff9d1-130">Desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-130">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="ff9d1-131">Si ha elegido el puerto de envío unidireccional estático en el paso 4, especifique una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-131">If you chose Static One-Way Send Port in step 4, specify a send pipeline.</span></span> <span data-ttu-id="ff9d1-132">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-132">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="ff9d1-133">Si ha elegido puerto de petición-respuesta estático en el paso 4, especifique el envío y las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-133">If you chose Static Solicit-Response Port in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="ff9d1-134">Desde el **canalización de envío** lista desplegable, seleccione la canalización XMLTransmit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-134">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="ff9d1-135">Desde el **canalización de recepción** lista desplegable, seleccione la canalización XMLReceive correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-135">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="ff9d1-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff9d1-136">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9d1-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff9d1-137">See Also</span></span>  
[<span data-ttu-id="ff9d1-138">Configurar manualmente un enlace de puerto físico para el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="ff9d1-138">Manually configure a physical port binding to the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)