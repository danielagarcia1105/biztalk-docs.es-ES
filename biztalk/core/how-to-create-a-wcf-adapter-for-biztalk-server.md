---
title: Cómo crear un adaptador de WCF para BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ddaeb72-d263-4291-bd79-485fc736e6e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07c838f9c53f7416ee0fea0e4efe71c49f60404
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989797"
---
# <a name="how-to-create-a-wcf-adapter-for-biztalk-server"></a><span data-ttu-id="f4925-102">Cómo crear un adaptador de WCF para BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f4925-102">How to Create a WCF Adapter for BizTalk Server</span></span>
<span data-ttu-id="f4925-103">La creación de un adaptador de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] de BizTalk consta de tres partes.</span><span class="sxs-lookup"><span data-stu-id="f4925-103">There are three parts to creating a BizTalk [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] adapter.</span></span>  
  
- <span data-ttu-id="f4925-104">Cree un servicio Web [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] mediante el Asistente para publicación de Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4925-104">Create a [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web service using the BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Publishing Wizard.</span></span> <span data-ttu-id="f4925-105">Para obtener información sobre el uso de BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Asistente para publicación de servicio, consulte [publicar servicios WCF](../core/publishing-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4925-105">For information about using the BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Publishing Wizard, see [Publishing WCF Services](../core/publishing-wcf-services.md).</span></span>  
  
- <span data-ttu-id="f4925-106">Configure las ubicaciones y puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4925-106">Configure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive and send locations and ports by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="f4925-107">Para obtener un ejemplo de cómo hacerlo, consulte [cómo configurar la recepción y ubicaciones de envío y puertos para la intercepción de WCF de BAM](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md).</span><span class="sxs-lookup"><span data-stu-id="f4925-107">For an example of how to do this, see [How to Configure Receive and Send Locations and Ports for BAM WCF Interception](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md).</span></span>  
  
- <span data-ttu-id="f4925-108">Si aloja su solución en IIS, debe configurar el servicio web [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] usando el Administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="f4925-108">If you are hosting your solution in IIS, you must configure the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web service by using IIS Manager.</span></span>  
  
  -   <span data-ttu-id="f4925-109">Debe conceder permisos al usuario de grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f4925-109">You must grant permissions to the App pool user.</span></span> <span data-ttu-id="f4925-110">Para ello, consulte [consideraciones de seguridad para la suplantación de IIS](../core/security-considerations-for-iis-impersonation.md).</span><span class="sxs-lookup"><span data-stu-id="f4925-110">To do this, see [Security Considerations for IIS Impersonation](../core/security-considerations-for-iis-impersonation.md).</span></span>  
  
  -   <span data-ttu-id="f4925-111">Debe configurar la seguridad de directorios para su aplicación tal y como se describe en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f4925-111">You must set the directory security for your application as described in the following procedure.</span></span>  
  
## <a name="setting-the-directory-security"></a><span data-ttu-id="f4925-112">Configurar la seguridad de directorios</span><span class="sxs-lookup"><span data-stu-id="f4925-112">Setting the Directory Security</span></span>  
 <span data-ttu-id="f4925-113">Asegúrese de que Access Control para seguridad de directorios del servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] permite accesos anónimos. Esto facilitará el acceso a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4925-113">Ensure that the Directory Security Access Control for the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] service allows for anonymous access; this simplifies the application access.</span></span>  
  
 <span data-ttu-id="f4925-114">Por ejemplo, si el nombre de la aplicación es MyBizTalkService3 y dispone de MyBizTalkService3·en los sitios web predeterminados, puede seguir este procedimiento para configurar el control de acceso.</span><span class="sxs-lookup"><span data-stu-id="f4925-114">For example, if your application is named MyBizTalkService3 and you have a MyBizTalkService3 that is in Default Websites, you would follow this procedure to set the access control.</span></span>  
  
#### <a name="to-set-the-access-control-in-windows-server-2008"></a><span data-ttu-id="f4925-115">Procedimiento para establecer el control de acceso en Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="f4925-115">To set the access control in Windows Server 2008</span></span>  
  
1. <span data-ttu-id="f4925-116">Haga clic en **iniciar**, haga clic en **todos los programas**, expanda **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="f4925-116">Click **Start**, click **All Programs**, expand **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2. <span data-ttu-id="f4925-117">En la ventana del Administrador de Internet Information Services (IIS), expanda el nombre del servidor, **sitios**, expanda **Internet Information Services**y, a continuación, expanda **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="f4925-117">In the Internet Information Services (IIS) Manager window, expand your server name, expand **Sites**, expand **Internet Information Services**, and then expand **Default Web Site**.</span></span>  
  
3. <span data-ttu-id="f4925-118">Haga clic en **MyBizTalkService3**y, a continuación, haga clic en **Editar permisos**.</span><span class="sxs-lookup"><span data-stu-id="f4925-118">Right-click **MyBizTalkService3**, and then click **Edit Permissions**.</span></span>  
  
4. <span data-ttu-id="f4925-119">En el **seguridad** pestaña de la **MyBizTalkService3 Properties** cuadro de diálogo, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="f4925-119">On the **Security** tab of the **MyBizTalkService3 Properties** dialog box, click **Edit**.</span></span>  
  
5. <span data-ttu-id="f4925-120">En el **permisos de MyBizTalkService3** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="f4925-120">In the **Permissions for MyBizTalkService3** dialog box, click **Add**.</span></span>  
  
6. <span data-ttu-id="f4925-121">En el **Seleccionar usuarios, equipos o grupos** cuadro de diálogo, escriba `anonymous logon` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f4925-121">In the **Select Users, Computers, or Groups** dialog box, type `anonymous logon` and then click **OK**.</span></span>  
  
7. <span data-ttu-id="f4925-122">Seleccione **ANONYMOUS LOGON** en el **los nombres de usuario o grupo** sección, seleccione **lectura & ejecutar** en el **permisos de ANONYMOUS LOGON** sección y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f4925-122">Select **ANONYMOUS LOGON** in the **Group or user names** section, select **Read & execute** in the **Permissions for ANONYMOUS LOGON** section, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="f4925-123">Haga clic en **Aceptar** para cerrar el **MyBizTalkService3 Properties** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f4925-123">Click **OK** to close the **MyBizTalkService3 Properties** dialog box.</span></span>  
  
   <span data-ttu-id="f4925-124">Para confirmar que el servicio está configurado correctamente, haga clic en el servicio y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="f4925-124">To confirm that the service is configured correctly, right-click the service, and then click **Browse**.</span></span>  
  
   <span data-ttu-id="f4925-125">Si el servicio está configurado correctamente, verá una pantalla semejante a la que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="f4925-125">If the service is configured correctly, you will see a screen similar to the one below.</span></span>  
  
   <span data-ttu-id="f4925-126">![Pantalla de servicio BizTalkServiceInstance](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")</span><span class="sxs-lookup"><span data-stu-id="f4925-126">![BizTalkServiceInstance Service Screen](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4925-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4925-127">See Also</span></span>  
 [<span data-ttu-id="f4925-128">Configuración del adaptador de WCF para interceptar datos de BAM</span><span class="sxs-lookup"><span data-stu-id="f4925-128">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)