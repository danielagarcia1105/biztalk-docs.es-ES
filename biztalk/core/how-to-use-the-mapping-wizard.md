---
title: Cómo usar el Asistente para asignación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35b96cea-ead7-43de-8411-62d2c7d6620e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6b016eb0599924d4927868b6a19d3b57389e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257364"
---
# <a name="how-to-use-the-mapping-wizard"></a><span data-ttu-id="e9c59-102">Cómo usar el Asistente para asignaciones</span><span class="sxs-lookup"><span data-stu-id="e9c59-102">How to Use the Mapping Wizard</span></span>
<span data-ttu-id="e9c59-103">Esta versión de Inicio de sesión único empresarial incluye el Asistente para asignaciones, que permite crear asignaciones de forma sencilla para aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="e9c59-103">This version of Enterprise Single Sign-On includes the Mapping Wizard, which allows you to easily create mappings for affiliate applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9c59-104">Sólo puede usar el Asistente para asignaciones si el UserID externo está basado en la cuenta de dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="e9c59-104">You can only use the Mapping Wizard if the External UserID is based on the Windows domain account.</span></span>  
  
### <a name="to-start-the-mapping-wizard"></a><span data-ttu-id="e9c59-105">Para iniciar el Asistente para asignaciones</span><span class="sxs-lookup"><span data-stu-id="e9c59-105">To start the Mapping Wizard</span></span>  
  
1.  <span data-ttu-id="e9c59-106">Abra el Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="e9c59-106">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="e9c59-107">En el panel de ámbito, haga clic en **aplicaciones afiliadas**.</span><span class="sxs-lookup"><span data-stu-id="e9c59-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
3.  <span data-ttu-id="e9c59-108">Haga clic con el botón secundario en la aplicación afiliada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e9c59-108">Right click the appropriate affiliate application.</span></span>  
  
4.  <span data-ttu-id="e9c59-109">Haga clic en **crear asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="e9c59-109">Click **Create Mappings**.</span></span> <span data-ttu-id="e9c59-110">Aparecerá el Asistente para asignaciones.</span><span class="sxs-lookup"><span data-stu-id="e9c59-110">The Mapping Wizard appears.</span></span>  
  
5.  <span data-ttu-id="e9c59-111">**Asistente para la asignación**</span><span class="sxs-lookup"><span data-stu-id="e9c59-111">**Welcome to the Mapping Wizard**</span></span>  
  
    -   <span data-ttu-id="e9c59-112">Compruebe que se trata de la aplicación afiliada correcta y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e9c59-112">Verify that this is the correct affiliate application, and click **Next**.</span></span>  
  
6.  <span data-ttu-id="e9c59-113">**Opción del archivo de asignaciones** página</span><span class="sxs-lookup"><span data-stu-id="e9c59-113">**Mappings File Option** page</span></span>  
  
    -   <span data-ttu-id="e9c59-114">ENTSSO administra las asignaciones a través de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e9c59-114">ENTSSO manages mappings through an XML file.</span></span> <span data-ttu-id="e9c59-115">Puede elegir entre crear un archivo nuevo o usar uno existente.</span><span class="sxs-lookup"><span data-stu-id="e9c59-115">You can choose to create a new file or use an existing one.</span></span>  
  
7.  <span data-ttu-id="e9c59-116">**Ubicación de los archivos** página</span><span class="sxs-lookup"><span data-stu-id="e9c59-116">**Files Location** page</span></span>  
  
    -   <span data-ttu-id="e9c59-117">Seleccione los archivos que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="e9c59-117">Select the files to be used.</span></span>  
  
    -   <span data-ttu-id="e9c59-118">Debe hacer clic en **validar** para validar los archivos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e9c59-118">You must click **Validate** to validate the files before proceeding.</span></span> <span data-ttu-id="e9c59-119">El estado de validación aparece en la **estado** ventana.</span><span class="sxs-lookup"><span data-stu-id="e9c59-119">The validation status appears in the **Status** window.</span></span>  
  
8.  <span data-ttu-id="e9c59-120">**Cuentas** página</span><span class="sxs-lookup"><span data-stu-id="e9c59-120">**Accounts** page</span></span>  
  
    -   <span data-ttu-id="e9c59-121">Elija una o varias cuentas para generar el archivo de asignaciones nuevo y haga clic en **validar**.</span><span class="sxs-lookup"><span data-stu-id="e9c59-121">Choose one or more accounts to generate the new mappings file, and click **Validate**.</span></span>  
  
9. <span data-ttu-id="e9c59-122">**Nombre de usuario externo** página</span><span class="sxs-lookup"><span data-stu-id="e9c59-122">**External User Name** page</span></span>  
  
    -   <span data-ttu-id="e9c59-123">Defina cómo se generará el nombre de usuario externo desde la cuenta de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="e9c59-123">Define how the external user name is generated from the Windows user account.</span></span> <span data-ttu-id="e9c59-124">Cuando realice las selecciones en los cuadros, puede ver cómo aparecerán los nombres en el **ejemplo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="e9c59-124">As you make selections in the boxes, you can see how the names will appear in the **Example** box.</span></span>  
  
10. <span data-ttu-id="e9c59-125">**Generar** página</span><span class="sxs-lookup"><span data-stu-id="e9c59-125">**Generate** page</span></span>  
  
    -   <span data-ttu-id="e9c59-126">Haga clic en **iniciar** para generar el archivo de asignaciones.</span><span class="sxs-lookup"><span data-stu-id="e9c59-126">Click **Start** to generate the mappings file.</span></span> <span data-ttu-id="e9c59-127">(En la página siguiente, tendrá la oportunidad de ver o editar el archivo según sea necesario antes de que se creen las asignaciones). Los resultados se muestran en las tres ventanas siguientes.</span><span class="sxs-lookup"><span data-stu-id="e9c59-127">(You will have an opportunity on the next page to view or edit the file as necessary before mappings are created.) Results are displayed in the three windows below.</span></span>  
  
    -   <span data-ttu-id="e9c59-128">El **número** de asignaciones en las cuentas seleccionadas es una aproximación, porque las cuentas pueden estar anidadas en otras cuentas.</span><span class="sxs-lookup"><span data-stu-id="e9c59-128">The **Number** of mappings in selected accounts is an approximation, because accounts may be nested in other accounts.</span></span>  
  
    -   <span data-ttu-id="e9c59-129">Haga clic en **Ver archivo de registro** para examinar los errores o advertencias que pudieran haberse producido.</span><span class="sxs-lookup"><span data-stu-id="e9c59-129">Click **View Log File** to examine any errors or warnings that might have occurred.</span></span>  
  
11. <span data-ttu-id="e9c59-130">**Opciones de** página</span><span class="sxs-lookup"><span data-stu-id="e9c59-130">**Options** page</span></span>  
  
    -   <span data-ttu-id="e9c59-131">Su archivo se ha creado.</span><span class="sxs-lookup"><span data-stu-id="e9c59-131">Your file has been created.</span></span> <span data-ttu-id="e9c59-132">Haga clic en **ver o editar el archivo de asignación** si lo desea.</span><span class="sxs-lookup"><span data-stu-id="e9c59-132">Click **View/Edit Mappings File** if desired.</span></span>  
  
    -   <span data-ttu-id="e9c59-133">Haga clic en **habilite las asignaciones de** si desea que las asignaciones que se habilitarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e9c59-133">Click **Enable mappings** if you want the mappings to be automatically enabled.</span></span> <span data-ttu-id="e9c59-134">(Si no selecciona esta opción, tendrá que habilitarlas manualmente).</span><span class="sxs-lookup"><span data-stu-id="e9c59-134">(If you do not click this, you will have to enable them manually.)</span></span>  
  
    -   <span data-ttu-id="e9c59-135">Haga clic en **establecer contraseña** para establecer automáticamente la contraseña para estas asignaciones.</span><span class="sxs-lookup"><span data-stu-id="e9c59-135">Click **Set Password** to automatically set the password for these mappings.</span></span>  
  
12. <span data-ttu-id="e9c59-136">**Crear** página</span><span class="sxs-lookup"><span data-stu-id="e9c59-136">**Create** page</span></span>  
  
    -   <span data-ttu-id="e9c59-137">Antes de crear las asignaciones, haga clic en **Ver archivo de asignaciones** si lo desea.</span><span class="sxs-lookup"><span data-stu-id="e9c59-137">Before creating the mappings, click **View Mappings File** if desired.</span></span>  
  
    -   <span data-ttu-id="e9c59-138">Cuando esté listo, haga clic en **iniciar** para realizar la operación de asignación.</span><span class="sxs-lookup"><span data-stu-id="e9c59-138">When you are ready, click **Start** to perform the mapping operation.</span></span> <span data-ttu-id="e9c59-139">Su estado aparece en los tres cuadros siguientes.</span><span class="sxs-lookup"><span data-stu-id="e9c59-139">Your status is displayed in the three boxes below.</span></span>  
  
    -   <span data-ttu-id="e9c59-140">Haga clic en **Ver archivo de registro** para examinar los errores o advertencias que pudieran haberse producido.</span><span class="sxs-lookup"><span data-stu-id="e9c59-140">Click **View Log File** to examine any errors or warnings that might have occurred.</span></span>  
  
13. <span data-ttu-id="e9c59-141">**Pantalla Finalización del Asistente para asignaciones**</span><span class="sxs-lookup"><span data-stu-id="e9c59-141">**Completing the Mapping Wizard screen**</span></span>  
  
14. <span data-ttu-id="e9c59-142">Seleccione las opciones que desee y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e9c59-142">Select any options desired, and then click **Finish**.</span></span>