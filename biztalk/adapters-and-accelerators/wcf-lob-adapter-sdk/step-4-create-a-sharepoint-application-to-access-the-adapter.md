---
title: 'Paso 4: Crear una aplicación de Sharepoint para tener acceso al adaptador | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d8c398-370a-4c62-961d-0eab6066ad5a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15da47a4171d6bdf4f3b53e2208851bd15ecb0d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986645"
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a><span data-ttu-id="8bc20-102">Paso 4: Crear una aplicación de Sharepoint para tener acceso al adaptador</span><span class="sxs-lookup"><span data-stu-id="8bc20-102">Step 4: Create a Sharepoint Application to Access the Adapter</span></span>
<span data-ttu-id="8bc20-103">![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="8bc20-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="8bc20-104">**Tiempo en completarse:** 15 minutos</span><span class="sxs-lookup"><span data-stu-id="8bc20-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="8bc20-105">En este paso se tome el archivo de definición de aplicación creados mediante la herramienta Editor de definición de catálogo de datos profesionales e importarlo en Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="8bc20-105">In this step you take the application definition file that you created using the Business Data Catalog Definition Editor tool, and import it into Microsoft Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8bc20-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8bc20-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="8bc20-107">Se debe haber creado un archivo de aplicación como se describe en [paso 3: crear un archivo de definición de aplicación](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span><span class="sxs-lookup"><span data-stu-id="8bc20-107">You should have created an application file as described in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
-   <span data-ttu-id="8bc20-108">El servicio Microsoft Single Sign-On debe estar ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="8bc20-108">The Microsoft Single Sign-On service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="8bc20-109">Cómo crear una aplicación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="8bc20-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="8bc20-110">Creación de una aplicación de SharePoint implica los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bc20-110">Creating a SharePoint application involves the following steps:</span></span>  
  
- <span data-ttu-id="8bc20-111">Cree una aplicación de inicio de sesión único (SSO) en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8bc20-111">Create a Single Sign-On (SSO) application in SharePoint.</span></span>  
  
- <span data-ttu-id="8bc20-112">Crear un proveedor de servicios compartidos e importar el archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8bc20-112">Create a Shared Services Provider, and import the application definition file.</span></span>  
  
- <span data-ttu-id="8bc20-113">Cree una página de elementos Web y agregar elementos Web.</span><span class="sxs-lookup"><span data-stu-id="8bc20-113">Create a Web Part page, and add Web Parts.</span></span>  
  
  <span data-ttu-id="8bc20-114">En este tema se muestra cómo realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8bc20-114">This topic demonstrates how to perform these steps.</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="8bc20-115">Creación de una aplicación de inicio de sesión único en SharePoint</span><span class="sxs-lookup"><span data-stu-id="8bc20-115">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="8bc20-116">Para pasar las credenciales de usuario para el adaptador de Echo desde una aplicación de SharePoint, debe configurar una aplicación de inicio de sesión único que se asigna a una cuenta de usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="8bc20-116">To pass user credentials to the Echo adapter from a SharePoint application, you must set up an SSO application that maps to a user account or group.</span></span>  
  
#### <a name="manage-server-settings-for-single-sign-on"></a><span data-ttu-id="8bc20-117">Administrar la configuración de servidor para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="8bc20-117">Manage server settings for Single Sign-On</span></span>  
  
1.  <span data-ttu-id="8bc20-118">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="8bc20-118">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="8bc20-119">En el **iniciar** menú, elija **todos los programas**, apunte a **Microsoft Office Server**y, a continuación, haga clic en **SharePoint 3.0 Central Administration**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-119">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="8bc20-120">En la barra de navegación superior, haga clic en **operaciones**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-120">On the top navigation bar, click **Operations**.</span></span>  
  
3.  <span data-ttu-id="8bc20-121">En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-121">On the Operations page, in the **Security Configuration** section, click **Manage settings for single sign-on**.</span></span>  
  
4.  <span data-ttu-id="8bc20-122">En la página Administrar configuración de inicio de sesión único, en el **configuración del servidor** sección, haga clic en **Administrar configuración del servidor**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-122">On the Manage Settings for Single Sign-On page, in the **Server Settings** section, click **Manage Server Settings**.</span></span>  
  
5.  <span data-ttu-id="8bc20-123">Asegúrese de que la información de esta página es correcta para la instalación de inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="8bc20-123">Ensure that the information on this page is correct for your Single Sign-On installation.</span></span> <span data-ttu-id="8bc20-124">Para obtener más información acerca de estas operaciones, vea "Configurar el inicio de sesión único (Office SharePoint Server)" en [ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291).</span><span class="sxs-lookup"><span data-stu-id="8bc20-124">For more information about these operations, see “Configure single sign-on (Office SharePoint Server)” at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a><span data-ttu-id="8bc20-125">Administrar la configuración de las definiciones de aplicaciones de empresa</span><span class="sxs-lookup"><span data-stu-id="8bc20-125">Manage settings for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="8bc20-126">En Administración Central de SharePoint, en la barra de navegación superior, haga clic en **operaciones**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-126">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="8bc20-127">En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-127">On the Operations page, in the **Security Configuration** section, click **Manage Settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="8bc20-128">En la página Administrar configuración de inicio de sesión único, en el **definición de configuración de aplicaciones de empresa** sección, haga clic en **administrar la configuración de las definiciones de aplicaciones de empresa**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-128">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage Settings for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="8bc20-129">En la página Administrar definiciones de aplicaciones de empresa, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-129">On the Manage Enterprise Application Definitions page, click **New Item**.</span></span>  
  
5.  <span data-ttu-id="8bc20-130">En la creación de Enterprise aplicación las definiciones de página, establezca el **nombre para mostrar** campo **EchoSSO**y, a continuación, establezca el **nombre de la aplicación** campo  **EchoSSO**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-130">On the Create Enterprise Application Definitions Page, set the **Display name** field to **EchoSSO**, and then set the **Application name** field to **EchoSSO**.</span></span> <span data-ttu-id="8bc20-131">Este valor debe coincidir con el que especificó en SecondarySsoApplicationId [paso 3: crear un archivo de definición de aplicación](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span><span class="sxs-lookup"><span data-stu-id="8bc20-131">This value should match the SecondarySsoApplicationId you specified in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
6.  <span data-ttu-id="8bc20-132">En el **dirección de correo electrónico de contacto** campo, escriba su dirección de correo electrónico y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-132">In the **Contact e-mail address** field, enter your e-mail address, and then click **OK**.</span></span>  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a><span data-ttu-id="8bc20-133">Administrar la información de cuenta para definiciones de aplicación de empresa</span><span class="sxs-lookup"><span data-stu-id="8bc20-133">Manage account information for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="8bc20-134">En Administración Central de SharePoint, en la barra de navegación superior, haga clic en **operaciones**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-134">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="8bc20-135">En la página operaciones, en la **sección de configuración de seguridad**, haga clic en **administrar la configuración de inicio de sesión único**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-135">On the Operations page, in the **Security Configuration Section**, click **Manage settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="8bc20-136">En la página Administrar configuración de inicio de sesión único, en el **definición de configuración de aplicaciones de empresa** sección, haga clic en **administrar información de cuenta para empresa las definiciones de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-136">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage account information for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="8bc20-137">En la información de cuenta de administración para una definición de aplicación empresarial, seleccione **EchoSSO** desde el **definición de aplicación empresarial** lista.</span><span class="sxs-lookup"><span data-stu-id="8bc20-137">On the Manage Account Information for an Enterprise Application Definition, select **EchoSSO** from the **Enterprise application definition** list.</span></span>  
  
5.  <span data-ttu-id="8bc20-138">En el **nombre de la cuenta de grupo** , escriba el grupo de Windows que se usará para proteger esta definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8bc20-138">In the **Group account name** field, type the Windows group that will be used to secure this application definition.</span></span> <span data-ttu-id="8bc20-139">Por ejemplo, **decir a los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-139">For example, **DOMAIN\Domain Users**.</span></span>  
  
6.  <span data-ttu-id="8bc20-140">Haga clic en **Conjunto**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-140">Click **Set**.</span></span>  
  
7.  <span data-ttu-id="8bc20-141">En la página de información de la cuenta de EchoSSO proporcionan, en la **Username** tipo de campo **testuser**y, a continuación, en el **contraseña** tipo de campo **testpassword**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-141">On the Provide EchoSSO Account Information page, in the **Username** field type **testuser**, and then in the **Password** field type **testpassword**.</span></span>  
  
8.  <span data-ttu-id="8bc20-142">Haga clic en **Aceptar**y, a continuación, haga clic en **realiza**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-142">Click **OK**, and then click **Done**.</span></span>  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a><span data-ttu-id="8bc20-143">Crear un proveedor de servicios compartidos e importar el archivo de definición de aplicación</span><span class="sxs-lookup"><span data-stu-id="8bc20-143">Creating a Shared Services Provider and importing the application definition file</span></span>  
 <span data-ttu-id="8bc20-144">Un proveedor de servicios compartidos (SSP) es una agrupación lógica de servicios compartidos y sus recursos de apoyo.</span><span class="sxs-lookup"><span data-stu-id="8bc20-144">A Shared Services Provider (SSP) is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="8bc20-145">Puede crear un SSP mediante la consola de Administración Central de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8bc20-145">You can create an SSP by using the SharePoint Central Administration Console.</span></span> <span data-ttu-id="8bc20-146">Este ejemplo funciona en cualquier SSP.</span><span class="sxs-lookup"><span data-stu-id="8bc20-146">This example will work in any SSP.</span></span> <span data-ttu-id="8bc20-147">Para obtener más información sobre la creación de un SSP, consulte "información general del capítulo: crear y configurar proveedores de servicios compartidos" en [ http://go.microsoft.com/fwlink/?LinkId=105119 ](http://go.microsoft.com/fwlink/?LinkId=105119).</span><span class="sxs-lookup"><span data-stu-id="8bc20-147">For more information about creating an SSP, see “Chapter overview: Create and Configure Shared Services Providers” at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="8bc20-148">Para importar el archivo de definición de aplicación</span><span class="sxs-lookup"><span data-stu-id="8bc20-148">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="8bc20-149">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="8bc20-149">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="8bc20-150">En el **iniciar** menú, elija **todos los programas**, apunte a **Microsoft Office Server**y, a continuación, haga clic en **SharePoint 3.0 Central Administration**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-150">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="8bc20-151">En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8bc20-151">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="8bc20-152">En el **Business Data Catalog** sección, haga clic en **Importar definición de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-152">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="8bc20-153">En la página definición de aplicación de importación, haga clic en **examinar**y, a continuación, seleccione el archivo EchoWS.xml.</span><span class="sxs-lookup"><span data-stu-id="8bc20-153">On the Import Application Definition page, click **Browse**, and then select the EchoWS.xml file.</span></span>  
  
5.  <span data-ttu-id="8bc20-154">Haga clic en **importación**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-154">Click **Import**, and then click **OK**.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="8bc20-155">Crear elementos Web</span><span class="sxs-lookup"><span data-stu-id="8bc20-155">Creating Web Parts</span></span>  
 <span data-ttu-id="8bc20-156">Ahora debe crear elementos Web en el sitio de SharePoint para usar la instancia de método creada en el Editor de definición de catálogo de datos de Business.</span><span class="sxs-lookup"><span data-stu-id="8bc20-156">You must now create Web Parts in your SharePoint site to use the method instance created in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="8bc20-157">Elementos Web son componentes reutilizables que pueden contener cualquier tipo de información basada en Web, incluido el análisis, colaboración e información de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8bc20-157">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
#### <a name="to-create-a-web-part-page"></a><span data-ttu-id="8bc20-158">Para crear una página de elementos Web</span><span class="sxs-lookup"><span data-stu-id="8bc20-158">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="8bc20-159">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="8bc20-159">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="8bc20-160">En el **iniciar** menú, elija **todos los programas**, apunte a **Microsoft Office Server**y, a continuación, haga clic en **SharePoint 3.0 Central Administration**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-160">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="8bc20-161">En el panel de navegación izquierdo, haga clic en el nombre de SSP en el que ha importado el archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8bc20-161">In the left navigation pane, click the name of the SSP in which you imported the application definition file.</span></span>  
  
3.  <span data-ttu-id="8bc20-162">En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-162">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="8bc20-163">![Crear acciones del sitio](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span><span class="sxs-lookup"><span data-stu-id="8bc20-163">![Create Site Actions](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span></span>  
  
4.  <span data-ttu-id="8bc20-164">En el **crear** página, en el **páginas Web** sección, haga clic en **página de elementos Web**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-164">On the **Create** page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="8bc20-165">En la página nuevo elemento Web, en el **nombre** , escriba **EchoPart**y, a continuación, seleccione **página completa, Vertical** desde el **ha elegido una plantilla de diseño**lista.</span><span class="sxs-lookup"><span data-stu-id="8bc20-165">On the New Web Part page, in the **Name** field, type **EchoPart**, and then select **Full Page, Vertical** from the **Chose a Layout Template** list.</span></span>  
  
6.  <span data-ttu-id="8bc20-166">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-166">Click **Create**.</span></span>  
  
#### <a name="to-add-a-business-data-web-part"></a><span data-ttu-id="8bc20-167">Para agregar un elemento Web de datos de empresa</span><span class="sxs-lookup"><span data-stu-id="8bc20-167">To add a Business Data Web Part</span></span>  
  
1.  <span data-ttu-id="8bc20-168">Haga clic en **Agregar elemento web**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-168">Click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="8bc20-169">En el **agregar elementos Web** cuadro de diálogo, seleccione **lista de datos económicos**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-169">In the **Add Web Parts** dialog box, select **Business Data List**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="8bc20-170">![Lista de datos económicos](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span><span class="sxs-lookup"><span data-stu-id="8bc20-170">![Business Data List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span></span>  
  
3.  <span data-ttu-id="8bc20-171">Haga clic en **abrir el panel de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-171">Click **Open the tool pane**.</span></span>  
  
4.  <span data-ttu-id="8bc20-172">Se abre el panel de herramientas de la lista de datos económicos en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="8bc20-172">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="8bc20-173">En el **lista de datos económicos** sección, para el **tipo** , a continuación, haga clic en el **examinar** botón.</span><span class="sxs-lookup"><span data-stu-id="8bc20-173">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="8bc20-174">![Seleccione el tipo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span><span class="sxs-lookup"><span data-stu-id="8bc20-174">![Select the Type](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span></span>  
  
5.  <span data-ttu-id="8bc20-175">En el **selector de tipos de datos de negocio** cuadro de diálogo, seleccione el **EchoWSLob_Instance** aplicación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-175">In the **Business Data Type Picker** dialog box, select the **EchoWSLob_Instance** application, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="8bc20-176">En el panel de herramientas de la lista de datos económicos, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-176">On the Business Data List tool pane, click **OK**.</span></span>  
  
7.  <span data-ttu-id="8bc20-177">Se presentan con un campo que le permite escribir un valor de saludo para pasar al método EchoGreetings.</span><span class="sxs-lookup"><span data-stu-id="8bc20-177">You are presented with a field that allows you to enter a greeting value to pass to the EchoGreetings method.</span></span> <span data-ttu-id="8bc20-178">Escribir datos en el campo de saludo y haga clic en **recuperar datos**.</span><span class="sxs-lookup"><span data-stu-id="8bc20-178">Enter data in the greeting field and click **Retrieve Data**.</span></span> <span data-ttu-id="8bc20-179">Esto invoca el método EchoGreetings del adaptador de Echo alojado en IIS y devuelve una respuesta.</span><span class="sxs-lookup"><span data-stu-id="8bc20-179">This invokes the EchoGreetings method of the Echo adapter hosted in IIS and returns a response.</span></span>  
  
     <span data-ttu-id="8bc20-180">![Lista EchoGreetings](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span><span class="sxs-lookup"><span data-stu-id="8bc20-180">![EchoGreetings List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8bc20-181">La columna de nombre no contiene la información de usuario, pero solo muestra BDC. Nombre.</span><span class="sxs-lookup"><span data-stu-id="8bc20-181">The name column does not contain the user information, but only displays BDC.Name.</span></span> <span data-ttu-id="8bc20-182">Esto ocurre porque el BDC espera sólo una estructura de registro simple y no muestra la estructura compleja representada por el campo de nombre.</span><span class="sxs-lookup"><span data-stu-id="8bc20-182">This occurs because the BDC expects only a simple record structure, and does not display the complex structure represented by the name field.</span></span>  
  
8.  <span data-ttu-id="8bc20-183">Haga clic en **salir del modo de edición** desde la esquina superior de la página.</span><span class="sxs-lookup"><span data-stu-id="8bc20-183">Click **Exit Edit Mode** from the upper corner of the page.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="8bc20-184">Síntesis</span><span class="sxs-lookup"><span data-stu-id="8bc20-184">What did I just do?</span></span>  
 <span data-ttu-id="8bc20-185">Ha usado la Administración Central de SharePoint 3.0 para importar una definición de aplicación y crear elementos Web que utilizan esta definición para invocar la operación EchoGreetings del adaptador de Echo.</span><span class="sxs-lookup"><span data-stu-id="8bc20-185">You have used the SharePoint 3.0 Central Administration to import an application definition, and create Web Parts that use this definition to invoke the EchoGreetings operation of the Echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8bc20-186">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8bc20-186">Next Steps</span></span>  
 <span data-ttu-id="8bc20-187">Este tutorial está completa.</span><span class="sxs-lookup"><span data-stu-id="8bc20-187">This tutorial is complete.</span></span> <span data-ttu-id="8bc20-188">Para obtener más información con el catálogo de datos empresariales, vea "Catálogo de datos empresariales" en [ http://go.microsoft.com/fwlink/?LinkId=119921 ](http://go.microsoft.com/fwlink/?LinkId=119921).</span><span class="sxs-lookup"><span data-stu-id="8bc20-188">For more information using the Business Data Catalog, see “Business Data Catalog” at [http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc20-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bc20-189">See Also</span></span>  
 [<span data-ttu-id="8bc20-190">Tutorial 3: Hospedar el adaptador de Echo en IIS</span><span class="sxs-lookup"><span data-stu-id="8bc20-190">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)