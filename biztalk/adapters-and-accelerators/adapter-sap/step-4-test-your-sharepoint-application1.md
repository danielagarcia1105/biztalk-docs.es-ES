---
title: 'Paso 4: Probar la aplicación de SharePoint 1 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7ded5a5-88d5-40aa-814b-70bc0a7dcfa3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b8be51df02bd9796b41201c0495758c281e8f14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216636"
---
# <a name="step-4-test-your-sharepoint-application"></a><span data-ttu-id="7d929-102">Paso 4: Probar la aplicación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d929-102">Step 4: Test Your SharePoint Application</span></span>
<span data-ttu-id="7d929-103">![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="7d929-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="7d929-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="7d929-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="7d929-105">**Objetivo:** después de haber agregado elementos Web en el sitio de SharePoint y crea una aplicación, debe probar la aplicación mediante la recuperación de algunos datos desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="7d929-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the SAP system.</span></span> <span data-ttu-id="7d929-106">Este tema proporciona instrucciones sobre cómo usar la aplicación para recuperar los datos desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="7d929-106">This topic provides instructions on how to use the application to retrieve the data from the SAP system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7d929-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7d929-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="7d929-108">Deberá haber creado la página de elementos Web que contiene los elementos Web adecuado para recuperar los datos empresariales.</span><span class="sxs-lookup"><span data-stu-id="7d929-108">You should have created the Web Part page that contains the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="7d929-109">Vea [paso 3: crear una aplicación de SharePoint para recuperar datos de SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md).</span><span class="sxs-lookup"><span data-stu-id="7d929-109">See [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md).</span></span>  
  
### <a name="to-test-the-sharepoint-application"></a><span data-ttu-id="7d929-110">Para probar la aplicación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d929-110">To test the SharePoint application</span></span>  
  
1.  <span data-ttu-id="7d929-111">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="7d929-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="7d929-112">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="7d929-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="7d929-113">En el panel de navegación izquierdo, haga clic en el nombre del SSP en la que se creó la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d929-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="7d929-114">En el panel izquierdo, haga clic en **ver todo el contenido del sitio**.</span><span class="sxs-lookup"><span data-stu-id="7d929-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="7d929-115">En el panel derecho, haga clic en **plantillas de formulario**.</span><span class="sxs-lookup"><span data-stu-id="7d929-115">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="7d929-116">En el **formulario categoría** lista, haga clic en **Customer_SalesOrders**.</span><span class="sxs-lookup"><span data-stu-id="7d929-116">In the **Form Category** list, click **Customer_SalesOrders**.</span></span> <span data-ttu-id="7d929-117">Ha especificado este nombre cuando creaste la página de elementos Web.</span><span class="sxs-lookup"><span data-stu-id="7d929-117">You specified this name when you created the Web Part page.</span></span> <span data-ttu-id="7d929-118">En la siguiente ilustración muestra la página de elementos Web que ha creado.</span><span class="sxs-lookup"><span data-stu-id="7d929-118">The following figure shows the Web Part page that you created.</span></span>  
  
     <span data-ttu-id="7d929-119">![Página de elemento Web completada](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")</span><span class="sxs-lookup"><span data-stu-id="7d929-119">![Completed Web Part page](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")</span></span>  
  
5.  <span data-ttu-id="7d929-120">Buscar los clientes basándose en una cadena de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d929-120">Search for customers based on a search string.</span></span> <span data-ttu-id="7d929-121">Por ejemplo, buscar los clientes cuyo nombre empieza por "John E".</span><span class="sxs-lookup"><span data-stu-id="7d929-121">For example, search for customers with names starting with "John E".</span></span> <span data-ttu-id="7d929-122">Para ello:</span><span class="sxs-lookup"><span data-stu-id="7d929-122">To do so:</span></span>  
  
    1.  <span data-ttu-id="7d929-123">En la sección de la lista de clientes, en la primera lista, haga clic en **CustomerName**.</span><span class="sxs-lookup"><span data-stu-id="7d929-123">In the Customer List section, from the first list, click **CustomerName**.</span></span>  
  
    2.  <span data-ttu-id="7d929-124">En la segunda lista, haga clic en **comienza con**.</span><span class="sxs-lookup"><span data-stu-id="7d929-124">From the second list, click **starts with**.</span></span>  
  
    3.  <span data-ttu-id="7d929-125">En el cuadro de texto, escriba **John E**.</span><span class="sxs-lookup"><span data-stu-id="7d929-125">In the text box, type **John E**.</span></span>  
  
    4.  <span data-ttu-id="7d929-126">Haga clic en el **recuperar datos** vincular o presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7d929-126">Click the **Retrieve Data** link or press ENTER.</span></span> <span data-ttu-id="7d929-127">La siguiente ilustración muestra los registros recuperados desde el sistema SAP que cumplen los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d929-127">The following figure shows the records retrieved from the SAP system that satisfy the search criteria.</span></span>  
  
         <span data-ttu-id="7d929-128">![Buscar resultados en el sistema SAP](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")</span><span class="sxs-lookup"><span data-stu-id="7d929-128">![Search results from the SAP system](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")</span></span>  
  
6.  <span data-ttu-id="7d929-129">Ahora puede ver los detalles de cualquier cliente en la lista y los pedidos de venta asociados con los clientes, en su caso.</span><span class="sxs-lookup"><span data-stu-id="7d929-129">You can now see the details of any customer in the list and the sales orders associated with the customers, if any.</span></span> <span data-ttu-id="7d929-130">Para ello, haga clic en el botón de opción en un número de cliente.</span><span class="sxs-lookup"><span data-stu-id="7d929-130">To do so, click the option button against a customer number.</span></span> <span data-ttu-id="7d929-131">Actualice la página para mostrar los detalles y los pedidos de venta para un cliente específico de los elementos Web correspondientes.</span><span class="sxs-lookup"><span data-stu-id="7d929-131">The page refreshes to present the details and the sales orders for a specific customer in the respective Web Parts.</span></span>  
  
     <span data-ttu-id="7d929-132">![Datos SAP presentados en SharePoint](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")</span><span class="sxs-lookup"><span data-stu-id="7d929-132">![SAP data presented on SharePoint](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")</span></span>  
  
     <span data-ttu-id="7d929-133">Si los detalles de los clientes y el pedido de venta asociado se muestran correctamente, ha completado correctamente el tutorial.</span><span class="sxs-lookup"><span data-stu-id="7d929-133">If the details of the customers and the associated sales order are displayed correctly, you have successfully completed the tutorial.</span></span> <span data-ttu-id="7d929-134">Si no hay ningún o datos incorrectos se muestran, compruebe con cuidado el trabajo para asegurarse de que ha realizado correctamente todas las tareas.</span><span class="sxs-lookup"><span data-stu-id="7d929-134">If no or incorrect data is displayed, carefully check your work to make sure you performed all the tasks correctly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="7d929-135">Resumen</span><span class="sxs-lookup"><span data-stu-id="7d929-135">Summary</span></span>  
 <span data-ttu-id="7d929-136">En este tutorial ha creado un servicio WCF para los artefactos SAP que desea tener acceso desde un SharePoint Portal.</span><span class="sxs-lookup"><span data-stu-id="7d929-136">In this tutorial you created a WCF service for the SAP artifacts you want to access from a SharePoint Portal.</span></span> <span data-ttu-id="7d929-137">También se crea una definición de aplicación para los artefactos SAP que se importa en un portal de SharePoint para crear elementos Web para presentar los datos de un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="7d929-137">You also created an application definition for the SAP artifacts that is imported into a SharePoint portal to create Web Parts to present data from an SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d929-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d929-138">See Also</span></span>  
 [<span data-ttu-id="7d929-139">Tutorial 1: Presentar datos desde un sistema SAP en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d929-139">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)