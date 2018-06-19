---
title: Cómo copiar los datos en el contexto del mensaje como campos de propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fdfe475-d9b4-4cf9-898f-dbd7e719c27c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18242f30f32974cc32ab5d39a4a9c63650f27ffa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249988"
---
# <a name="how-to-copy-data-to-the-message-context-as-property-fields"></a><span data-ttu-id="1f179-102">Cómo copiar los datos en el contexto del mensaje como campos de propiedades</span><span class="sxs-lookup"><span data-stu-id="1f179-102">How to Copy Data to the Message Context as Property Fields</span></span>
<span data-ttu-id="1f179-103">Puede promocionar una propiedad como un **campo de propiedad** de la misma manera como promocionar una propiedad como un **campo distintivo**, y también puede usar el **promoción rápida** característica a simplificar el proceso.</span><span class="sxs-lookup"><span data-stu-id="1f179-103">You can promote a property as a **Property Field** in much the same way as promoting a property as a **Distinguished Field**, and you can also use the **Quick Promotion** feature to streamline the process.</span></span>  
  
 <span data-ttu-id="1f179-104">Puede elegir **campo de propiedad** promoción sobre **campo distintivo** promoción por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f179-104">You might choose **Property Field** promotion over **Distinguished Field** promotion for the following reasons:</span></span>  
  
-   <span data-ttu-id="1f179-105">Los valores que desea promocionar tienen menos caracteres que la limitación de 255 caracteres que se aplica a **campos de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1f179-105">The values you want to promote are shorter than the 255 character limitation that applies to **Property Fields**.</span></span>  
  
-   <span data-ttu-id="1f179-106">Necesita que sea posible el acceso a los valores promocionados desde fuera de las orquestaciones; por ejemplo, desde canalizaciones o puertos.</span><span class="sxs-lookup"><span data-stu-id="1f179-106">You need the values that you promote to be accessible outside of orchestrations, such as within pipelines or ports.</span></span>  
  
 <span data-ttu-id="1f179-107">Este tema proporciona instrucciones paso a paso para promocionar una propiedad como un **campo de propiedad** en ambas de estas maneras.</span><span class="sxs-lookup"><span data-stu-id="1f179-107">This topic provides step-by-step instructions for promoting a property as a **Property Field** in both of these ways.</span></span>  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-promote-properties-dialog-box"></a><span data-ttu-id="1f179-108">Para promocionar una propiedad como un campo de propiedades mediante el cuadro de diálogo Promocionar propiedades</span><span class="sxs-lookup"><span data-stu-id="1f179-108">To promote a property as a Property Field using the Promote Properties dialog box</span></span>  
  
1.  <span data-ttu-id="1f179-109">Si es necesario, cree un esquema de propiedades adecuado para promocionar una propiedad.</span><span class="sxs-lookup"><span data-stu-id="1f179-109">If necessary, create an appropriate property schema into which you will promote a property.</span></span> <span data-ttu-id="1f179-110">Para obtener instrucciones paso a paso para crear esquemas de propiedades, vea [crear esquemas de propiedad](../core/how-to-create-property-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="1f179-110">For step-by-step instructions for creating property schemas, see [Creating Property Schemas](../core/how-to-create-property-schemas.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-111">Este paso no sea necesario si ya ha creado un esquema de propiedad e inserta adecuado **elemento de campo** nodos como nodos secundarios de la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="1f179-111">This step might not be necessary if you have already created a property schema and inserted the appropriate **Field Element** nodes as child nodes of the **Schema** node.</span></span>  
  
2.  <span data-ttu-id="1f179-112">En el Editor de BizTalk, abra el esquema para el que desea promocionar una o varias propiedades y, a continuación, seleccione el (primer) **elemento de campo**, **atributo de campo**, o **registro** nodo que desea promover como un **campo de la propiedad**.</span><span class="sxs-lookup"><span data-stu-id="1f179-112">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Property Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-113">Solo puede promocionar **registro** nodos si se han configurado para incluir únicamente contenido simple manteniendo su **Content Type** propiedad establecida en **SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="1f179-113">You can only promote **Record** nodes if they are configured to contain only simple content by having its **Content Type** property set to **SimpleContent**.</span></span>  
  
3.  <span data-ttu-id="1f179-114">Haga clic en el nodo seleccionado, haga clic en **promover**y, a continuación, haga clic en **mostrar promociones**.</span><span class="sxs-lookup"><span data-stu-id="1f179-114">Right-click the selected node, click **Promote**, and then click **Show Promotions**.</span></span>  
  
     <span data-ttu-id="1f179-115">El **promocionar propiedades** abre el cuadro de diálogo con la muestra el nodo seleccionado en el árbol de esquema en el lado izquierdo del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1f179-115">The **Promote Properties** dialog box opens with the selected node showing as selected in the schema tree on the left side of the dialog box.</span></span>  
  
4.  <span data-ttu-id="1f179-116">En el **promocionar propiedades** cuadro de diálogo, seleccione la **campos de propiedades** ficha.</span><span class="sxs-lookup"><span data-stu-id="1f179-116">In the **Promote Properties** dialog box, select the **Property Fields** tab.</span></span>  
  
5.  <span data-ttu-id="1f179-117">Confirme que el esquema de propiedad en la que desea promocionar una propiedad está presente en el **lista de esquemas de propiedad** en la pestaña campos de propiedades. Si está presente, vaya al paso 8.</span><span class="sxs-lookup"><span data-stu-id="1f179-117">Confirm that the property schema into which you want to promote a property is present in the **Property Schemas List** in the Property Fields tab. If it is present, skip to step 8.</span></span>  
  
6.  <span data-ttu-id="1f179-118">En el **lista de esquemas de propiedad** sección, haga clic en el **carpeta** icono.</span><span class="sxs-lookup"><span data-stu-id="1f179-118">In the **Property Schemas List** section, click the **Folder** icon.</span></span> <span data-ttu-id="1f179-119">El **selector de tipos de BizTalk** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1f179-119">The **BizTalk Type Picker** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="1f179-120">En el **selector de tipos de BizTalk** diálogo cuadro, vaya al esquema de propiedades adecuado (que haya creado en el paso 1), seleccione dicho esquema y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f179-120">In the **BizTalk Type Picker** dialog box, navigate to the appropriate property schema (that you may have created in step 1), select that schema, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-121">Si lo desea, puede cambiar el prefijo de espacio de nombres asociado al esquema de propiedad cambiando la cadena en la correspondiente **prefijo** campo de la columna.</span><span class="sxs-lookup"><span data-stu-id="1f179-121">Optionally, you can change the namespace prefix associated with the property schema by changing the string in the appropriate **Prefix** column field.</span></span>  
  
8.  <span data-ttu-id="1f179-122">Con el nodo para promocionar todavía seleccionado en el árbol de esquema en el lado izquierdo de la **promocionar propiedades** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="1f179-122">With the node to be promoted still selected in the schema tree on the left side of the **Promote Properties** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="1f179-123">Si se permite, el nodo seleccionado se agrega al final de la **lista de campos de propiedades** en el **campos de propiedades** ficha. En caso de no permitirse, un cuadro de mensajes proporciona una explicación.</span><span class="sxs-lookup"><span data-stu-id="1f179-123">If allowed, the selected node is added to the end of the **Property Fields List** on the **Property Fields** tab. If not allowed, a message box provides an explanation.</span></span> <span data-ttu-id="1f179-124">Si no se permite la **agregar** botón no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="1f179-124">If not allowed, the **Add** button is not enabled.</span></span>  
  
9. <span data-ttu-id="1f179-125">Haga doble clic en **propiedad** celda de la columna de la fila que acaba de agregar a la **lista de campos de propiedades**y, a continuación, en la lista desplegable, seleccione la **esquema de propiedad** y correspondiente **elemento de campo** nodo en el que desea promocionar el nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1f179-125">Double-click **Property** column cell for the row you just added to the **Property Fields List**, and then in the drop-down list, select the **Property Schema** and corresponding **Field Element** node into which you want to promote the selected node.</span></span> <span data-ttu-id="1f179-126">Valores de lista desplegable tienen el formato x: y, donde X es el prefijo de espacio de nombres de un esquema de propiedad de la **lista de esquemas de propiedad**, e Y es el nombre del nodo de un **elemento de campo** nodo en ese esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1f179-126">Drop-down list values have the form X:Y, where X is the namespace prefix of a property schema in the **Property Schemas List**, and Y is the node name of a **Field Element** node in that property schema.</span></span>  
  
     <span data-ttu-id="1f179-127">El valor predeterminado en la lista desplegable es el primer esquema de propiedad **(elemento de campo)** nodo que no se ha promocionado, por orden alfabético de todos los esquemas de propiedad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1f179-127">The default value in the drop-down list is the first property schema **(Field Element)** node that has not yet been promoted, sorted alphabetically across all relevant property schemas.</span></span> <span data-ttu-id="1f179-128">En raras ocasiones será el nodo de esquema de propiedades en el que pretende promocionar un nodo de esquema específico.</span><span class="sxs-lookup"><span data-stu-id="1f179-128">This will rarely be the property schema node into which you intend to promote a given schema node.</span></span>  
  
10. <span data-ttu-id="1f179-129">Puede seleccionar nodos adicionales para promocionarlos en el árbol de esquema en el lado izquierdo del cuadro de diálogo, haga clic en **agregar** y, a continuación, realizar el paso 9 después de cada selección.</span><span class="sxs-lookup"><span data-stu-id="1f179-129">You can select additional nodes for promotion in the schema tree on the left side of the dialog box, clicking **Add** and then performing step 9 after each selection.</span></span>  
  
11. <span data-ttu-id="1f179-130">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f179-130">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="1f179-131">Los nodos seleccionados para promocionar son ahora **campos de propiedades** y están asociados a un determinado **elemento de campo** nodo en un esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1f179-131">The nodes that you selected to promote are now **Property Fields** and are associated with a particular **Field Element** node in a property schema.</span></span>  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-quick-promotion-command"></a><span data-ttu-id="1f179-132">Para promocionar una propiedad como un campo de propiedades mediante el comando Promoción rápida</span><span class="sxs-lookup"><span data-stu-id="1f179-132">To promote a property as a Property Field using the Quick Promotion command</span></span>  
  
1.  <span data-ttu-id="1f179-133">En el Editor de BizTalk, abra el esquema para el que desea promocionar una o varias propiedades y, a continuación, seleccione el (primer) **elemento de campo**, **atributo de campo**, o **registro** nodo que desea promover como un **campo de la propiedad**.</span><span class="sxs-lookup"><span data-stu-id="1f179-133">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Property Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f179-134">Solo puede promocionar **registro** nodos si se han configurado para incluir únicamente contenido simple manteniendo su **Content Type** propiedad establecida en **SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="1f179-134">You can only promote **Record** nodes if they are configured to contain only simple content by having its **Content Type** property set to **SimpleContent**.</span></span>  
  
2.  <span data-ttu-id="1f179-135">Haga clic en el nodo seleccionado, haga clic en **promover**y, a continuación, haga clic en **promoción rápida**.</span><span class="sxs-lookup"><span data-stu-id="1f179-135">Right-click the selected node, click **Promote**, and then click **Quick Promotion**.</span></span>  
  
     <span data-ttu-id="1f179-136">Si el esquema de propiedad predeterminado, tal como se define por la **nombre del esquema de propiedad predeterminado** propiedad en el **páginas de propiedades** para el esquema correspondiente, no existe, debe hacer clic en **Aceptar**en el cuadro de diálogo de confirmación para crear el esquema de propiedad predeterminado y configurarlo con un adecuado **elemento de campo** nodo para dar cabida a la promoción de propiedades.</span><span class="sxs-lookup"><span data-stu-id="1f179-136">If the default property schema, as defined by the **Default Property Schema Name** property on the **Property Pages** for the relevant schema, does not exist, you must click **OK** in the confirmation dialog to create the default property schema and configure it with an appropriate **Field Element** node to accommodate your property promotion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f179-137">Puede ver y administrar las propiedades promocionadas mediante la **promociones rápidas** característica abriendo el **promocionar propiedades** cuadro de diálogo y, a continuación, haga clic en el **campos de propiedades** pestaña. Para obtener instrucciones paso a paso para abrir el **promocionar propiedades** cuadro de diálogo, vea [abrir el cuadro de diálogo Promocionar propiedades](../core/how-to-open-the-promote-properties-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="1f179-137">You can view and manage properties promoted using the **Quick Promotions** feature by opening the **Promote Properties** dialog box and then clicking the **Property Fields** tab. For step-by-step instructions for opening the **Promote Properties** dialog box, see [Opening the Promote Properties Dialog Box](../core/how-to-open-the-promote-properties-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f179-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f179-138">See Also</span></span>  
 <span data-ttu-id="1f179-139">[Promoción de propiedades](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1f179-139">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="1f179-140">[Cómo crear esquemas de propiedades](../core/how-to-create-property-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="1f179-140">[How to Create Property Schemas](../core/how-to-create-property-schemas.md) </span></span>  
 [<span data-ttu-id="1f179-141">Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control</span><span class="sxs-lookup"><span data-stu-id="1f179-141">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)