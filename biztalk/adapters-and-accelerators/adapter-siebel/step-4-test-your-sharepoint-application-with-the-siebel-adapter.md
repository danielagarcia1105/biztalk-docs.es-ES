---
title: 'Paso 4: Prueba la aplicación de SharePoint con el adaptador de Siebel | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec1392fa-fdc1-42be-b4dc-75a55d8fa400
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85cebcafcdf768686ed3f7382a0838db5062d96b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222188"
---
# <a name="step-4-test-your-sharepoint-application-with-the-siebel-adapter"></a><span data-ttu-id="77b54-102">Paso 4: Probar la aplicación de SharePoint con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="77b54-102">Step 4: Test Your SharePoint Application with the Siebel adapter</span></span>
<span data-ttu-id="77b54-103">![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="77b54-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="77b54-104">**Tiempo en completarse:** 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="77b54-104">**Time to complete:** 5 minutes.</span></span>  
  
 <span data-ttu-id="77b54-105">**Objetivo:** después de haber agregado elementos Web en el sitio de SharePoint y crea una aplicación, debe probar la aplicación mediante la recuperación de algunos datos en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="77b54-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the Siebel system.</span></span> <span data-ttu-id="77b54-106">Esta sección proporciona instrucciones sobre cómo usar la aplicación para recuperar los datos en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="77b54-106">This section provides instructions on how to use the application to retrieve the data from the Siebel system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="77b54-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="77b54-107">Prerequisites</span></span>  
 <span data-ttu-id="77b54-108">Deberá haber creado la página de elementos Web que contiene los elementos Web adecuado para recuperar los datos empresariales.</span><span class="sxs-lookup"><span data-stu-id="77b54-108">You should have created the Web Part page containing the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="77b54-109">Vea [paso 3: crear una aplicación de SharePoint para recuperar datos de Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="77b54-109">See [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md).</span></span>  
  
### <a name="to-test-the-sharepoint-application"></a><span data-ttu-id="77b54-110">Para probar la aplicación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="77b54-110">To test the SharePoint application</span></span>  
  
1.  <span data-ttu-id="77b54-111">Inicie Administración Central de SharePoint 3.0.</span><span class="sxs-lookup"><span data-stu-id="77b54-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="77b54-112">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.</span><span class="sxs-lookup"><span data-stu-id="77b54-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="77b54-113">En el panel de navegación izquierdo, haga clic en el nombre del SSP en la que se creó la aplicación.</span><span class="sxs-lookup"><span data-stu-id="77b54-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="77b54-114">En el panel izquierdo, haga clic en **ver todo el contenido del sitio**.</span><span class="sxs-lookup"><span data-stu-id="77b54-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="77b54-115">En el panel derecho, haga clic en **plantillas de formulario**.</span><span class="sxs-lookup"><span data-stu-id="77b54-115">From the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="77b54-116">En el **formulario categoría** lista, haga clic en **cuenta de Siebel**.</span><span class="sxs-lookup"><span data-stu-id="77b54-116">In the **Form Category** list, click **Siebel Account**.</span></span> <span data-ttu-id="77b54-117">Ha especificado este nombre al crear la página de elementos Web.</span><span class="sxs-lookup"><span data-stu-id="77b54-117">You specified this name while creating the Web Part page.</span></span> <span data-ttu-id="77b54-118">En la siguiente ilustración muestra la página de elementos Web que ha creado.</span><span class="sxs-lookup"><span data-stu-id="77b54-118">The following figure shows the Web Part page that you created.</span></span>  
  
     <span data-ttu-id="77b54-119">![Página de elemento Web completada](../../adapters-and-accelerators/adapter-siebel/media/a0bfe7af-0246-4f0b-aa0d-0ee084456003.gif "a0bfe7af-0246-4f0b-aa0d-0ee084456003")</span><span class="sxs-lookup"><span data-stu-id="77b54-119">![Completed Web Part page](../../adapters-and-accelerators/adapter-siebel/media/a0bfe7af-0246-4f0b-aa0d-0ee084456003.gif "a0bfe7af-0246-4f0b-aa0d-0ee084456003")</span></span>  
  
5.  <span data-ttu-id="77b54-120">Consultar el componente de negocio de cuenta en función de una cadena de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="77b54-120">Query the Account business component based on a search string.</span></span> <span data-ttu-id="77b54-121">Por ejemplo, especifique la expresión de búsqueda `[Name] LIKE ‘W*’`.</span><span class="sxs-lookup"><span data-stu-id="77b54-121">For example, specify the search expression `[Name] LIKE ‘W*’`.</span></span> <span data-ttu-id="77b54-122">Para ello:</span><span class="sxs-lookup"><span data-stu-id="77b54-122">To do so:</span></span>  
  
    1.  <span data-ttu-id="77b54-123">En el **lista de cuentas de** sección, en la primera lista, seleccione **SearchExpression**y, a continuación, seleccione **es igual a**.</span><span class="sxs-lookup"><span data-stu-id="77b54-123">In the **Account List** section, from the first list, select **SearchExpression**, and then select **is equal to**.</span></span>  
  
    2.  <span data-ttu-id="77b54-124">En el campo de texto, escriba `[Name] LIKE ‘W*’`.</span><span class="sxs-lookup"><span data-stu-id="77b54-124">In the text field, type `[Name] LIKE ‘W*’`.</span></span>  
  
    3.  <span data-ttu-id="77b54-125">Haga clic en **recuperar datos** vincular, o presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="77b54-125">Click **Retrieve Data** link, or press ENTER.</span></span> <span data-ttu-id="77b54-126">La siguiente ilustración muestra los registros recuperados en el sistema Siebel que cumplen los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="77b54-126">The following figure shows the records retrieved from the Siebel system that satisfy the search criteria.</span></span>  
  
         <span data-ttu-id="77b54-127">![Buscar resultados en el sistema Siebel](../../adapters-and-accelerators/adapter-siebel/media/6c4721ac-c7bc-4626-9ee0-55cf322026cf.gif "6c4721ac-c7bc-4626-9ee0-55cf322026cf")</span><span class="sxs-lookup"><span data-stu-id="77b54-127">![Search results from the Siebel system](../../adapters-and-accelerators/adapter-siebel/media/6c4721ac-c7bc-4626-9ee0-55cf322026cf.gif "6c4721ac-c7bc-4626-9ee0-55cf322026cf")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b54-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="77b54-128">See Also</span></span>  
 [<span data-ttu-id="77b54-129">Tutorial 1: Presentar datos desde un sistema Siebel en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="77b54-129">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)