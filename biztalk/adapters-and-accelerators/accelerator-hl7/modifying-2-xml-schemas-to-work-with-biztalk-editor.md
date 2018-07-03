---
title: Modificación de esquemas 2.XML para trabajar con el Editor de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, modifying
- modifying, 2.XML schemas
ms.assetid: 07316826-84b6-494e-81b9-f64a3d46ffb0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96dd1c4cd8909564ff39c78b5b1a9e4fc248d93f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972861"
---
# <a name="modifying-2xml-schemas-to-work-with-biztalk-editor"></a><span data-ttu-id="bf6cb-102">Modificación de esquemas 2.XML para trabajar con el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bf6cb-102">Modifying 2.XML Schemas to Work with BizTalk Editor</span></span>
<span data-ttu-id="bf6cb-103">Esquemas de HL7 2.XML requieren ninguna modificación para funcionar correctamente con el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="bf6cb-103">HL7 2.XML schemas require modification to work properly with Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span> <span data-ttu-id="bf6cb-104">El siguiente describe cómo modificar HL7 V2. Esquemas XML para que pueda usarlos con el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-104">The following describes how to modify HL7 V2.XML schemas to enable you to use them with BizTalk Editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf6cb-105">La herramienta Update2XMLSchema realiza estos pasos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-105">The Update2XMLSchema tool performs these steps automatically.</span></span> <span data-ttu-id="bf6cb-106">Consulte [herramienta Update2XMLSchema](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-106">See [Update2XMLSchema Tool](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md) for more information.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="bf6cb-107">El **nillable** atributo puede aparecer en un esquema en un elemento.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-107">The **nillable** attribute can occur in a schema on an element.</span></span> <span data-ttu-id="bf6cb-108">Si establece en **true**, indica que la instancia del elemento primario puede tener un **xsi: nil = "true"** atributo.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-108">If set to **true**, it indicates that the instance of the parent element can have an **xsi:nil="true"** attribute.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bf6cb-109"> omite este atributo durante la compilación y durante el análisis y serialización.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-109"> ignores this attribute during compilation and during parsing/serialization.</span></span>  
  
### <a name="to-modify-2xml-schemas"></a><span data-ttu-id="bf6cb-110">Para modificar esquemas 2.Xml</span><span class="sxs-lookup"><span data-stu-id="bf6cb-110">To modify 2.XML schemas</span></span>  
  
1. <span data-ttu-id="bf6cb-111">En el archivo fields.xsd, debe quitar las instancias de **importar** y reemplácelas con **incluyen**.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-111">In the fields.xsd file, you must remove instances of **import** and replace them with **include**.</span></span> <span data-ttu-id="bf6cb-112">Por ejemplo, busque el archivo fields.xsd el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf6cb-112">For example, search the fields.xsd file for the following text:</span></span>  
  
   ```  
   <xsd:import namespace="urn:hl7-org:v2xml" schemaLocation="datatypes.xsd"/>   
   ```  
  
    <span data-ttu-id="bf6cb-113">Y cambie el texto a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf6cb-113">And change the text to the following:</span></span>  
  
   ```  
   <xsd:include schemaLocation="datatypes.xsd"/>   
   ```  
  
2. <span data-ttu-id="bf6cb-114">En el archivo segments.xsd, debe quitar todas las instancias de las líneas que contienen texto processContents = "lax".</span><span class="sxs-lookup"><span data-stu-id="bf6cb-114">In the segments.xsd file, you must remove all instances of the lines that contain the text processContents="lax".</span></span> <span data-ttu-id="bf6cb-115">Por ejemplo, busque el archivo segments.xsd el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf6cb-115">For example, search the segments.xsd file for the following text:</span></span>  
  
   ```  
   <xsd:any processContents="lax" namespace="##any" minOccurs="0"/>   
   ```  
  
    <span data-ttu-id="bf6cb-116">And</span><span class="sxs-lookup"><span data-stu-id="bf6cb-116">And</span></span>  
  
   ```  
   <xsd:any processContents="lax" namespace="##any"/>   
   ```  
  
    <span data-ttu-id="bf6cb-117">Y quite estas líneas.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-117">And remove those lines.</span></span>  
  
3. <span data-ttu-id="bf6cb-118">Para todos los esquemas, en la etiqueta de XSD: Schema, debe agregar la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="bf6cb-118">For all schemas, under the tag xsd:schema, you must add the following line:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf6cb-119">No agregue esta línea si ha agregado el esquema mediante Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] porque [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] hace esto automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-119">Do not add this line if you have added the schema using Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] because [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] does this for you automatically.</span></span>  
  
   ```  
   xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
   ```  
  
    <span data-ttu-id="bf6cb-120">Por ejemplo, en el archivo ADT_A01.xsd, busque el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf6cb-120">For example, in the file ADT_A01.xsd, search for the following text:</span></span>  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="urn:hl7-org:v2xml"   
    targetNamespace="urn:hl7-org:v2xml">   
   ```  
  
    <span data-ttu-id="bf6cb-121">Y cambie el texto a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf6cb-121">And change the text to the following:</span></span>  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:hl7-org:v2xml"  
    targetNamespace="urn:hl7-org:v2xml"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003">   
   ```  
  
4. <span data-ttu-id="bf6cb-122">Para todos los esquemas, debe agregar una referencia de raíz.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-122">For all schemas, you must add a root reference.</span></span> <span data-ttu-id="bf6cb-123">Por ejemplo, en el archivo ADT_A01.xsd, busque el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf6cb-123">For example, in the ADT_A01.xsd file, search for the following text:</span></span>  
  
   ```  
   <xsd:include schemaLocation="segments.xsd" />   
   ```  
  
    <span data-ttu-id="bf6cb-124">Y cambie el texto para:</span><span class="sxs-lookup"><span data-stu-id="bf6cb-124">And change the text to:</span></span>  
  
   ```  
   <xsd:include schemaLocation="segments.xsd" />  
   <xsd:annotation>   
     <xsd:appinfo>   
       <schemaInfo root_reference="ADT_A01"  
    xmlns="http://schemas.microsoft.com/BizTalk/2003" />   
     </xsd:appinfo>   
   </xsd:annotation>   
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="bf6cb-125">Si usas [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], puede agregar este root_reference mediante el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-125">If you are using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can add this root_reference by using the following procedure.</span></span>  
  
### <a name="to-add-the-root-reference"></a><span data-ttu-id="bf6cb-126">Para agregar la referencia raíz</span><span class="sxs-lookup"><span data-stu-id="bf6cb-126">To add the root reference</span></span>  
  
1.  <span data-ttu-id="bf6cb-127">En el Explorador de soluciones, haga doble clic en el esquema que desea editar.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-127">In Solution Explorer, double-click the schema you want to edit.</span></span>  
  
2.  <span data-ttu-id="bf6cb-128">En el panel Propiedades, desplácese a la propiedad **root_reference**y en la lista desplegable, haga clic en la propiedad con el mismo nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-128">In the Properties pane, scroll down to the property **root_reference**, and from the drop-down list, click the property with the same schema name.</span></span>  
  
3.  <span data-ttu-id="bf6cb-129">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="bf6cb-129">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6cb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf6cb-130">See Also</span></span>  
 [<span data-ttu-id="bf6cb-131">Uso de esquemas de HL7 2.XML</span><span class="sxs-lookup"><span data-stu-id="bf6cb-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)