---
title: 'Tutorial: Módulo 1: enviar y recibir mensajes con Windows SharePoint Services adaptador | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, creating sites
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, receiving messages
- security, Windows SharePoint Services
- creating, Windows SharePoint Services site
- Windows SharePoint Services, security
- Windows SharePoint Services, document libraries
- Windows SharePoint Services adapters, security
- Windows SharePoint Services
- Windows SharePoint Services adapter tutorials, sending messages
ms.assetid: 6494aef5-bb1d-4a41-8186-1d49625a1013
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8e83297233c4f8ac51ad90f488437a6c259691a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010509"
---
# <a name="walkthrough-module-1---sending-and-receiving-messages-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="20ebc-102">Tutorial: Módulo 1 – enviar y recibir mensajes con el adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="20ebc-102">Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="20ebc-103">En este tutorial se muestra cómo configurar Windows SharePoint Services y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que pueda enviar y recibir mensajes mediante el adaptador de Windows SharePoint Services y el enrutamiento basado en contenido (CBR).</span><span class="sxs-lookup"><span data-stu-id="20ebc-103">This walkthrough shows you how to configure Windows SharePoint Services and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] so you can send and receive a message using the Windows SharePoint Services Adapter and content-based routing (CBR).</span></span> <span data-ttu-id="20ebc-104">El enrutamiento por contenidos elimina la necesidad de suscribir mensajes para los mensajes enlazados de forma determinista a puertos específicos.</span><span class="sxs-lookup"><span data-stu-id="20ebc-104">Content-based routing eliminates the need for message subscription for messages that are deterministically bound to specific ports.</span></span> <span data-ttu-id="20ebc-105">Asimismo, proporciona flexibilidad adicional para los usuarios que deseen enrutar los mensajes según las propiedades del sobre o simplemente según las propiedades de configuración del puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="20ebc-105">It also provides additional flexibility for users who want to route messages based on envelope properties or simply based on receive port configuration properties.</span></span> <span data-ttu-id="20ebc-106">Para obtener una introducción al adaptador de Windows SharePoint Services, vea [¿qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="20ebc-106">For an introduction to the Windows SharePoint Services adapter, see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="20ebc-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="20ebc-107">Prerequisites</span></span>  
 <span data-ttu-id="20ebc-108">A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:</span><span class="sxs-lookup"><span data-stu-id="20ebc-108">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="20ebc-109">Debe tener una implementación de servidor único con una instalación completa de BizTalk Server que se ejecutan en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20ebc-109">You must have a single-server deployment with a complete installation of BizTalk Server running on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span>  
  
 <span data-ttu-id="20ebc-110">Para obtener información acerca de cómo utilizar el adaptador de Windows SharePoint Services en una implementación multiservidor, vea [configurar e implementar el adaptador de Windows SharePoint Services](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="20ebc-110">For information about using the Windows SharePoint Services adapter in a multiserver deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="configure-windows-sharepoint-services"></a><span data-ttu-id="20ebc-111">Configurar Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="20ebc-111">Configure Windows SharePoint Services</span></span>  
 <span data-ttu-id="20ebc-112">En este procedimiento, se creará un sitio Web de nivel superior de SharePoint que contiene tres bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="20ebc-112">In this procedure you create a SharePoint top-level Web site that contains three document libraries.</span></span> <span data-ttu-id="20ebc-113">El adaptador de Windows SharePoint Services utiliza estas bibliotecas para trasladar un mensaje a una biblioteca de destino desde una biblioteca de origen.</span><span class="sxs-lookup"><span data-stu-id="20ebc-113">The Windows SharePoint Services adapter uses these libraries to move a message from a source library to a destination library.</span></span> <span data-ttu-id="20ebc-114">Este mensaje también se archiva en una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="20ebc-114">This message is also archived in a document library.</span></span> <span data-ttu-id="20ebc-115">Este procedimiento resulta necesario para proporcionar el sitio de Windows Sharepoint Services al que tiene acceso el adaptador de Windows Sharepoint Services en este tutorial, así como para definir derechos de usuario que hagan posible el acceso a este sitio.</span><span class="sxs-lookup"><span data-stu-id="20ebc-115">This procedure must be done to provide the Windows Sharepoint Services site that is accessed by the Windows Sharepoint Services adapter in this walkthrough and to set user rights to enable access to this site.</span></span>  
  
#### <a name="create-a-windows-sharepoint-services-site"></a><span data-ttu-id="20ebc-116">Crear un sitio de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="20ebc-116">Create a Windows SharePoint Services site</span></span>  
  
1.  <span data-ttu-id="20ebc-117">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="20ebc-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration.**</span></span>  
  
2.  <span data-ttu-id="20ebc-118">En **configuración del servidor Virtual**, haga clic en **crear un sitio Web de nivel superior**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-118">Under **Virtual Server Configuration**, click **Create a top-level Web site**.</span></span>  
  
3.  <span data-ttu-id="20ebc-119">En **lista de servidores virtuales**, seleccione el sitio Web que ha instalado el adaptador de Windows SharePoint Services en.</span><span class="sxs-lookup"><span data-stu-id="20ebc-119">Under **Virtual Server List**, select the Web site that you installed the Windows SharePoint Services Adapter on.</span></span> <span data-ttu-id="20ebc-120">Por ejemplo, `Default Web Site`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-120">For example, `Default Web Site`.</span></span>  
  
4.  <span data-ttu-id="20ebc-121">En el **dirección del sitio Web** sección, en la **nombre de dirección URL** , escriba `WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-121">In the **Web Site Address** section, in the **URL name** field, type `WSSAdapterWalkthrough`.</span></span>  
  
5.  <span data-ttu-id="20ebc-122">En el **propietario de la colección de sitios** sección, en la **campo de nombre de usuario,** escriba un nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="20ebc-122">In the **Site Collection Owner** section, in the **User name field,** type a user name.</span></span> <span data-ttu-id="20ebc-123">El usuario será el propietario del sitio web y no necesita permisos especiales para usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20ebc-123">This user will be the owner for the Web site and does not need special permissions in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
6.  <span data-ttu-id="20ebc-124">En el **propietario de la colección de sitios** sección, en la **correo electrónico** , escriba una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="20ebc-124">In the **Site Collection Owner** section, in the **E-mail** field, type in an e-mail address.</span></span>  
  
7.  <span data-ttu-id="20ebc-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-125">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="20ebc-126">En el **sitio de nivel superior correctamente creado** página, haga clic en nuevo sitio Web de nivel superior que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="20ebc-126">On the **Top-Level Site Successfully Created** page, click the new top-level Web site you just created.</span></span> <span data-ttu-id="20ebc-127">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-127">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
9. <span data-ttu-id="20ebc-128">Seleccione el **equipo sitio** plantilla de la lista de plantillas y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-128">Select the **Team Site** template from the list of templates, and then click **OK**.</span></span> <span data-ttu-id="20ebc-129">De este modo se abre la página principal del sitio Web del equipo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-129">This will open the Team Web Site Home page.</span></span>  
  
#### <a name="create-a-source-document-library"></a><span data-ttu-id="20ebc-130">Crear una biblioteca de documentos de “origen”</span><span class="sxs-lookup"><span data-stu-id="20ebc-130">Create a "Source" document library</span></span>  
  
1.  <span data-ttu-id="20ebc-131">En la página principal del sitio Web del equipo, en la barra de navegación superior, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-131">On the Team Web Site Home page, on the top navigation bar, click **Create**.</span></span>  
  
2.  <span data-ttu-id="20ebc-132">En **las bibliotecas de documentos**, haga clic en **biblioteca de documentos**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-132">Under **Document Libraries**, click **Document Library**.</span></span>  
  
3.  <span data-ttu-id="20ebc-133">En el **nombre y una descripción** sección, en la **campo nombre,** tipo `Source`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-133">In the **Name and Description** section, in the **Name field,** type `Source`.</span></span>  
  
4.  <span data-ttu-id="20ebc-134">En el **navegación** sección, seleccione **Sí** para mostrar esta biblioteca de formularios en la barra Inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="20ebc-134">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
5.  <span data-ttu-id="20ebc-135">En el **plantilla de documento** sección, en la **plantilla de documento** lista desplegable, seleccione `None`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-135">In the **Document Template** section, in the **Document Template** drop-down list, select `None`.</span></span>  
  
6.  <span data-ttu-id="20ebc-136">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-136">Click **Create**.</span></span> <span data-ttu-id="20ebc-137">Se creará la biblioteca de documentos y tendrá lugar una redirección a la biblioteca vacía.</span><span class="sxs-lookup"><span data-stu-id="20ebc-137">The document library will be created and you will be redirected to the empty library.</span></span>  
  
#### <a name="create-a-destination-document-library"></a><span data-ttu-id="20ebc-138">Crear una biblioteca de documentos de "destino"</span><span class="sxs-lookup"><span data-stu-id="20ebc-138">Create a "Destination" document library</span></span>  
  
1.  <span data-ttu-id="20ebc-139">En la página principal del sitio Web del equipo, en la barra de navegación superior, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-139">On the Team Web Site Home page, on the top navigation bar, click **Create**.</span></span>  
  
2.  <span data-ttu-id="20ebc-140">En **las bibliotecas de documentos**, haga clic en **biblioteca de documentos**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-140">Under **Document Libraries**, click **Document Library**.</span></span>  
  
3.  <span data-ttu-id="20ebc-141">En el **nombre y una descripción** sección, en la **campo nombre**, tipo `Destination`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-141">In the **Name and Description** section, in the **Name field**, type `Destination`.</span></span>  
  
4.  <span data-ttu-id="20ebc-142">En el **navegación** sección, seleccione **Sí** para mostrar esta biblioteca de formularios en la barra Inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="20ebc-142">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
5.  <span data-ttu-id="20ebc-143">En el **plantilla de documento** sección, en la **plantilla de documento** lista desplegable, seleccione `None`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-143">In the **Document Template** section, in the **Document Template** drop-down list, select `None`.</span></span>  
  
6.  <span data-ttu-id="20ebc-144">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-144">Click **Create**.</span></span> <span data-ttu-id="20ebc-145">Se creará la biblioteca de documentos y tendrá lugar una redirección a la biblioteca vacía.</span><span class="sxs-lookup"><span data-stu-id="20ebc-145">The document library will be created and you will be redirected to the empty library.</span></span>  
  
#### <a name="create-an-archive-document-library"></a><span data-ttu-id="20ebc-146">Crear una biblioteca de documentos de "archivo"</span><span class="sxs-lookup"><span data-stu-id="20ebc-146">Create an "Archive" document library</span></span>  
  
1.  <span data-ttu-id="20ebc-147">En la página principal del sitio Web del equipo, en la barra de navegación superior, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-147">On the Team Web Site Home page, on the top navigation bar, click **Create**.</span></span>  
  
2.  <span data-ttu-id="20ebc-148">En **las bibliotecas de documentos**, haga clic en **biblioteca de documentos**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-148">Under **Document Libraries**, click **Document Library**.</span></span>  
  
3.  <span data-ttu-id="20ebc-149">En el **nombre** y sección de descripción, en la **campo nombre**, tipo `Archive`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-149">In the **Name** and Description section, in the **Name field**, type `Archive`.</span></span>  
  
4.  <span data-ttu-id="20ebc-150">En el **navegación** sección, seleccione **Sí** para mostrar esta biblioteca de formularios en la barra Inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="20ebc-150">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
5.  <span data-ttu-id="20ebc-151">En el **plantilla de documento** sección, en la **plantilla de documento** lista desplegable, seleccione `None`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-151">In the **Document Template** section, in the **Document Template** drop-down list, select `None`.</span></span>  
  
6.  <span data-ttu-id="20ebc-152">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-152">Click **Create**.</span></span> <span data-ttu-id="20ebc-153">Se creará la biblioteca de documentos y tendrá lugar una redirección a la biblioteca vacía.</span><span class="sxs-lookup"><span data-stu-id="20ebc-153">The document library will be created and you will be redirected to the empty library.</span></span>  
  
7.  <span data-ttu-id="20ebc-154">Cierre el sitio web de `WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-154">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
8.  <span data-ttu-id="20ebc-155">Cerrar la **Administración Central de SharePoint** sitio Web.</span><span class="sxs-lookup"><span data-stu-id="20ebc-155">Close the **SharePoint Central Administration** Web site.</span></span>  
  
#### <a name="configure-windows-security"></a><span data-ttu-id="20ebc-156">Configurar seguridad de Windows</span><span class="sxs-lookup"><span data-stu-id="20ebc-156">Configure Windows security</span></span>  
  
1.  <span data-ttu-id="20ebc-157">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-157">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="20ebc-158">En el árbol de consola, expanda **usuarios y grupos locales**y, a continuación, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-158">In the console tree, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
3.  <span data-ttu-id="20ebc-159">Haga clic en el **Hosts habilitados de SharePoint** grupo, haga clic en **agregar al grupo**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-159">Right-click the **SharePoint Enabled Hosts** group, click **Add to Group**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="20ebc-160">En el **cuadro de diálogo Seleccionar usuarios, equipos o grupos**, en **escriba los nombres de objeto para seleccionar**, escriba el nombre de la cuenta que configuró la instancia de Host de BizTalk Server para ejecutarse en y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-160">In the **Select Users, Computers, or Groups dialog box**, under **Enter the object names to select**, type the name of the account that you configured the BizTalk Server Host Instance to run under, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="20ebc-161">En el árbol de consola, expanda **servicios y aplicaciones**y, a continuación, haga clic en **Services**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-161">In the console tree, expand **Services and Applications**, and then click **Services**.</span></span>  
  
6.  <span data-ttu-id="20ebc-162">Haga clic en **servicio de BizTalk grupo: < BizTalk_Host_Name >** y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-162">Right-click **BizTalk Service BizTalk Group: <BizTalk_Host_Name>**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20ebc-163"><BizTalk_Host_Name> es el nombre del host.</span><span class="sxs-lookup"><span data-stu-id="20ebc-163"><BizTalk_Host_Name> is the name of your host.</span></span> <span data-ttu-id="20ebc-164">De forma predeterminada, es `BizTalkServerApplication`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-164">By Default, this is `BizTalkServerApplication`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20ebc-165">La suscripción no tiene ningún efecto hasta que se reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="20ebc-165">Membership does not take effect until the service is restarted.</span></span>  
  
7.  <span data-ttu-id="20ebc-166">Cerrar **administración de equipos**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-166">Close **Computer Management**.</span></span>  
  
#### <a name="configure-sharepoint-security"></a><span data-ttu-id="20ebc-167">Configurar seguridad de SharePoint</span><span class="sxs-lookup"><span data-stu-id="20ebc-167">Configure SharePoint security</span></span>  
  
1.  <span data-ttu-id="20ebc-168">Abra un explorador web y vaya a la dirección URL del sitio creado.</span><span class="sxs-lookup"><span data-stu-id="20ebc-168">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="20ebc-169">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-169">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="20ebc-170">En la página principal del sitio Web del equipo, en la barra de navegación superior, haga clic en **configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-170">On the Team Web Site Home page, on the top navigation bar, click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="20ebc-171">En **administración**, haga clic en **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-171">Under **Administration**, click **Manage users**.</span></span>  
  
4.  <span data-ttu-id="20ebc-172">Haga clic en **Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-172">Click **Add Users**.</span></span>  
  
5.  <span data-ttu-id="20ebc-173">En **paso 1: elegir usuarios**, escriba el nombre de la cuenta que el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instancia de Host se ejecuta bajo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-173">In **Step 1: Choose Users**, type the name of the account that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Host Instance is running under.</span></span>  
  
6.  <span data-ttu-id="20ebc-174">En **paso 2: elegir grupos de sitio**, seleccione la **lector** y **colaborador** casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="20ebc-174">In **Step 2: Choose Site Groups**, select the **Reader** and **Contributor** check boxes.</span></span>  
  
7.  <span data-ttu-id="20ebc-175">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-175">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="20ebc-176">Desactive el **enviar el correo electrónico siguiente para informar a los usuarios ahora que han sido agregados** casilla de verificación y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-176">Clear the **Send the following e-mail to let these users now they've been added** check box, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="20ebc-177">Cierre el sitio web de `WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-177">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
## <a name="create-and-configure-the-biztalk-server-ports"></a><span data-ttu-id="20ebc-178">Crear y configurar los puertos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="20ebc-178">Create and configure the BizTalk Server ports</span></span>  
 <span data-ttu-id="20ebc-179">En este procedimiento se crearán y configurarán los puertos de recepción, las ubicaciones de recepción y los puertos de envío de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el adaptador de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="20ebc-179">In this procedure you will create and configure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive ports, receive locations, and send ports for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="20ebc-180">Estos puertos son puntos de entrada y salida de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para documentos que recibe y envía el adaptador de Windows Sharepoint Services.</span><span class="sxs-lookup"><span data-stu-id="20ebc-180">These ports are points of entry into and out of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for documents received and sent by the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-the-receive-port"></a><span data-ttu-id="20ebc-181">Crear el puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="20ebc-181">Create the receive port</span></span>  
  
1.  <span data-ttu-id="20ebc-182">Haga clic en **iniciar**, **todos los programas**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="20ebc-182">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="20ebc-183">Expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**, haga clic en **depuertosderecepción**, haga clic en **New**y, a continuación, haga clic en **puerto de recepción unidireccional...**</span><span class="sxs-lookup"><span data-stu-id="20ebc-183">Expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, right-click **Receive Ports**, click **New**, and then click **One-way Receive Port…**</span></span>  
  
3.  <span data-ttu-id="20ebc-184">En el **propiedades de puerto de recepción** cuadro de diálogo **General**, tipo `FromSource` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-184">In the **Receive Port Properties** dialog box, under **General**, type `FromSource` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="20ebc-185">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-185">Click **OK**.</span></span>  
  
#### <a name="create-the-receive-location"></a><span data-ttu-id="20ebc-186">Crear la ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="20ebc-186">Create the receive location</span></span>  
  
1.  <span data-ttu-id="20ebc-187">En el **consola de administración de BizTalk**, haga clic en el **ubicaciones de recepción** nodo, haga clic en **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-187">In the **BizTalk Administration Console**, right-click the **Receive Locations** node, click **New**, and then click **One-way Receive Location**.</span></span>  
  
2.  <span data-ttu-id="20ebc-188">En el **seleccionar un puerto de recepción** cuadro de diálogo, seleccione `FromSource`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-188">In the **Select a Receive Port** dialog box, select `FromSource`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="20ebc-189">En el **propiedades de la ubicación de recepción** cuadro de diálogo **General**, tipo `SourceLocation` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-189">In the **Receive Location Properties** dialog box, under **General**, type `SourceLocation` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="20ebc-190">En el **transporte** sección, en la **tipo** lista desplegable, seleccione `Windows``SharePoint``Services`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-190">In the **Transport** section, in the **Type** drop-down list, select `Windows``SharePoint``Services`.</span></span>  
  
5.  <span data-ttu-id="20ebc-191">Haga clic en **configurar** para configurar las propiedades de adaptador de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="20ebc-191">Click **Configure** to configure the Windows SharePoint Services adapter properties.</span></span>  
  
6.  <span data-ttu-id="20ebc-192">En el **adaptador de puerto del servicio Web** propiedad, escriba el número de puerto del servidor virtual donde se instaló el servicio Web del adaptador de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="20ebc-192">In the **Adapter Web Service Port** property, type the port number of the virtual server where the Windows SharePoint Services adapter Web service was installed.</span></span> <span data-ttu-id="20ebc-193">De forma predeterminada, éste es el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="20ebc-193">By default, this is port 80.</span></span>  
  
7.  <span data-ttu-id="20ebc-194">Tipo de `Archive` en el **ubicación de archivado** propiedad.</span><span class="sxs-lookup"><span data-stu-id="20ebc-194">Type `Archive` in the **Archive Location** property.</span></span>  
  
8.  <span data-ttu-id="20ebc-195">Tipo de `10` en el **intervalo de sondeo** propiedad.</span><span class="sxs-lookup"><span data-stu-id="20ebc-195">Type `10` in the **Polling Interval** property.</span></span>  
  
9. <span data-ttu-id="20ebc-196">Escriba la dirección URL para el sitio de SharePoint en el **dirección**punto propiedad de dirección Url del sitio.</span><span class="sxs-lookup"><span data-stu-id="20ebc-196">Type the URL to your SharePoint site in the **ShareP**oint Site Url property.</span></span> <span data-ttu-id="20ebc-197">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-197">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
10. <span data-ttu-id="20ebc-198">Tipo de `Source` para el **biblioteca de documentos de origen** propiedad.</span><span class="sxs-lookup"><span data-stu-id="20ebc-198">Type `Source` for the **Source Document Library** property.</span></span>  
  
11. <span data-ttu-id="20ebc-199">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-199">Click **OK**.</span></span>  
  
12. <span data-ttu-id="20ebc-200">En el **propiedades de la ubicación de recepción** cuadro de diálogo, seleccione `BizTalkServerApplication` como el **controlador de recepción**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-200">In the **Receive Location Properties** dialog box, select `BizTalkServerApplication` as the **Receive handler**.</span></span>  
  
13. <span data-ttu-id="20ebc-201">En el **canalización de recepción** lista desplegable, seleccione `PassThruReceive`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-201">In the **Receive pipeline** drop-down list, select `PassThruReceive`.</span></span>  
  
14. <span data-ttu-id="20ebc-202">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-202">Click **OK**.</span></span>  
  
#### <a name="create-the-send-port"></a><span data-ttu-id="20ebc-203">Crear el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="20ebc-203">Create the send port</span></span>  
  
1.  <span data-ttu-id="20ebc-204">En el **consola de administración de BizTalk**, haga clic en el **puertos de envío** nodo, haga clic en **New**y, a continuación, haga clic en **puerto de envío unidireccional estático** .</span><span class="sxs-lookup"><span data-stu-id="20ebc-204">In the **BizTalk Administration Console**, right-click the **Send Ports** node, click **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="20ebc-205">En el **propiedades de puerto de envío** cuadro de diálogo **General**, tipo `SendToDestination` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-205">In the **Send Port Properties** dialog box, under **General**, type `SendToDestination` in the **Name** field.</span></span>  
  
3.  <span data-ttu-id="20ebc-206">En el **transporte** sección, seleccione `Windows SharePoint Services` para el tipo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-206">In the **Transport** section, select `Windows SharePoint Services` for the type.</span></span>  
  
4.  <span data-ttu-id="20ebc-207">Haga clic en **configurar** para configurar las propiedades de adaptador de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="20ebc-207">Click **Configure** to configure the Windows SharePoint Services adapter properties.</span></span>  
  
5.  <span data-ttu-id="20ebc-208">En el **adaptador de puerto del servicio Web** propiedad, escriba el número de puerto del servidor virtual donde se instaló el servicio Web del adaptador de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="20ebc-208">In the **Adapter Web Service Port** property, type the port number of the virtual server where the Windows SharePoint Services adapter Web service was installed.</span></span> <span data-ttu-id="20ebc-209">De forma predeterminada, éste es el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="20ebc-209">By default, this is port 80.</span></span>  
  
6.  <span data-ttu-id="20ebc-210">Escriba en `Destination` para el **carpeta de destino** propiedad.</span><span class="sxs-lookup"><span data-stu-id="20ebc-210">Type in `Destination` for the **Destination Folder** property.</span></span>  
  
7.  <span data-ttu-id="20ebc-211">Escriba en `PurchaseOrder1-%MessageID%.xml` para el **Filename** propiedad.</span><span class="sxs-lookup"><span data-stu-id="20ebc-211">Type in `PurchaseOrder1-%MessageID%.xml` for the **Filename** property.</span></span>  
  
8.  <span data-ttu-id="20ebc-212">Establecer el **sobrescribir** propiedad `Yes`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-212">Set the **Overwrite** property to `Yes`.</span></span>  
  
9. <span data-ttu-id="20ebc-213">Escriba la dirección URL para el sitio de SharePoint en el **dirección Url del sitio de SharePoint** propiedad.</span><span class="sxs-lookup"><span data-stu-id="20ebc-213">Type in the URL to your SharePoint site in the **SharePoint Site Url** property.</span></span> <span data-ttu-id="20ebc-214">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-214">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
10. <span data-ttu-id="20ebc-215">Establecer el **integración con Microsoft Office** propiedad `No`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-215">Set the **Microsoft Office Integration** property to `No`.</span></span>  
  
11. <span data-ttu-id="20ebc-216">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-216">Click **OK**.</span></span>  
  
12. <span data-ttu-id="20ebc-217">En el **cuadro de diálogo de propiedades de puerto de envío**, en la **controlador de envío** lista desplegable, seleccione `BizTalkServerApplication`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-217">In the **Send Port Properties dialog box**, in the **Send handler** drop-down list, select `BizTalkServerApplication`.</span></span>  
  
13. <span data-ttu-id="20ebc-218">En el **canalización de envío** lista desplegable, seleccione `PassThruTransmit`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-218">In the **Send pipeline** drop-down list, select `PassThruTransmit`.</span></span>  
  
14. <span data-ttu-id="20ebc-219">Haga clic en el **filtros** ficha.</span><span class="sxs-lookup"><span data-stu-id="20ebc-219">Click the **Filters** tab.</span></span>  
  
15. <span data-ttu-id="20ebc-220">Seleccione `WSS.InListName` en el **propiedad** campo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-220">Select `WSS.InListName` in the **Property** field.</span></span>  
  
16. <span data-ttu-id="20ebc-221">Seleccione `==` en el **operador** campo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-221">Select `==` in the **Operator** field.</span></span>  
  
17. <span data-ttu-id="20ebc-222">Tipo de `Source` en el **valor** campo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-222">Type `Source` in the **Value** field.</span></span>  
  
18. <span data-ttu-id="20ebc-223">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-223">Click **OK**.</span></span>  
  
## <a name="enable-and-start-the-receive-location-and-receive-port"></a><span data-ttu-id="20ebc-224">Habilite e inicie la ubicación de recepción y el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="20ebc-224">Enable and start the receive location and receive port</span></span>  
 <span data-ttu-id="20ebc-225">Con estos procedimientos, se habilita la ubicación de recepción y se inicia el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="20ebc-225">In these procedures you enable the receive location and start the receive port.</span></span> <span data-ttu-id="20ebc-226">Este procedimiento debe completarse para permitir que el adaptador de Windows Sharepoint Services envíe y reciba mensajes a través de la ubicación de recepción y del puerto de envío especificados.</span><span class="sxs-lookup"><span data-stu-id="20ebc-226">This procedure must be completed to allow the Windows Sharepoint Services adapter to send and receive messages through the specified send port and receive location.</span></span>  
  
#### <a name="enable-the-receive-location"></a><span data-ttu-id="20ebc-227">Habilitar la ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="20ebc-227">Enable the receive location</span></span>  
  
1.  <span data-ttu-id="20ebc-228">En el **consola de administración de BizTalk**, haga clic en el **ubicaciones de recepción** nodo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-228">In the **BizTalk Administration Console**, click the **Receive Locations** node.</span></span>  
  
2.  <span data-ttu-id="20ebc-229">Haga clic en `SourceLocation`y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-229">Right-click `SourceLocation`, and then click **Enable**.</span></span>  
  
#### <a name="start-the-send-port"></a><span data-ttu-id="20ebc-230">Iniciar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="20ebc-230">Start the send port</span></span>  
  
1.  <span data-ttu-id="20ebc-231">En el **consola de administración de BizTalk**, haga clic en el **puertos de envío** nodo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-231">In the **BizTalk Administration Console**, click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="20ebc-232">Haga clic en `SendToDestination`y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-232">Right-click `SendToDestination`, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="20ebc-233">Cerrar la **consola de administración de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-233">Close the **BizTalk Administration Console**.</span></span>  
  
## <a name="sending-a-message-through-the-system"></a><span data-ttu-id="20ebc-234">Enviar un mensaje a través del sistema</span><span class="sxs-lookup"><span data-stu-id="20ebc-234">Sending a message through the system</span></span>  
 <span data-ttu-id="20ebc-235">Con este procedimiento, creará un documento XML y lo cargará en el sitio Web de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="20ebc-235">In this procedure you create an XML document and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="20ebc-236">El adaptador de Windows SharePoint Services tomará el mensaje, lo archivará en la biblioteca de documentos de archivo y, a continuación, lo enviará a la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="20ebc-236">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="20ebc-237">En este procedimiento se demuestra cómo un documento se transfiere de un sitio web de Sharepoint, a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a un sitio web de Sharepoint Services mediante el adaptador de Windows Sharepoint Services.</span><span class="sxs-lookup"><span data-stu-id="20ebc-237">This procedure demonstrates how a document flows from a Sharepoint web site, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and to a Sharepoint Services Web site using the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-a-working-directory"></a><span data-ttu-id="20ebc-238">Crear un directorio de trabajo</span><span class="sxs-lookup"><span data-stu-id="20ebc-238">Create a working directory</span></span>  
  
-   <span data-ttu-id="20ebc-239">Cree un directorio en su equipo llamado **WSSAdapterWalkthrough**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-239">Create a directory on your computer called **WSSAdapterWalkthrough**.</span></span> <span data-ttu-id="20ebc-240">Por ejemplo, `C:\WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-240">For example, `C:\WSSAdapterWalkthrough`.</span></span>  
  
#### <a name="create-an-xml-file"></a><span data-ttu-id="20ebc-241">Crear un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="20ebc-241">Create an XML file</span></span>  
  
1.  <span data-ttu-id="20ebc-242">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **el Bloc de notas.**</span><span class="sxs-lookup"><span data-stu-id="20ebc-242">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Notepad.**</span></span>  
  
2.  <span data-ttu-id="20ebc-243">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="20ebc-243">Type the following:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <PurchaseOrder>  
        <ID>1001</ID>  
        <FirstName>John</FirstName>  
        <LastName>Doe</LastName>  
        <Amount>750</Amount>  
    </PurchaseOrder>  
    ```  
  
3.  <span data-ttu-id="20ebc-244">Guarde el archivo en el directorio de trabajo como `PurchaseOrder1.xml`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-244">Save the file in your working directory as `PurchaseOrder1.xml`.</span></span> <span data-ttu-id="20ebc-245">Por ejemplo, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-245">For example, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`.</span></span>  
  
#### <a name="upload-the-xml-file"></a><span data-ttu-id="20ebc-246">Cargar el archivo XML</span><span class="sxs-lookup"><span data-stu-id="20ebc-246">Upload the XML file</span></span>  
  
1.  <span data-ttu-id="20ebc-247">Abra un explorador Web y desplácese a la dirección URL del sitio creado en la última tarea.</span><span class="sxs-lookup"><span data-stu-id="20ebc-247">Open a Web browser and navigate to the URL of the site you created in the last task.</span></span> <span data-ttu-id="20ebc-248">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="20ebc-248">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="20ebc-249">En el lado izquierdo, bajo **documentos**, haga clic en **origen**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-249">On the left side, under **Documents**, click **Source**.</span></span>  
  
3.  <span data-ttu-id="20ebc-250">Haga clic en **cargar documento**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-250">Click **Upload Document**.</span></span>  
  
4.  <span data-ttu-id="20ebc-251">En el **nombre** cuadro, escriba o busque el archivo XML que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="20ebc-251">In the **Name** box, type or browse to the XML file you created above.</span></span> <span data-ttu-id="20ebc-252">Por ejemplo, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`y, a continuación, haga clic en **guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-252">For example, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`, and then click **Save and Close**.</span></span> <span data-ttu-id="20ebc-253">Debería poder ver el archivo en la lista.</span><span class="sxs-lookup"><span data-stu-id="20ebc-253">You should now be able to see the file in the list.</span></span>  
  
5.  <span data-ttu-id="20ebc-254">Actualice la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="20ebc-254">Refresh the browser window.</span></span> <span data-ttu-id="20ebc-255">El archivo `PurchaseOrder1.xml` ya no aparece en esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="20ebc-255">The `PurchaseOrder1.xml` file will no longer be listed in this library.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20ebc-256">Es posible que tenga que actualizar el explorador varias veces ya que el intervalo de sondeo está establecido en 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="20ebc-256">You may have to refresh the browser a few times since the polling interval is set at 10 seconds.</span></span>  
  
6.  <span data-ttu-id="20ebc-257">En la barra de navegación superior, haga clic en **documentos y listas**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-257">On the top navigation bar, click **Documents and Lists**.</span></span>  
  
7.  <span data-ttu-id="20ebc-258">En **las bibliotecas de documentos**, haga clic en **destino**.</span><span class="sxs-lookup"><span data-stu-id="20ebc-258">Under **Document Libraries**, click **Destination**.</span></span>  
  
8.  <span data-ttu-id="20ebc-259">En la biblioteca de documentos de destino, ahora verá el mensaje incluido en la lista.</span><span class="sxs-lookup"><span data-stu-id="20ebc-259">In the Destination Document Library, you will now see your message listed.</span></span> <span data-ttu-id="20ebc-260">También encontrará una copia archivada en la biblioteca de documentos de archivo.</span><span class="sxs-lookup"><span data-stu-id="20ebc-260">You will also find a copy archived in the Archive Document Library.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20ebc-261">Si no aparece el mensaje en la biblioteca de documentos de destino, vea "Solucionar problemas del adaptador de Windows SharePoint Services" en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20ebc-261">If the message does not appear in the Destination Document Library, refer to "Troubleshooting the Windows SharePoint Services Adapter" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="20ebc-262">Resumen</span><span class="sxs-lookup"><span data-stu-id="20ebc-262">Summary</span></span>  
 <span data-ttu-id="20ebc-263">En este tutorial ha visto cómo configurar Windows SharePoint Services y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar y recibir mensajes mediante el adaptador de Windows SharePoint Services y el enrutamiento basado en contenido (CBR).</span><span class="sxs-lookup"><span data-stu-id="20ebc-263">In this walkthrough you have seen how to configure Windows SharePoint Services and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] so you can send and receive a message using the Windows SharePoint Services adapter and content-based routing (CBR).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="20ebc-264">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="20ebc-264">Next Steps</span></span>  
 <span data-ttu-id="20ebc-265">Ahora que ha completado este tutorial, realice la [Tutorial: módulo 2: integrar Office con el adaptador de Windows SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) tutorial, que se expande en el trabajo que ha realizado en este tutorial y muestra también cómo integrar Office con el adaptador de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="20ebc-265">Now that you have completed this walkthrough, perform the [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) walkthrough, which expands on the work you have done with this walkthrough and shows you how to integrate Office with the Windows SharePoint Services adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ebc-266">Vea también</span><span class="sxs-lookup"><span data-stu-id="20ebc-266">See Also</span></span>  
 <span data-ttu-id="20ebc-267">[¿Qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="20ebc-267">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="20ebc-268">Tutoriales del adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="20ebc-268">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)