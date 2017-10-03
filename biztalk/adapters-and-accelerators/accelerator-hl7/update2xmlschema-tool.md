---
title: Herramienta de Update2XMLSchema | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, Update2XMLSchema tool
- schemas, Update2XMLSchema tool
- Update2XMLSchema tool
- Update2XMLSchema tool, syntax
ms.assetid: fd861e2f-ebda-427f-bd52-a2f05b7e22da
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e673e55557af87e5f28005a50c2a01aedf09d2c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="update2xmlschema-tool"></a><span data-ttu-id="1e425-102">Herramienta Update2XMLSchema</span><span class="sxs-lookup"><span data-stu-id="1e425-102">Update2XMLSchema Tool</span></span>
<span data-ttu-id="1e425-103">La herramienta Update2XMLSchema le permite modificar los esquemas XML de HL7 2. para trabajar con el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1e425-103">The Update2XMLSchema tool enables you to modify HL7 2.XML schemas to work with BizTalk Editor.</span></span> <span data-ttu-id="1e425-104">Esto es necesario porque algunos esquemas XML de 2. HL7 no funcionan correctamente en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sin ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="1e425-104">This is necessary because certain HL7 2.XML schemas do not work correctly within [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] without modification.</span></span> <span data-ttu-id="1e425-105">Después de modificar los esquemas, la herramienta coloca en la carpeta esquemas donde [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] está instalado, por ejemplo,  *\<unidad >*: \Program BizTalk \<versión > Accelerator for HL7\Templates\Schemas.</span><span class="sxs-lookup"><span data-stu-id="1e425-105">After modifying the schemas, the tool places them in the Schemas folder where [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] is installed, for instance, *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\Templates\Schemas.</span></span>  
  
 <span data-ttu-id="1e425-106">Debe actualizar manualmente algunos campos de los esquemas que son el resultado de ejecutar la herramienta Update2XMLSchema.</span><span class="sxs-lookup"><span data-stu-id="1e425-106">You need to update manually some fields of the schemas that result from running the Update2XMLSchema tool.</span></span> <span data-ttu-id="1e425-107">Vea [requiere actualizaciones manuales](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) para obtener una lista de los esquemas.</span><span class="sxs-lookup"><span data-stu-id="1e425-107">See [Required Manual Updates](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) for a list of those schemas.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e425-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e425-108">Syntax</span></span>  
 <span data-ttu-id="1e425-109">Esta herramienta se encuentra en  *\<unidad >*: \Program BizTalk \<versión > Accelerator for HL7\SDK\2XML utilidades.</span><span class="sxs-lookup"><span data-stu-id="1e425-109">This tool is located in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\2XML Utilities.</span></span> <span data-ttu-id="1e425-110">Ejecute esta herramienta en el símbolo del sistema con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e425-110">You run this tool at the command prompt with the following command:</span></span>  
  
```  
Update2XMLSchema /s /v  
```  
  
 <span data-ttu-id="1e425-111">En la tabla siguiente se enumera los parámetros para usar con este comando.</span><span class="sxs-lookup"><span data-stu-id="1e425-111">The following table lists the parameters to use with this command.</span></span>  
  
|<span data-ttu-id="1e425-112">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1e425-112">Parameter</span></span>|<span data-ttu-id="1e425-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="1e425-113">Name</span></span>|<span data-ttu-id="1e425-114">Valor</span><span class="sxs-lookup"><span data-stu-id="1e425-114">Value</span></span>|  
|---------------|----------|-----------|  
|<span data-ttu-id="1e425-115">*S*</span><span class="sxs-lookup"><span data-stu-id="1e425-115">*S*</span></span>|<span data-ttu-id="1e425-116">Source</span><span class="sxs-lookup"><span data-stu-id="1e425-116">Source</span></span>|<span data-ttu-id="1e425-117">Ruta de acceso completa de los esquemas de HL7 originales</span><span class="sxs-lookup"><span data-stu-id="1e425-117">Full path of the original HL7 schemas</span></span>|  
|<span data-ttu-id="1e425-118">*V*</span><span class="sxs-lookup"><span data-stu-id="1e425-118">*V*</span></span>|<span data-ttu-id="1e425-119">Versión</span><span class="sxs-lookup"><span data-stu-id="1e425-119">Version</span></span>|<span data-ttu-id="1e425-120">La versión de los esquemas XML de 2.: 2.3.1, 2.4 o 2.5</span><span class="sxs-lookup"><span data-stu-id="1e425-120">The version of the 2.XML schemas:  either 2.3.1, 2.4, or 2.5</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1e425-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e425-121">Example</span></span>  
  
-   <span data-ttu-id="1e425-122">Si desea modificar esquemas XML versión 2.3.1 2. que encuentra en el directorio c:\231XML\v231\xsd, escribiría el comando siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="1e425-122">If you want to modify version 2.3.1 2.XML schemas located in the c:\231XML\v231\xsd directory, you would type the following command at the command prompt:</span></span>  
  
```  
Update2XMLSchema /s c:\231XML\v231\xsd /v 2.3.1  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="1e425-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1e425-123">In This Section</span></span>  
  
-   [<span data-ttu-id="1e425-124">Actualizaciones manuales necesarias</span><span class="sxs-lookup"><span data-stu-id="1e425-124">Required Manual Updates</span></span>](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)