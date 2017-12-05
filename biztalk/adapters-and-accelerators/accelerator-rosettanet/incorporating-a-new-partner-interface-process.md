---
title: "Incorporación de un nuevo proceso de interfaz de socio comercial | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, PIP schemas
- PIP schemas
- PIP schemas, deploying
- PIP schemas, downloading
- creating, PIP schemas
- PIP schemas, creating
ms.assetid: 6a5fcbcb-c6aa-40c0-bcca-dd0c391e7f42
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bf80c8bb577f4ddc8aec3282805714a830c7d23
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="incorporating-a-new-partner-interface-process"></a><span data-ttu-id="69c42-102">Incorporación de un nuevo proceso de interfaz de socio comercial</span><span class="sxs-lookup"><span data-stu-id="69c42-102">Incorporating a New Partner Interface Process</span></span>
<span data-ttu-id="69c42-103">Puede incorporar un nuevo esquema de proceso de interfaz de socio (PIP) RosettaNet en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ensamblados.</span><span class="sxs-lookup"><span data-stu-id="69c42-103">You can incorporate a new RosettaNet Partner Interface Process (PIP) schema in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] assemblies.</span></span> <span data-ttu-id="69c42-104">Para ello:</span><span class="sxs-lookup"><span data-stu-id="69c42-104">You do so by:</span></span>  
  
-   <span data-ttu-id="69c42-105">Descargar el esquema PIP desde el sitio RosettaNet Web en [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span><span class="sxs-lookup"><span data-stu-id="69c42-105">Downloading the PIP schema from the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span>  
  
-   <span data-ttu-id="69c42-106">Implementar el esquema para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como parte de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Rnpip ensamblado o como parte de otro [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ensamblado.</span><span class="sxs-lookup"><span data-stu-id="69c42-106">Deploying the schema to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as part of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIPs assembly or as part of a separate [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] assembly.</span></span> <span data-ttu-id="69c42-107">Para obtener más información, consulte [BTARN extender a una PIP nueva](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md).</span><span class="sxs-lookup"><span data-stu-id="69c42-107">For more information, see [Extending BTARN with a New PIP](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md).</span></span>  
  
-   <span data-ttu-id="69c42-108">Crear un nuevo valor de configuración de proceso en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="69c42-108">Creating a new Process Configuration Setting in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="69c42-109">Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="69c42-109">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="69c42-110">El esquema descargado generalmente está en formato de .dtd, con una especificación de PIP acompañamiento de la organización RosettaNet como un archivo .doc.</span><span class="sxs-lookup"><span data-stu-id="69c42-110">The downloaded schema is generally in .dtd format, with an accompanying PIP specification from the RosettaNet organization as a .doc file.</span></span> <span data-ttu-id="69c42-111">El proceso de la extensión de la canalización para usar el nuevo esquema incluye la conversión del archivo de .dtd PIP en un archivo .xsd.</span><span class="sxs-lookup"><span data-stu-id="69c42-111">The process of extending the pipeline to use the new schema includes converting the PIP .dtd file into an .xsd file.</span></span>  
  
 <span data-ttu-id="69c42-112">Al instalar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye una serie de esquemas XSD.</span><span class="sxs-lookup"><span data-stu-id="69c42-112">When you install [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes a number of XSD schemas.</span></span> <span data-ttu-id="69c42-113">Puede encontrar los esquemas en el \< *unidad*\>: \Program BizTalk \<versión\> Accelerator for RosettaNet\SDK\Schemas carpeta.</span><span class="sxs-lookup"><span data-stu-id="69c42-113">You can find those schemas in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas folder.</span></span> <span data-ttu-id="69c42-114">BTARN crea estos esquemas a un archivo RNPIPs.dll.</span><span class="sxs-lookup"><span data-stu-id="69c42-114">BTARN builds these schemas into an RNPIPs.dll file.</span></span> <span data-ttu-id="69c42-115">Si tiene que cambiar uno de estos esquemas, debe abrir el proyecto Rnpip en la misma carpeta, cambiar el esquema en el Editor de BizTalk y, a continuación, vuelva a compilar y volver a implementar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="69c42-115">If you have to change one of these schemas, you must open the RNPIPs project in the same folder, change the schema in BizTalk Editor, and then recompile and redeploy the assembly.</span></span> <span data-ttu-id="69c42-116">Después de volver a implementar el archivo RNPIPs.dll, debe volver a implementar la canalización que utiliza el esquema.</span><span class="sxs-lookup"><span data-stu-id="69c42-116">After you redeploy the RNPIPs.dll file, you must redeploy the pipeline that uses the schema.</span></span> <span data-ttu-id="69c42-117">Puede utilizar este proceso para incorporar un nuevo esquema en BTARN, pero es más fácil ampliar la canalización para incluir el nuevo esquema.</span><span class="sxs-lookup"><span data-stu-id="69c42-117">You could use this process to incorporate a new schema in BTARN, but it is easier to extend the pipeline to include the new schema.</span></span>  
  
### <a name="to-obtain-the-pip-schema"></a><span data-ttu-id="69c42-118">Para obtener el esquema PIP</span><span class="sxs-lookup"><span data-stu-id="69c42-118">To obtain the PIP schema</span></span>  
  
-   <span data-ttu-id="69c42-119">En Internet Explorer, vaya al sitio RosettaNet Web en [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span><span class="sxs-lookup"><span data-stu-id="69c42-119">In Internet Explorer, go to the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c42-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="69c42-120">See Also</span></span>  
 [<span data-ttu-id="69c42-121">Extensión de BTARN con un PIP nuevo</span><span class="sxs-lookup"><span data-stu-id="69c42-121">Extending BTARN with a New PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)