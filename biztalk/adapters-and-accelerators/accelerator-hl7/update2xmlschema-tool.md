---
title: Herramienta Update2XMLSchema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, Update2XMLSchema tool
- schemas, Update2XMLSchema tool
- Update2XMLSchema tool
- Update2XMLSchema tool, syntax
ms.assetid: fd861e2f-ebda-427f-bd52-a2f05b7e22da
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 108bc63536e84dd18cd738fbc6ec10d1e07c404b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978141"
---
# <a name="update2xmlschema-tool"></a><span data-ttu-id="8526c-102">Herramienta Update2XMLSchema</span><span class="sxs-lookup"><span data-stu-id="8526c-102">Update2XMLSchema Tool</span></span>
<span data-ttu-id="8526c-103">La herramienta Update2XMLSchema permite modificar esquemas de HL7 2.XML para trabajar con el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8526c-103">The Update2XMLSchema tool enables you to modify HL7 2.XML schemas to work with BizTalk Editor.</span></span> <span data-ttu-id="8526c-104">Esto es necesario porque algunos esquemas de HL7 2.XML no funcionan correctamente en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sin ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="8526c-104">This is necessary because certain HL7 2.XML schemas do not work correctly within Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] without modification.</span></span> <span data-ttu-id="8526c-105">Después de modificar los esquemas, la herramienta coloca en la carpeta esquemas donde [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] está instalado, por ejemplo,  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\Templates\Schemas.</span><span class="sxs-lookup"><span data-stu-id="8526c-105">After modifying the schemas, the tool places them in the Schemas folder where [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] is installed, for instance, *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\Templates\Schemas.</span></span>  
  
 <span data-ttu-id="8526c-106">Deberá actualizar manualmente algunos campos de los esquemas de ese resultado de ejecutar la herramienta Update2XMLSchema.</span><span class="sxs-lookup"><span data-stu-id="8526c-106">You need to update manually some fields of the schemas that result from running the Update2XMLSchema tool.</span></span> <span data-ttu-id="8526c-107">Consulte [requiere actualizaciones manuales](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) para obtener una lista de esos esquemas.</span><span class="sxs-lookup"><span data-stu-id="8526c-107">See [Required Manual Updates](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) for a list of those schemas.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8526c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8526c-108">Syntax</span></span>  
 <span data-ttu-id="8526c-109">Esta herramienta se encuentra en  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\2XML utilidades.</span><span class="sxs-lookup"><span data-stu-id="8526c-109">This tool is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\2XML Utilities.</span></span> <span data-ttu-id="8526c-110">Ejecute esta herramienta en el símbolo del sistema con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="8526c-110">You run this tool at the command prompt with the following command:</span></span>  
  
```  
Update2XMLSchema /s /v  
```  
  
 <span data-ttu-id="8526c-111">En la tabla siguiente se enumera los parámetros para usar con este comando.</span><span class="sxs-lookup"><span data-stu-id="8526c-111">The following table lists the parameters to use with this command.</span></span>  
  
|<span data-ttu-id="8526c-112">Parámetro</span><span class="sxs-lookup"><span data-stu-id="8526c-112">Parameter</span></span>|<span data-ttu-id="8526c-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="8526c-113">Name</span></span>|<span data-ttu-id="8526c-114">Valor</span><span class="sxs-lookup"><span data-stu-id="8526c-114">Value</span></span>|  
|---------------|----------|-----------|  
|<span data-ttu-id="8526c-115">*S*</span><span class="sxs-lookup"><span data-stu-id="8526c-115">*S*</span></span>|<span data-ttu-id="8526c-116">Source</span><span class="sxs-lookup"><span data-stu-id="8526c-116">Source</span></span>|<span data-ttu-id="8526c-117">Ruta de acceso completa de los esquemas de HL7 originales</span><span class="sxs-lookup"><span data-stu-id="8526c-117">Full path of the original HL7 schemas</span></span>|  
|<span data-ttu-id="8526c-118">*V*</span><span class="sxs-lookup"><span data-stu-id="8526c-118">*V*</span></span>|<span data-ttu-id="8526c-119">Versión</span><span class="sxs-lookup"><span data-stu-id="8526c-119">Version</span></span>|<span data-ttu-id="8526c-120">La versión de los esquemas 2.XML: 2.3.1, 2.4 o 2.5</span><span class="sxs-lookup"><span data-stu-id="8526c-120">The version of the 2.XML schemas:  either 2.3.1, 2.4, or 2.5</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8526c-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8526c-121">Example</span></span>  
  
-   <span data-ttu-id="8526c-122">Si desea modificar la versión 2.3.1 esquemas 2.XML ubicados en el directorio c:\231XML\v231\xsd, escribiría el comando siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="8526c-122">If you want to modify version 2.3.1 2.XML schemas located in the c:\231XML\v231\xsd directory, you would type the following command at the command prompt:</span></span>  
  
```  
Update2XMLSchema /s c:\231XML\v231\xsd /v 2.3.1  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="8526c-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8526c-123">In This Section</span></span>  
  
-   [<span data-ttu-id="8526c-124">Actualizaciones manuales obligatorias</span><span class="sxs-lookup"><span data-stu-id="8526c-124">Required Manual Updates</span></span>](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)