---
title: 'Paso 3: Asignar un nombre seguro al ensamblado | Microsoft Docs'
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
ms.openlocfilehash: 591423d04d8551620036e94a6ec780271e04feec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012629"
---
# <a name="step-3-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="aa4a5-102">Paso 3: Asignar un nombre seguro al ensamblado</span><span class="sxs-lookup"><span data-stu-id="aa4a5-102">Step 3: Assign a Strong Name to the Assembly</span></span>
<span data-ttu-id="aa4a5-103">En este paso, creará y asignar un nombre seguro para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-103">In this step, you create and assign a strong name for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] assembly.</span></span> <span data-ttu-id="aa4a5-104">Un ensamblado con nombre seguro proporciona varias ventajas de seguridad y es necesario para implementar el proyecto en la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="aa4a5-104">A strong-named assembly provides several security benefits and is required in order to deploy your project in the global assembly cache (GAC).</span></span> <span data-ttu-id="aa4a5-105">Un nombre seguro garantiza la exclusividad del ensamblado mediante la asignación de una firma digital y un único par de claves.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span> <span data-ttu-id="aa4a5-106">Además, esto protege el linaje del ensamblado al garantizar que nadie puede generar una versión posterior del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-106">This also protects the lineage of the assembly by ensuring that no one can generate a subsequent version of the assembly.</span></span> <span data-ttu-id="aa4a5-107">Por último, un nombre seguro proporciona una comprobación de integridad importante para garantizar que el contenido del ensamblado no ha cambiado desde que se compiló.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-107">Lastly, a strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since you built it.</span></span>  
  
### <a name="to-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="aa4a5-108">Para asignar un nombre seguro al ensamblado</span><span class="sxs-lookup"><span data-stu-id="aa4a5-108">To assign a strong name to the assembly</span></span>  
  
1. <span data-ttu-id="aa4a5-109">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-109">Start **Visual Studio Command Prompt**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="aa4a5-110">Si ya ha creado una clave de nombre seguro, puede volver a usar.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-110">If you have already created a strong name key, you can reuse it.</span></span>  
  
2. <span data-ttu-id="aa4a5-111">En el símbolo del sistema, vaya a<strong>\<*unidad*\>: \Tutorial\BTAHL7V22Common</strong> (donde \< *unidad* \> es la letra de unidad de instalación) y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-111">At the command prompt, move to<strong>\<*drive*\>:\Tutorial\BTAHL7V22Common</strong> (where \<*drive*\> is your installation drive letter) and then press **Enter**.</span></span>  
  
3. <span data-ttu-id="aa4a5-112">En el símbolo del sistema, escriba **sn – k key.snk**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-112">At the command prompt, type **sn –k key.snk**, and then press **Enter**.</span></span> <span data-ttu-id="aa4a5-113">Aparece un mensaje indicando que [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] escribió el par de claves en el archivo de clave de key.snk.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-113">A message appears indicating that [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] wrote the key pair to the key file key.snk.</span></span>  
  
4. <span data-ttu-id="aa4a5-114">En el Explorador de soluciones, haga clic en el **BTAHL7V22Common** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-114">In Solution Explorer, right-click the **BTAHL7V22Common** project, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="aa4a5-115">En el cuadro de diálogo páginas de propiedades BTAHL7V22Common, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-115">In the BTAHL7V22Common Property Pages dialog box, click **Assembly**.</span></span>  
  
6. <span data-ttu-id="aa4a5-116">En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="aa4a5-116">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
7. <span data-ttu-id="aa4a5-117">En el cuadro de diálogo de archivo de clave de ensamblado, vaya a  **\< *unidad*\>: \Tutorial\BTAHL7V22Common\key.snk**, haga clic en **abierto**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-117">In the Assembly Key File dialog box, browse to **\<*drive*\>:\Tutorial\BTAHL7V22Common\key.snk**, click **Open**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="aa4a5-118">En el Explorador de soluciones, haga clic en **BTAHL7V22Common**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-118">In Solution Explorer, right-click **BTAHL7V22Common**, and then click **Deploy**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="aa4a5-119"> crea un ensamblado que puede hacer referencia desde su próximo proyecto.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-119"> creates an assembly that you can reference from your next project.</span></span>  
  
9. <span data-ttu-id="aa4a5-120">Repita los pasos del 4 al 8 para el proyecto BTAHL7V2XCommon.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-120">Repeat steps 4 through 8 for the BTAHL7V2XCommon project.</span></span>  
  
   <span data-ttu-id="aa4a5-121">Continúe con [paso 4: crear los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="aa4a5-121">Proceed to [Step 4: Create the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa4a5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa4a5-122">See Also</span></span>  
 [<span data-ttu-id="aa4a5-123">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="aa4a5-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)