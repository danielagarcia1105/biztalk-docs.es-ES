---
title: "Implementación de esquemas de A4SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, A4SWIFT
- deploying, A4SWIFT schemas
- A4SWIFT, deploying schemas
- schemas, deploying
ms.assetid: a6aed2cd-3578-442e-ab1e-8284cc5f7b72
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc89b26d0eee970268d5e9084cd0827d3100fd7b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="deploying-a4swift-schemas"></a><span data-ttu-id="fe579-102">Implementación de esquemas de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="fe579-102">Deploying A4SWIFT Schemas</span></span>
<span data-ttu-id="fe579-103">Debe implementar los esquemas para los mensajes SWIFT que desea intercambiar.</span><span class="sxs-lookup"><span data-stu-id="fe579-103">You must deploy schemas for the SWIFT messages that you want to exchange.</span></span>  
  
 <span data-ttu-id="fe579-104">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="fe579-104">**Summary**</span></span>  
  
 <span data-ttu-id="fe579-105">Implementar los siguientes esquemas:</span><span class="sxs-lookup"><span data-stu-id="fe579-105">Deploy the following schemas:</span></span>  
  
-   <span data-ttu-id="fe579-106">SWIFT Types.xsd Base</span><span class="sxs-lookup"><span data-stu-id="fe579-106">SWIFT Base Types.xsd</span></span>  
  
-   <span data-ttu-id="fe579-107">SWIFT Types.xsd datos comunes</span><span class="sxs-lookup"><span data-stu-id="fe579-107">SWIFT Common Data Types.xsd</span></span>  
  
-   <span data-ttu-id="fe579-108">Esquema específico para un tipo de mensaje, por ejemplo, MT103.xsd</span><span class="sxs-lookup"><span data-stu-id="fe579-108">Specific schema for a message type, for example, MT103.xsd</span></span>  
  
### <a name="to-create-a-strong-named-swift-project"></a><span data-ttu-id="fe579-109">Para crear un proyecto SWIFT con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="fe579-109">To create a strong-named SWIFT project</span></span>  
  
1.  <span data-ttu-id="fe579-110">En Visual Studio, haga clic en **archivo**, seleccione **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fe579-110">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="fe579-111">En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** panel, seleccione la **proyectos de BizTalk** carpeta.</span><span class="sxs-lookup"><span data-stu-id="fe579-111">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  
  
3.  <span data-ttu-id="fe579-112">En el **plantillas** panel, seleccione **proyecto vacío de servidor BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="fe579-112">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  
  
4.  <span data-ttu-id="fe579-113">En el **nombre** , escriba el nombre que desea para el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fe579-113">In the **Name** box, type the name you want for the project name.</span></span>  
  
5.  <span data-ttu-id="fe579-114">En el **solución** cuadro, seleccione **crear nueva solución**.</span><span class="sxs-lookup"><span data-stu-id="fe579-114">In the **Solution** box, select **Create new Solution**.</span></span> <span data-ttu-id="fe579-115">En el **ubicación** cuadro, escriba la ubicación del proyecto que se va a agregar el proyecto de esquema.</span><span class="sxs-lookup"><span data-stu-id="fe579-115">In the **Location** box, enter the location of the project that you are adding the schema project to.</span></span>  
  
6.  <span data-ttu-id="fe579-116">Haga clic en **Aceptar** para abrir el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="fe579-116">Click **OK** to open the new project.</span></span>  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="fe579-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]Agrega un nuevo proyecto en el Explorador de soluciones y crea la carpeta del proyecto y los archivos en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="fe579-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] adds a new project to Solution Explorer, and creates the project folder and files in the folder specified.</span></span>  
  
7.  <span data-ttu-id="fe579-118">Inicie el símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fe579-118">Start Visual Studio command prompt.</span></span>  
  
8.  <span data-ttu-id="fe579-119">En el símbolo del sistema de Visual Studio, vaya a  **\<* unidad*\>: \Program Acelerador de BizTalk para SWIFT **.</span><span class="sxs-lookup"><span data-stu-id="fe579-119">At the Visual Studio command prompt, browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT**.</span></span>  
  
9. <span data-ttu-id="fe579-120">En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fe579-120">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="fe579-121">Asegúrese de que se muestra un mensaje en la ventana de símbolo del sistema que indica que se ha escrito un par de claves para key.snk.</span><span class="sxs-lookup"><span data-stu-id="fe579-121">Ensure that a message is displayed in the command-prompt window indicating that a key pair was written to key.snk.</span></span>  
  
10. <span data-ttu-id="fe579-122">En el Explorador de soluciones, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fe579-122">In Solution Explorer, right-click your project name, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="fe579-123">En el panel izquierdo de la **páginas de propiedades** cuadro de diálogo, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="fe579-123">In the left pane of the **Property Pages** dialog box, click **Assembly**.</span></span>  
  
12. <span data-ttu-id="fe579-124">En el panel derecho de la **páginas de propiedades** cuadro de diálogo, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="fe579-124">In the right pane of the **Property Pages** dialog box, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis () button.</span></span>  
  
13. <span data-ttu-id="fe579-125">En el **archivo de clave de ensamblado** cuadro de diálogo, vaya a  **\<* unidad*\>: \Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)], haga clic en **key.snk**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="fe579-125">In the **Assembly Key File** dialog box, browse to **\<*drive*\>:\Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)], click **key.snk**, and then click **Open**.</span></span>  
  
14. <span data-ttu-id="fe579-126">En el **páginas de propiedades** cuadro de diálogo, haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="fe579-126">In the **Property Pages** dialog box, click **OK** to save your changes.</span></span>  
  
### <a name="to-add-a-swift-schema"></a><span data-ttu-id="fe579-127">Para agregar un esquema SWIFT</span><span class="sxs-lookup"><span data-stu-id="fe579-127">To add a SWIFT schema</span></span>  
  
1.  <span data-ttu-id="fe579-128">En el Explorador de soluciones de Visual Studio, abra el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fe579-128">In Solution Explorer of Visual Studio, open your project.</span></span>  
  
2.  <span data-ttu-id="fe579-129">Haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="fe579-129">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span>  
  
3.  <span data-ttu-id="fe579-130">En el **Agregar elemento existente** cuadro de diálogo el:\\**programa Files\Microsoft BizTalk Accelerator para SWIFT \<versión\> Pack\SWIFT Messages\A4SWIFT-SRGdemensaje\<versión\>\Base esquemas**.</span><span class="sxs-lookup"><span data-stu-id="fe579-130">In the **Add Existing Item** dialog box, in the :\\**Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Schemas**.</span></span> <span data-ttu-id="fe579-131">Seleccione el **SWIFT Base Types.xsd** y **Types.xsd de datos común de SWIFT** esquemas y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="fe579-131">Select the **SWIFT Base Types.xsd** and **SWIFT Common Data Types.xsd** schemas, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="fe579-132">Haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="fe579-132">Right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
5.  <span data-ttu-id="fe579-133">En el **Agregar elemento existente** cuadro de diálogo, en la **buscar en** cuadro de lista desplegable, desplácese a  **\<unidad\>: \Program Acelerador de BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category n\MTxxx**.</span><span class="sxs-lookup"><span data-stu-id="fe579-133">In the **Add Existing Item** dialog box, in the **Look in** drop-down box, move to **\<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category n\MTxxx**.</span></span> <span data-ttu-id="fe579-134">Seleccionar un esquema para un tipo de mensaje, por ejemplo **MT103.xsd**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="fe579-134">Select a schema for a message type, for instance **MT103.xsd**, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe579-135">A4SWIFT agrega el esquema para el proyecto, como se muestra en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="fe579-135">A4SWIFT adds the schema for your project, as shown in Solution Explorer.</span></span>  
  
6.  <span data-ttu-id="fe579-136">En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Versión de compilación**.</span><span class="sxs-lookup"><span data-stu-id="fe579-136">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
7.  <span data-ttu-id="fe579-137">En el Explorador de soluciones, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="fe579-137">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>