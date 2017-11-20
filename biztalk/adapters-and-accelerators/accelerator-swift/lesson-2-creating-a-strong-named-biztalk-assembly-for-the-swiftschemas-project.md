---
title: "Lección 2: Crear un ensamblado de BizTalk con nombre seguro para el proyecto SWIFTSchemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28afb0b029924a49dfd9a1bff87c5c847157d669
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a><span data-ttu-id="a91b5-102">Lección 2: Crear un ensamblado de BizTalk con nombre seguro para el proyecto SWIFTSchemas</span><span class="sxs-lookup"><span data-stu-id="a91b5-102">Lesson 2: Creating a Strong-Named BizTalk Assembly for the SWIFTSchemas Project</span></span>
<span data-ttu-id="a91b5-103">En esta lección, creará un nombre seguro en el que se compilan e implementan los ensamblados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a91b5-103">In this lesson, you create a strong name upon which the BizTalk assemblies are compiled and deployed.</span></span> <span data-ttu-id="a91b5-104">Un ensamblado con nombre seguro ofrece varias ventajas de seguridad:</span><span class="sxs-lookup"><span data-stu-id="a91b5-104">A strong-named assembly provides several security benefits:</span></span>  
  
-   <span data-ttu-id="a91b5-105">Un nombre seguro garantiza la exclusividad del ensamblado mediante la asignación de una firma digital y un único par de claves.</span><span class="sxs-lookup"><span data-stu-id="a91b5-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span>  
  
-   <span data-ttu-id="a91b5-106">Un nombre seguro protege el linaje del ensamblado al garantizar que nadie más puede generar una versión posterior del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a91b5-106">A strong name protects the lineage of the assembly by ensuring that no one else can generate a subsequent version of the assembly.</span></span>  
  
-   <span data-ttu-id="a91b5-107">Un nombre seguro proporciona una comprobación de integridad sólida para garantizar que el contenido del ensamblado no ha cambiado desde la última compilación.</span><span class="sxs-lookup"><span data-stu-id="a91b5-107">A strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since the last build.</span></span>  
  
 <span data-ttu-id="a91b5-108">Puede generar un archivo de clave mediante la herramienta de nombre seguro (sn.exe) que se incluye con [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] o [!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a91b5-108">You can generate a key file by using the strong name tool (sn.exe) that comes with [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] or the [!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)].</span></span>  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a><span data-ttu-id="a91b5-109">Para crear un ensamblado de BizTalk con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="a91b5-109">To create a strong-named BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="a91b5-110">Inicie el símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a91b5-110">Start Visual Studio command prompt.</span></span>  
  
2.  <span data-ttu-id="a91b5-111">En el símbolo del sistema de Visual Studio, desplácese hasta la \< *unidad*>: \labs carpeta.</span><span class="sxs-lookup"><span data-stu-id="a91b5-111">At the Visual Studio command prompt, browse to the \<*drive*>:\labs folder.</span></span>  
  
3.  <span data-ttu-id="a91b5-112">En el símbolo del sistema, escriba **sn – k swift.snk**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a91b5-112">At the command prompt, type **sn –k swift.snk**, and then press ENTER.</span></span> <span data-ttu-id="a91b5-113">Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="a91b5-113">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a91b5-114">Si no aparece el mensaje correcto, use Visual Studio para solucionar problemas de su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a91b5-114">If the correct message does not appear, use Visual Studio to troubleshoot your assembly.</span></span>  
  
4.  <span data-ttu-id="a91b5-115">En el Explorador de soluciones, haga clic en el **SWIFTSchemas** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a91b5-115">In Solution Explorer, right-click the **SWIFTSchemas** project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="a91b5-116">En el cuadro de diálogo páginas de propiedades de SWIFTSchemas, asegúrese de que **propiedades comunes** está expandido y, a continuación, seleccione **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="a91b5-116">In the SWIFTSchemas Property Pages dialog box, ensure that **Common Properties** is expanded, and then select **Assembly**.</span></span>  
  
6.  <span data-ttu-id="a91b5-117">Desplácese hacia abajo en las propiedades del ensamblado en el panel derecho y en el **nombre seguro** sección, haga clic en el cuadro a la derecha del **archivo de clave de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="a91b5-117">Scroll down the assembly properties in the right pane, and in the **Strong name** section, click the box to the right of **Assembly Key File**.</span></span> <span data-ttu-id="a91b5-118">Haga clic en el botón de puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="a91b5-118">Click the ellipsis button.</span></span>  
  
7.  <span data-ttu-id="a91b5-119">En el cuadro de diálogo de archivo de clave de ensamblado, vaya a  **\<* unidad*: > \labs**.</span><span class="sxs-lookup"><span data-stu-id="a91b5-119">In the Assembly Key File dialog box, browse to **\<*drive*:>\labs**.</span></span>  
  
8.  <span data-ttu-id="a91b5-120">Seleccione el **swift.snk** de archivos como el archivo de clave y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="a91b5-120">Select the **swift.snk** file as the key file, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="a91b5-121">En el cuadro de diálogo páginas de propiedades de SWIFTSchemas, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a91b5-121">In the SWIFTSchemas Property Pages dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="a91b5-122">En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a91b5-122">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="a91b5-123">Continúe con [lección 3: agregar esquemas SWIFT a un proyecto](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md).</span><span class="sxs-lookup"><span data-stu-id="a91b5-123">Proceed to [Lesson 3: Adding SWIFT Schemas to a Project](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md).</span></span>