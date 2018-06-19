---
title: 'Paso 4: Crear una aplicación de Sharepoint para tener acceso el adaptador | Documentos de Microsoft'
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
ms.openlocfilehash: 3360bbdf5ae5a6a8dde9851c544342ea6a6bc1cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226884"
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a><span data-ttu-id="ac044-102">Paso 4: Crear una aplicación de Sharepoint para tener acceso el adaptador</span><span class="sxs-lookup"><span data-stu-id="ac044-102">Step 4: Create a Sharepoint Application to Access the Adapter</span></span>
<span data-ttu-id="ac044-103">![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="ac044-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="ac044-104">**Tiempo en completarse:** 15 minutos</span><span class="sxs-lookup"><span data-stu-id="ac044-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="ac044-105">En este paso se dejar el archivo de definición de aplicación que creó utilizando la herramienta Editor de definición de catálogo de datos profesionales y se importa en Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="ac044-105">In this step you take the application definition file that you created using the Business Data Catalog Definition Editor tool, and import it into Microsoft Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ac044-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ac044-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="ac044-107">Se debe haber creado un archivo de aplicación como se describe en [paso 3: crear un archivo de definición de aplicación](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span><span class="sxs-lookup"><span data-stu-id="ac044-107">You should have created an application file as described in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
-   <span data-ttu-id="ac044-108">Debe ejecutar el servicio Microsoft Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="ac044-108">The Microsoft Single Sign-On service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="ac044-109">Cómo crear una aplicación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ac044-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="ac044-110">Crear una aplicación de SharePoint implica los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac044-110">Creating a SharePoint application involves the following steps:</span></span>  
  
-   <span data-ttu-id="ac044-111">Crear una aplicación de inicio de sesión único (SSO) en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ac044-111">Create a Single Sign-On (SSO) application in SharePoint.</span></span>  
  
-   <span data-ttu-id="ac044-112">Crear un proveedor de servicios compartidos e importar el archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ac044-112">Create a Shared Services Provider, and import the application definition file.</span></span>  
  
-   <span data-ttu-id="ac044-113">Crear una página de elementos Web y agregar elementos Web.</span><span class="sxs-lookup"><span data-stu-id="ac044-113">Create a Web Part page, and add Web Parts.</span></span>  
  
 <span data-ttu-id="ac044-114">Este tema muestra cómo realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ac044-114">This topic demonstrates how to perform these steps.</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="ac044-115">Crear una aplicación de SSO en SharePoint</span><span class="sxs-lookup"><span data-stu-id="ac044-115">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="ac044-116">Para pasar las credenciales de usuario para el adaptador de eco desde una aplicación de SharePoint, debe configurar una aplicación de SSO que se asigna a una cuenta de usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="ac044-116">To pass user credentials to the Echo adapter from a SharePoint application, you must set up an SSO application that maps to a user account or group.</span></span>  
  
#### <a name="manage-server-settings-for-single-sign-on"></a><span data-ttu-id="ac044-117">Administrar la configuración de servidor para el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="ac044-117">Manage server settings for Single Sign-On</span></span>  
  
1.  <span data-ttu-id="ac044-118">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="ac044-118">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="ac044-119">En el **iniciar** menú, elija **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="ac044-119">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="ac044-120">En la barra de navegación superior, haga clic en **Operations**.</span><span class="sxs-lookup"><span data-stu-id="ac044-120">On the top navigation bar, click **Operations**.</span></span>  
  
3.  <span data-ttu-id="ac044-121">En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.</span><span class="sxs-lookup"><span data-stu-id="ac044-121">On the Operations page, in the **Security Configuration** section, click **Manage settings for single sign-on**.</span></span>  
  
4.  <span data-ttu-id="ac044-122">En la página Administrar configuración de inicio de sesión único, en el **configuración del servidor** sección, haga clic en **Administrar configuración del servidor**.</span><span class="sxs-lookup"><span data-stu-id="ac044-122">On the Manage Settings for Single Sign-On page, in the **Server Settings** section, click **Manage Server Settings**.</span></span>  
  
5.  <span data-ttu-id="ac044-123">Asegúrese de que la información de esta página es correcta para la instalación de inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="ac044-123">Ensure that the information on this page is correct for your Single Sign-On installation.</span></span> <span data-ttu-id="ac044-124">Para obtener más información acerca de estas operaciones, vea "Configurar el inicio de sesión único (Office SharePoint Server)" en [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span><span class="sxs-lookup"><span data-stu-id="ac044-124">For more information about these operations, see “Configure single sign-on (Office SharePoint Server)” at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a><span data-ttu-id="ac044-125">Administrar la configuración de las definiciones de aplicaciones de empresa</span><span class="sxs-lookup"><span data-stu-id="ac044-125">Manage settings for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="ac044-126">En Administración Central de SharePoint, en la barra de navegación superior, haga clic en **Operations**.</span><span class="sxs-lookup"><span data-stu-id="ac044-126">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="ac044-127">En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.</span><span class="sxs-lookup"><span data-stu-id="ac044-127">On the Operations page, in the **Security Configuration** section, click **Manage Settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="ac044-128">En la página Administrar configuración de inicio de sesión único, en el **configuración de definición de aplicaciones de empresa** sección, haga clic en **administrar la configuración de las definiciones de aplicaciones de empresa**.</span><span class="sxs-lookup"><span data-stu-id="ac044-128">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage Settings for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="ac044-129">En la página Administrar las definiciones de aplicación de empresa, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ac044-129">On the Manage Enterprise Application Definitions page, click **New Item**.</span></span>  
  
5.  <span data-ttu-id="ac044-130">En el crear Enterprise aplicación definiciones de página, establezca la **nombre para mostrar** campo **EchoSSO**y, a continuación, establezca el **nombre de la aplicación** campo  **EchoSSO**.</span><span class="sxs-lookup"><span data-stu-id="ac044-130">On the Create Enterprise Application Definitions Page, set the **Display name** field to **EchoSSO**, and then set the **Application name** field to **EchoSSO**.</span></span> <span data-ttu-id="ac044-131">Este valor debe coincidir con SecondarySsoApplicationId especificado en [paso 3: crear un archivo de definición de aplicación](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span><span class="sxs-lookup"><span data-stu-id="ac044-131">This value should match the SecondarySsoApplicationId you specified in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
6.  <span data-ttu-id="ac044-132">En el **póngase en contacto con la dirección de correo electrónico** campo, escriba su dirección de correo electrónico y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac044-132">In the **Contact e-mail address** field, enter your e-mail address, and then click **OK**.</span></span>  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a><span data-ttu-id="ac044-133">Administrar la información de cuenta para definiciones de aplicación de empresa</span><span class="sxs-lookup"><span data-stu-id="ac044-133">Manage account information for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="ac044-134">En Administración Central de SharePoint, en la barra de navegación superior, haga clic en **Operations**.</span><span class="sxs-lookup"><span data-stu-id="ac044-134">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="ac044-135">En la página operaciones, en la **sección de configuración de seguridad**, haga clic en **administrar la configuración de inicio de sesión único**.</span><span class="sxs-lookup"><span data-stu-id="ac044-135">On the Operations page, in the **Security Configuration Section**, click **Manage settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="ac044-136">En la página Administrar configuración de inicio de sesión único, en el **configuración de definición de aplicaciones de empresa** sección, haga clic en **administrar información de cuenta para empresa las definiciones de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="ac044-136">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage account information for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="ac044-137">En la información de cuenta de administrar para una definición de aplicación de empresa, seleccione **EchoSSO** desde el **definición de aplicación empresarial** lista.</span><span class="sxs-lookup"><span data-stu-id="ac044-137">On the Manage Account Information for an Enterprise Application Definition, select **EchoSSO** from the **Enterprise application definition** list.</span></span>  
  
5.  <span data-ttu-id="ac044-138">En el **nombre de la cuenta de grupo** , escriba el grupo de Windows que se usará para proteger esta definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ac044-138">In the **Group account name** field, type the Windows group that will be used to secure this application definition.</span></span> <span data-ttu-id="ac044-139">Por ejemplo, **decir a los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ac044-139">For example, **DOMAIN\Domain Users**.</span></span>  
  
6.  <span data-ttu-id="ac044-140">Haga clic en **Conjunto**.</span><span class="sxs-lookup"><span data-stu-id="ac044-140">Click **Set**.</span></span>  
  
7.  <span data-ttu-id="ac044-141">En la página de información de la cuenta de EchoSSO proporcionar, en la **nombre de usuario** campo tipo **testuser**y, a continuación, en la **contraseña** campo tipo **testpassword**.</span><span class="sxs-lookup"><span data-stu-id="ac044-141">On the Provide EchoSSO Account Information page, in the **Username** field type **testuser**, and then in the **Password** field type **testpassword**.</span></span>  
  
8.  <span data-ttu-id="ac044-142">Haga clic en **Aceptar**y, a continuación, haga clic en **realiza**.</span><span class="sxs-lookup"><span data-stu-id="ac044-142">Click **OK**, and then click **Done**.</span></span>  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a><span data-ttu-id="ac044-143">Crear un proveedor de servicios compartidos e importar el archivo de definición de aplicación</span><span class="sxs-lookup"><span data-stu-id="ac044-143">Creating a Shared Services Provider and importing the application definition file</span></span>  
 <span data-ttu-id="ac044-144">Un proveedor de servicios compartidos (SSP) es una agrupación lógica de servicios compartidos y sus recursos de soporte.</span><span class="sxs-lookup"><span data-stu-id="ac044-144">A Shared Services Provider (SSP) is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="ac044-145">Puede crear un SSP mediante la consola de Administración Central de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ac044-145">You can create an SSP by using the SharePoint Central Administration Console.</span></span> <span data-ttu-id="ac044-146">Este ejemplo funciona en cualquier SSP.</span><span class="sxs-lookup"><span data-stu-id="ac044-146">This example will work in any SSP.</span></span> <span data-ttu-id="ac044-147">Para obtener más información acerca de cómo crear un SSP, vea "información general de capítulo: crear y configurar proveedores de servicios compartidos" en [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span><span class="sxs-lookup"><span data-stu-id="ac044-147">For more information about creating an SSP, see “Chapter overview: Create and Configure Shared Services Providers” at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="ac044-148">Para importar el archivo de definición de aplicación</span><span class="sxs-lookup"><span data-stu-id="ac044-148">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="ac044-149">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="ac044-149">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="ac044-150">En el **iniciar** menú, elija **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="ac044-150">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="ac044-151">En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ac044-151">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="ac044-152">En el **catálogo de datos profesionales** sección, haga clic en **Importar definición de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="ac044-152">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="ac044-153">En la página definición de la aplicación de importación, haga clic en **examinar**y, a continuación, seleccione el archivo EchoWS.xml.</span><span class="sxs-lookup"><span data-stu-id="ac044-153">On the Import Application Definition page, click **Browse**, and then select the EchoWS.xml file.</span></span>  
  
5.  <span data-ttu-id="ac044-154">Haga clic en **importación**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac044-154">Click **Import**, and then click **OK**.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="ac044-155">Crear elementos Web</span><span class="sxs-lookup"><span data-stu-id="ac044-155">Creating Web Parts</span></span>  
 <span data-ttu-id="ac044-156">Ahora debe crear elementos Web en el sitio de SharePoint para usar la instancia de método creada en el Editor de definición de catálogo de datos de Business.</span><span class="sxs-lookup"><span data-stu-id="ac044-156">You must now create Web Parts in your SharePoint site to use the method instance created in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="ac044-157">Elementos Web son componentes reutilizables que pueden contener cualquier tipo de información basada en Web, incluidos analíticos, colaboración y obtener información de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac044-157">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
#### <a name="to-create-a-web-part-page"></a><span data-ttu-id="ac044-158">Para crear una página de elementos Web</span><span class="sxs-lookup"><span data-stu-id="ac044-158">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="ac044-159">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="ac044-159">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="ac044-160">En el **iniciar** menú, elija **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="ac044-160">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="ac044-161">En el panel de navegación izquierdo, haga clic en el nombre del SSP en el que se importó el archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ac044-161">In the left navigation pane, click the name of the SSP in which you imported the application definition file.</span></span>  
  
3.  <span data-ttu-id="ac044-162">En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="ac044-162">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="ac044-163">![Crear acciones del sitio](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span><span class="sxs-lookup"><span data-stu-id="ac044-163">![Create Site Actions](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span></span>  
  
4.  <span data-ttu-id="ac044-164">En el **crear** página, en la **páginas Web** sección, haga clic en **página de elementos Web**.</span><span class="sxs-lookup"><span data-stu-id="ac044-164">On the **Create** page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="ac044-165">En la página nuevo elemento Web, en la **nombre** , escriba **EchoPart**y, a continuación, seleccione **página completa, Vertical** desde el **elegido una plantilla de diseño**lista.</span><span class="sxs-lookup"><span data-stu-id="ac044-165">On the New Web Part page, in the **Name** field, type **EchoPart**, and then select **Full Page, Vertical** from the **Chose a Layout Template** list.</span></span>  
  
6.  <span data-ttu-id="ac044-166">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="ac044-166">Click **Create**.</span></span>  
  
#### <a name="to-add-a-business-data-web-part"></a><span data-ttu-id="ac044-167">Para agregar un elemento Web de datos de empresa</span><span class="sxs-lookup"><span data-stu-id="ac044-167">To add a Business Data Web Part</span></span>  
  
1.  <span data-ttu-id="ac044-168">Haga clic en **Agregar elemento web**.</span><span class="sxs-lookup"><span data-stu-id="ac044-168">Click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="ac044-169">En el **agregar elementos Web** cuadro de diálogo, seleccione **lista de datos económicos**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="ac044-169">In the **Add Web Parts** dialog box, select **Business Data List**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="ac044-170">![Lista de datos económicos](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span><span class="sxs-lookup"><span data-stu-id="ac044-170">![Business Data List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span></span>  
  
3.  <span data-ttu-id="ac044-171">Haga clic en **abrir el panel de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ac044-171">Click **Open the tool pane**.</span></span>  
  
4.  <span data-ttu-id="ac044-172">El panel de herramientas de la lista de datos económicos se abre en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="ac044-172">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="ac044-173">En el **lista de datos económicos** sección, para la **tipo** , a continuación, haga clic en el **examinar** botón.</span><span class="sxs-lookup"><span data-stu-id="ac044-173">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="ac044-174">![Seleccione el tipo de](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span><span class="sxs-lookup"><span data-stu-id="ac044-174">![Select the Type](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span></span>  
  
5.  <span data-ttu-id="ac044-175">En el **selector de tipo de datos profesionales** cuadro de diálogo, seleccione la **EchoWSLob_Instance** aplicación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac044-175">In the **Business Data Type Picker** dialog box, select the **EchoWSLob_Instance** application, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="ac044-176">En el panel de herramientas de la lista de datos económicos, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac044-176">On the Business Data List tool pane, click **OK**.</span></span>  
  
7.  <span data-ttu-id="ac044-177">Se presentan con un campo que permite especificar un valor de saludo para pasar al método EchoGreetings.</span><span class="sxs-lookup"><span data-stu-id="ac044-177">You are presented with a field that allows you to enter a greeting value to pass to the EchoGreetings method.</span></span> <span data-ttu-id="ac044-178">Escribir datos en el campo de saludo y haga clic en **recuperar datos**.</span><span class="sxs-lookup"><span data-stu-id="ac044-178">Enter data in the greeting field and click **Retrieve Data**.</span></span> <span data-ttu-id="ac044-179">Esto invoca el método EchoGreetings del adaptador de eco hospedado en IIS y devuelve una respuesta.</span><span class="sxs-lookup"><span data-stu-id="ac044-179">This invokes the EchoGreetings method of the Echo adapter hosted in IIS and returns a response.</span></span>  
  
     <span data-ttu-id="ac044-180">![Lista EchoGreetings](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span><span class="sxs-lookup"><span data-stu-id="ac044-180">![EchoGreetings List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac044-181">La columna de nombre no contiene la información de usuario, pero solo muestra BDC. Nombre.</span><span class="sxs-lookup"><span data-stu-id="ac044-181">The name column does not contain the user information, but only displays BDC.Name.</span></span> <span data-ttu-id="ac044-182">Esto ocurre porque la BDC espera sólo una estructura de registro simple y no muestra la estructura compleja representada por el campo de nombre.</span><span class="sxs-lookup"><span data-stu-id="ac044-182">This occurs because the BDC expects only a simple record structure, and does not display the complex structure represented by the name field.</span></span>  
  
8.  <span data-ttu-id="ac044-183">Haga clic en **salir del modo de edición** desde la esquina superior de la página.</span><span class="sxs-lookup"><span data-stu-id="ac044-183">Click **Exit Edit Mode** from the upper corner of the page.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="ac044-184">Síntesis</span><span class="sxs-lookup"><span data-stu-id="ac044-184">What did I just do?</span></span>  
 <span data-ttu-id="ac044-185">Ha usado la Administración Central de SharePoint 3.0 para importar una definición de aplicación y crear elementos Web que utilizan esta definición para invocar la operación de EchoGreetings del adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="ac044-185">You have used the SharePoint 3.0 Central Administration to import an application definition, and create Web Parts that use this definition to invoke the EchoGreetings operation of the Echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ac044-186">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ac044-186">Next Steps</span></span>  
 <span data-ttu-id="ac044-187">Este tutorial está completado.</span><span class="sxs-lookup"><span data-stu-id="ac044-187">This tutorial is complete.</span></span> <span data-ttu-id="ac044-188">Para obtener más información con el catálogo de datos empresariales, vea "Catálogo de datos profesionales" en [http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921).</span><span class="sxs-lookup"><span data-stu-id="ac044-188">For more information using the Business Data Catalog, see “Business Data Catalog” at [http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac044-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac044-189">See Also</span></span>  
 [<span data-ttu-id="ac044-190">Tutorial 3: Aloja el adaptador de eco en IIS</span><span class="sxs-lookup"><span data-stu-id="ac044-190">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)