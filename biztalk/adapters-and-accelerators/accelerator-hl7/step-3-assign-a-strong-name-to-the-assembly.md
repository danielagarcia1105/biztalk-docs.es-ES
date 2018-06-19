---
title: 'Paso 3: Asignar un nombre seguro al ensamblado | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies
- message enrichment tutorial, strong name assemblies
- strong name assemblies
ms.assetid: 8709e4e1-b428-42af-ba3c-08225c17a9eb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57368dbbb2d8ecaa6621707ea7b989bf7f5b005d
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "26004957"
---
# <a name="step-3-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="f16a0-102">Paso 3: Asignar un nombre seguro al ensamblado</span><span class="sxs-lookup"><span data-stu-id="f16a0-102">Step 3: Assign a Strong Name to the Assembly</span></span>
<span data-ttu-id="f16a0-103">En este paso, creará y asignar un nombre seguro para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f16a0-103">In this step, you create and assign a strong name for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] assembly.</span></span> <span data-ttu-id="f16a0-104">Un ensamblado con nombre seguro ofrece varias ventajas de seguridad y es necesario para implementar el proyecto en la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="f16a0-104">A strong-named assembly provides several security benefits and is required in order to deploy your project in the global assembly cache (GAC).</span></span> <span data-ttu-id="f16a0-105">Un nombre seguro garantiza la exclusividad del ensamblado mediante la asignación de una firma digital y un único par de claves.</span><span class="sxs-lookup"><span data-stu-id="f16a0-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span> <span data-ttu-id="f16a0-106">Además, esto protege el linaje del ensamblado al garantizar que nadie puede generar una versión posterior del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f16a0-106">This also protects the lineage of the assembly by ensuring that no one can generate a subsequent version of the assembly.</span></span> <span data-ttu-id="f16a0-107">Por último, un nombre seguro proporciona una comprobación de integridad sólida para garantizar que el contenido del ensamblado no ha cambiado desde que se compiló.</span><span class="sxs-lookup"><span data-stu-id="f16a0-107">Lastly, a strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since you built it.</span></span>  
  
### <a name="to-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="f16a0-108">Para asignar un nombre seguro al ensamblado</span><span class="sxs-lookup"><span data-stu-id="f16a0-108">To assign a strong name to the assembly</span></span>  
  
1.  <span data-ttu-id="f16a0-109">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="f16a0-109">Start **Visual Studio Command Prompt**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f16a0-110">Si ya ha creado una clave de nombre seguro, puede volver a usarla.</span><span class="sxs-lookup"><span data-stu-id="f16a0-110">If you have already created a strong name key, you can reuse it.</span></span>  
  
2.  <span data-ttu-id="f16a0-111">En el símbolo del sistema, vaya a**\<*unidad*\>: \Tutorial\BTAHL7V22Common** (donde \< *unidad* \> es la letra de unidad de instalación) y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f16a0-111">At the command prompt, move to**\<*drive*\>:\Tutorial\BTAHL7V22Common** (where \<*drive*\> is your installation drive letter) and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="f16a0-112">En el símbolo del sistema, escriba **sn – k key.snk**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f16a0-112">At the command prompt, type **sn –k key.snk**, and then press **Enter**.</span></span> <span data-ttu-id="f16a0-113">Aparece un mensaje indicando que [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] el par de claves se escribió en el archivo de clave key.snk.</span><span class="sxs-lookup"><span data-stu-id="f16a0-113">A message appears indicating that [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] wrote the key pair to the key file key.snk.</span></span>  
  
4.  <span data-ttu-id="f16a0-114">En el Explorador de soluciones, haga clic en el **BTAHL7V22Common** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f16a0-114">In Solution Explorer, right-click the **BTAHL7V22Common** project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="f16a0-115">En el cuadro de diálogo páginas de propiedades de BTAHL7V22Common, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="f16a0-115">In the BTAHL7V22Common Property Pages dialog box, click **Assembly**.</span></span>  
  
6.  <span data-ttu-id="f16a0-116">En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="f16a0-116">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
7.  <span data-ttu-id="f16a0-117">En el cuadro de diálogo de archivo de clave de ensamblado, vaya a  **\< *unidad*\>: \Tutorial\BTAHL7V22Common\key.snk**, haga clic en **abiertos**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f16a0-117">In the Assembly Key File dialog box, browse to **\<*drive*\>:\Tutorial\BTAHL7V22Common\key.snk**, click **Open**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="f16a0-118">En el Explorador de soluciones, haga clic en **BTAHL7V22Common**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="f16a0-118">In Solution Explorer, right-click **BTAHL7V22Common**, and then click **Deploy**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="f16a0-119">crea un ensamblado que puede hacer referencia desde el proyecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="f16a0-119"> creates an assembly that you can reference from your next project.</span></span>  
  
9. <span data-ttu-id="f16a0-120">Repita los pasos del 4 al 8 para el proyecto BTAHL7V2XCommon.</span><span class="sxs-lookup"><span data-stu-id="f16a0-120">Repeat steps 4 through 8 for the BTAHL7V2XCommon project.</span></span>  
  
 <span data-ttu-id="f16a0-121">Continúe con [paso 4: crear los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="f16a0-121">Proceed to [Step 4: Create the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f16a0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f16a0-122">See Also</span></span>  
 [<span data-ttu-id="f16a0-123">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="f16a0-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)