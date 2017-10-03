---
title: Modificar esquemas XML de 2. para trabajar con el Editor de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, modifying
- modifying, 2.XML schemas
ms.assetid: 07316826-84b6-494e-81b9-f64a3d46ffb0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf68f39e4e4c36587b889490b28541e5a690ed05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="modifying-2xml-schemas-to-work-with-biztalk-editor"></a><span data-ttu-id="64d28-102">Modificar esquemas XML de 2. para trabajar con el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="64d28-102">Modifying 2.XML Schemas to Work with BizTalk Editor</span></span>
<span data-ttu-id="64d28-103">Esquemas XML de HL7 2. requieran modificaciones para que funcione correctamente con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="64d28-103">HL7 2.XML schemas require modification to work properly with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span> <span data-ttu-id="64d28-104">A continuación describe cómo modificar HL7 V2. Esquemas XML para que pueda usarlas con el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="64d28-104">The following describes how to modify HL7 V2.XML schemas to enable you to use them with BizTalk Editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64d28-105">La herramienta Update2XMLSchema realiza estos pasos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="64d28-105">The Update2XMLSchema tool performs these steps automatically.</span></span> <span data-ttu-id="64d28-106">Vea [Update2XMLSchema herramienta](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="64d28-106">See [Update2XMLSchema Tool](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md) for more information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64d28-107">El **nillable** atributo puede aparecer en un esquema en un elemento.</span><span class="sxs-lookup"><span data-stu-id="64d28-107">The **nillable** attribute can occur in a schema on an element.</span></span> <span data-ttu-id="64d28-108">Si establece en **true**, indica que la instancia del elemento primario puede tener un **xsi: nil = "true"** atributo.</span><span class="sxs-lookup"><span data-stu-id="64d28-108">If set to **true**, it indicates that the instance of the parent element can have an **xsi:nil="true"** attribute.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="64d28-109">pasa por alto este atributo durante la compilación y durante el análisis y serialización.</span><span class="sxs-lookup"><span data-stu-id="64d28-109"> ignores this attribute during compilation and during parsing/serialization.</span></span>  
  
### <a name="to-modify-2xml-schemas"></a><span data-ttu-id="64d28-110">Para modificar esquemas XML de 2.</span><span class="sxs-lookup"><span data-stu-id="64d28-110">To modify 2.XML schemas</span></span>  
  
1.  <span data-ttu-id="64d28-111">En el archivo fields.xsd, debe quitar instancias de **importar** y reemplácelas con **incluir**.</span><span class="sxs-lookup"><span data-stu-id="64d28-111">In the fields.xsd file, you must remove instances of **import** and replace them with **include**.</span></span> <span data-ttu-id="64d28-112">Por ejemplo, busque en el archivo fields.xsd para el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="64d28-112">For example, search the fields.xsd file for the following text:</span></span>  
  
    ```  
    <xsd:import namespace="urn:hl7-org:v2xml" schemaLocation="datatypes.xsd"/>   
    ```  
  
     <span data-ttu-id="64d28-113">Y cambie el texto a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="64d28-113">And change the text to the following:</span></span>  
  
    ```  
    <xsd:include schemaLocation="datatypes.xsd"/>   
    ```  
  
2.  <span data-ttu-id="64d28-114">En el archivo segments.xsd, debe quitar todas las instancias de las líneas que contienen texto processContents = "lax".</span><span class="sxs-lookup"><span data-stu-id="64d28-114">In the segments.xsd file, you must remove all instances of the lines that contain the text processContents="lax".</span></span> <span data-ttu-id="64d28-115">Por ejemplo, busque en el archivo segments.xsd para el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="64d28-115">For example, search the segments.xsd file for the following text:</span></span>  
  
    ```  
    <xsd:any processContents="lax" namespace="##any" minOccurs="0"/>   
    ```  
  
     <span data-ttu-id="64d28-116">And</span><span class="sxs-lookup"><span data-stu-id="64d28-116">And</span></span>  
  
    ```  
    <xsd:any processContents="lax" namespace="##any"/>   
    ```  
  
     <span data-ttu-id="64d28-117">Y quite estas líneas.</span><span class="sxs-lookup"><span data-stu-id="64d28-117">And remove those lines.</span></span>  
  
3.  <span data-ttu-id="64d28-118">Para todos los esquemas, en la etiqueta de XSD: Schema, debe agregar la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="64d28-118">For all schemas, under the tag xsd:schema, you must add the following line:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64d28-119">No agregue esta línea si ha agregado el esquema mediante [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] porque [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] lo hace automáticamente.</span><span class="sxs-lookup"><span data-stu-id="64d28-119">Do not add this line if you have added the schema using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] because [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] does this for you automatically.</span></span>  
  
    ```  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    ```  
  
     <span data-ttu-id="64d28-120">Por ejemplo, en el archivo ADT_A01.xsd, busque el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="64d28-120">For example, in the file ADT_A01.xsd, search for the following text:</span></span>  
  
    ```  
    <xsd:schema  
     xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
     xmlns="urn:hl7-org:v2xml"   
     targetNamespace="urn:hl7-org:v2xml">   
    ```  
  
     <span data-ttu-id="64d28-121">Y cambie el texto a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="64d28-121">And change the text to the following:</span></span>  
  
    ```  
    <xsd:schema  
     xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
     xmlns="urn:hl7-org:v2xml"  
     targetNamespace="urn:hl7-org:v2xml"  
     xmlns:b="http://schemas.microsoft.com/BizTalk/2003">   
    ```  
  
4.  <span data-ttu-id="64d28-122">Para todos los esquemas, debe agregar una referencia de raíz.</span><span class="sxs-lookup"><span data-stu-id="64d28-122">For all schemas, you must add a root reference.</span></span> <span data-ttu-id="64d28-123">Por ejemplo, en el archivo ADT_A01.xsd, busque el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="64d28-123">For example, in the ADT_A01.xsd file, search for the following text:</span></span>  
  
    ```  
    <xsd:include schemaLocation="segments.xsd" />   
    ```  
  
     <span data-ttu-id="64d28-124">Y cambie el texto para:</span><span class="sxs-lookup"><span data-stu-id="64d28-124">And change the text to:</span></span>  
  
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
    >  <span data-ttu-id="64d28-125">Si utilizas [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], puede agregar este root_reference mediante el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="64d28-125">If you are using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can add this root_reference by using the following procedure.</span></span>  
  
### <a name="to-add-the-root-reference"></a><span data-ttu-id="64d28-126">Para agregar la referencia raíz</span><span class="sxs-lookup"><span data-stu-id="64d28-126">To add the root reference</span></span>  
  
1.  <span data-ttu-id="64d28-127">En el Explorador de soluciones, haga doble clic en el esquema que desea editar.</span><span class="sxs-lookup"><span data-stu-id="64d28-127">In Solution Explorer, double-click the schema you want to edit.</span></span>  
  
2.  <span data-ttu-id="64d28-128">En el panel Propiedades, desplácese hacia abajo hasta la propiedad **root_reference**y en la lista desplegable, haga clic en la propiedad con el mismo nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="64d28-128">In the Properties pane, scroll down to the property **root_reference**, and from the drop-down list, click the property with the same schema name.</span></span>  
  
3.  <span data-ttu-id="64d28-129">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="64d28-129">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d28-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="64d28-130">See Also</span></span>  
 [<span data-ttu-id="64d28-131">Uso de esquemas XML de HL7 2.</span><span class="sxs-lookup"><span data-stu-id="64d28-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)