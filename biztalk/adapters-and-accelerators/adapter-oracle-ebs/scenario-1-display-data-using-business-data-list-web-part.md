---
title: "Escenario 1: Mostrar datos mediante el elemento web de lista de datos económicos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3831814-8b70-4352-b22f-cebd08750ef5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1add974ca3ad0b80b7838b120920f4de47f1650
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-1-display-data-using-business-data-list-web-part"></a><span data-ttu-id="930be-102">Escenario 1: Mostrar datos mediante el elemento web de lista de datos económicos</span><span class="sxs-lookup"><span data-stu-id="930be-102">Scenario 1: Display data using Business Data List web part</span></span>
<span data-ttu-id="930be-103">Usaremos el **lista de datos económicos** elemento Web para la **buscador** instancia de método.</span><span class="sxs-lookup"><span data-stu-id="930be-103">We will use the **Business Data List** Web Part for the **Finder** method instance.</span></span> <span data-ttu-id="930be-104">Este elemento Web le permite especificar una expresión de búsqueda para recuperar una lista de empleados de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="930be-104">This Web Part enables you to specify a search expression to retrieve a list of employees from Oracle E-Business Suite.</span></span> <span data-ttu-id="930be-105">Para este tutorial, esto se denomina el elemento Web de los empleados de presentación.</span><span class="sxs-lookup"><span data-stu-id="930be-105">For this tutorial, this is called the Display Employees Web Part.</span></span> <span data-ttu-id="930be-106">Esta sección proporciona instrucciones para crear este elemento Web.</span><span class="sxs-lookup"><span data-stu-id="930be-106">This section provides instructions to create this Web Part.</span></span> <span data-ttu-id="930be-107">Para obtener más información acerca de cómo crear elementos Web, vea "Personalizar listas de datos de negocio, elementos Web y sitios" en [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span><span class="sxs-lookup"><span data-stu-id="930be-107">For more information about creating Web Parts, see "Customize business data lists, Web Parts, and sites" at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
 <span data-ttu-id="930be-108">Debe crear una página de elementos Web antes de agregar los elementos Web.</span><span class="sxs-lookup"><span data-stu-id="930be-108">You must create a Web Part page before adding the Web Parts.</span></span>  
  
## <a name="creating-a-web-part-page"></a><span data-ttu-id="930be-109">Crear una página de elementos Web</span><span class="sxs-lookup"><span data-stu-id="930be-109">Creating a Web Part Page</span></span>  
 <span data-ttu-id="930be-110">Esta sección proporciona instrucciones para crear una página de elementos Web.</span><span class="sxs-lookup"><span data-stu-id="930be-110">This section provides instructions to create a Web Part page.</span></span>  
  
###  <a name="WebPart"></a><span data-ttu-id="930be-111">Para crear una página de elementos Web</span><span class="sxs-lookup"><span data-stu-id="930be-111">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="930be-112">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="930be-112">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="930be-113">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="930be-113">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="930be-114">En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="930be-114">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="930be-115">En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="930be-115">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="930be-116">![Menú para crear un elemento web](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="930be-116">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4.  <span data-ttu-id="930be-117">En la página Crear, en el **páginas Web** sección, haga clic en **página de elementos Web**.</span><span class="sxs-lookup"><span data-stu-id="930be-117">On the Create page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="930be-118">En la página nuevo elemento Web, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="930be-118">On the New Web Part page, do the following:</span></span>  
  
    1.  <span data-ttu-id="930be-119">En el **nombre** , escriba un nombre para la página.</span><span class="sxs-lookup"><span data-stu-id="930be-119">In the **Name** field, type a name for the page.</span></span> <span data-ttu-id="930be-120">Para este tutorial, escriba el nombre como **MS_SAMPLE_EMPLOYEE**.</span><span class="sxs-lookup"><span data-stu-id="930be-120">For this tutorial, type the name as **MS_SAMPLE_EMPLOYEE**.</span></span>  
  
    2.  <span data-ttu-id="930be-121">Seleccione el **sobrescribir si ya existe el archivo** casilla de verificación si desea sobrescribir páginas anteriores con el mismo nombre que la página nueva que cree.</span><span class="sxs-lookup"><span data-stu-id="930be-121">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the new page you create.</span></span>  
  
    3.  <span data-ttu-id="930be-122">En el **diseño** sección, desde el **elegir una plantilla de diseño** , seleccione un diseño para la página de elementos Web.</span><span class="sxs-lookup"><span data-stu-id="930be-122">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="930be-123">Para este tutorial, seleccione **página completa, Vertical**.</span><span class="sxs-lookup"><span data-stu-id="930be-123">For this tutorial, select **Full Page, Vertical**.</span></span>  
  
    4.  <span data-ttu-id="930be-124">En el **ubicación de almacenamiento** sección, en la **biblioteca de documentos** lista, haga clic en **plantillas de formulario**.</span><span class="sxs-lookup"><span data-stu-id="930be-124">In the **Save Location** section, in the **Document Library** list, click **Form Templates**.</span></span>  
  
    5.  <span data-ttu-id="930be-125">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="930be-125">Click **Create**.</span></span> <span data-ttu-id="930be-126">La siguiente ilustración muestra la página de elementos Web después de crearlo.</span><span class="sxs-lookup"><span data-stu-id="930be-126">The following figure shows the Web Part page after it is created.</span></span>  
  
         <span data-ttu-id="930be-127">![La nueva página de elemento Web](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23_Web_Part")</span><span class="sxs-lookup"><span data-stu-id="930be-127">![The new WebPart page](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23_Web_Part")</span></span>  
  
    6.  <span data-ttu-id="930be-128">Ahora debe agregar los elementos Web a esta página.</span><span class="sxs-lookup"><span data-stu-id="930be-128">You must now add the Web Parts to this page.</span></span>  
  
## <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="930be-129">Agregar un elemento Web de lista de datos de negocio</span><span class="sxs-lookup"><span data-stu-id="930be-129">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="930be-130">Ahora debe agregar un elemento Web de lista de datos de negocio a la página de elementos Web.</span><span class="sxs-lookup"><span data-stu-id="930be-130">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="930be-131">Con este elemento Web recuperará una lista de los registros de empleados de la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite que coincide con una expresión de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="930be-131">Using this Web Part you will retrieve a list of employee records from the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite that matches a search expression.</span></span> <span data-ttu-id="930be-132">Este elemento Web corresponde a la **buscador** instancia de método (*Finder_Instance*) que creó en el Editor de definición de catálogo de datos de Business.</span><span class="sxs-lookup"><span data-stu-id="930be-132">This Web Part corresponds to the **Finder** method instance (*Finder_Instance*) that you created in the Business Data Catalog Definition Editor.</span></span>  
  
#### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="930be-133">Para agregar un elemento Web de lista de datos de negocio</span><span class="sxs-lookup"><span data-stu-id="930be-133">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="930be-134">En la página MS_SAMPLE_EMPLOYEE, haga clic en **agregar un elemento Web**.</span><span class="sxs-lookup"><span data-stu-id="930be-134">On the MS_SAMPLE_EMPLOYEE page, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="930be-135">En el **agregar elementos Web** cuadro de diálogo, en la **datos económicos** sección, seleccione la **lista de datos económicos** casilla de verificación y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="930be-135">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="930be-136">![Opciones para crear un elemento Web de datos empresariales](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="930be-136">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="930be-137">En la parte de Web de recién agregado Business datos de lista, haga clic en el **abrir el panel de herramientas** vínculo.</span><span class="sxs-lookup"><span data-stu-id="930be-137">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="930be-138">![Abra el panel de herramientas para el elemento Web](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="930be-138">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="930be-139">El panel de herramientas de la lista de datos económicos se abre en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="930be-139">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="930be-140">En el **lista de datos económicos** sección, para la **tipo** , a continuación, haga clic en el **examinar** botón.</span><span class="sxs-lookup"><span data-stu-id="930be-140">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="930be-141">![Panel de herramientas de lista de datos de negocio](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24_BDC_Browse")</span><span class="sxs-lookup"><span data-stu-id="930be-141">![Business Data List tool pane](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24_BDC_Browse")</span></span>  
  
5.  <span data-ttu-id="930be-142">En el **selector de tipo de datos profesionales** cuadro de diálogo, seleccione la **MS_SAMPLE_EMPLOYEE_Instance** aplicación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="930be-142">In the **Business Data Type Picker** dialog box, select the **MS_SAMPLE_EMPLOYEE_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="930be-143">![Seleccione la instancia de aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25_BDC_Picker")</span><span class="sxs-lookup"><span data-stu-id="930be-143">![Select the application instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25_BDC_Picker")</span></span>  
  
6.  <span data-ttu-id="930be-144">Expanda el **apariencia** nodo y en el **título** , escriba un título para el elemento Web.</span><span class="sxs-lookup"><span data-stu-id="930be-144">Expand the **Appearance** node, and in the **Title** box, type a title for the Web Part.</span></span> <span data-ttu-id="930be-145">Para este elemento Web, escriba **lista de empleados**.</span><span class="sxs-lookup"><span data-stu-id="930be-145">For this Web Part, type **Employee List**.</span></span>  
  
7.  <span data-ttu-id="930be-146">En el panel de herramientas de la lista de datos económicos, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="930be-146">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="930be-147">El elemento Web de lista de datos de negocio ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="930be-147">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="930be-148">![Elemento Web de lista de datos económicos](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26_BDC_WebPart")</span><span class="sxs-lookup"><span data-stu-id="930be-148">![Business Data List Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26_BDC_WebPart")</span></span>  
  
8.  <span data-ttu-id="930be-149">El elemento Web se enumeran los campos que se devuelven mediante la ejecución de la operación de selección en la tabla de interfaz MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="930be-149">The Web Part lists the fields that are returned by executing the Select operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="930be-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="930be-150">See Also</span></span>  
 <span data-ttu-id="930be-151">[Paso 3: Crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md) </span><span class="sxs-lookup"><span data-stu-id="930be-151">[Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md) </span></span>  
 [<span data-ttu-id="930be-152">Escenario 2: Realizar búsquedas mediante el elemento Web de cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="930be-152">Scenario 2: Search Using the Search Box Web Part</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)