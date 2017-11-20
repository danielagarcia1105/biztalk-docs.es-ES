---
title: "Instancia con promoción de propiedades de procesamiento de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 753571b8-4609-4ac4-a974-8bd6dfecb077
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 288657d43443582c5a05df5dd6e67059eca572e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instance-message-processing-using-property-promotion"></a><span data-ttu-id="c7856-102">Procesar mensajes de instancia con promoción de propiedades</span><span class="sxs-lookup"><span data-stu-id="c7856-102">Instance Message Processing Using Property Promotion</span></span>
<span data-ttu-id="c7856-103">Promocionar propiedades mediante la **campo de propiedad** método requiere la creación de un esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c7856-103">Promoting properties by using the **Property Field** method requires the creation of a property schema.</span></span> <span data-ttu-id="c7856-104">Para obtener más información acerca de cómo crear un esquema de propiedades, vea [cómo crear esquemas de propiedad](../core/how-to-create-property-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="c7856-104">For more information about creating a property schema, see [How to Create Property Schemas](../core/how-to-create-property-schemas.md).</span></span> <span data-ttu-id="c7856-105">Como con la promoción de propiedades, use el **promocionar propiedades** cuadro de diálogo, que es accesible mediante la **promocionar propiedades** propiedad de la **esquema** nodo esquemas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7856-105">As with all property promotion, you use the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node in message schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7856-106">Para obtener acceso a las propiedades promocionadas y usarlas, debe seleccionar una canalización que promocione propiedades.</span><span class="sxs-lookup"><span data-stu-id="c7856-106">You must choose a pipeline that promotes properties in order to access and use the promote properties.</span></span> <span data-ttu-id="c7856-107">Por ejemplo, si usa la canalización PassthruReceive, no se promocionarán propiedades; esto ocasionará que el enrutamiento basado en contenido y otras funciones no actúen según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="c7856-107">For example, if you use the PassthruReceive pipeline, no properties will be promoted; as a result, content-based routing and other functionality will not work as expected.</span></span>  
  
 <span data-ttu-id="c7856-108">En el **promocionar propiedades** diálogo cuadro, asegúrese de que el **campos de propiedades** ficha está seleccionada en el lado derecho del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c7856-108">In the **Promote Properties** dialog box, make sure the **Property Fields** tab is selected in the right side of the dialog box.</span></span> <span data-ttu-id="c7856-109">A continuación, asegúrese del esquema de propiedades adecuado está incluido en la lista de esquemas de propiedad en la parte superior de la **campos de propiedades** ficha. Si es necesario, utilice el botón de carpeta para seleccionar el esquema de propiedades adecuado mediante la **selector de tipos de BizTalk** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c7856-109">Next, ensure the appropriate property schema is included in the Property Schemas List at the top of the **Property Fields** tab. If necessary, use the folder button to select the appropriate property schema by using the **BizTalk Type Picker** dialog box.</span></span> <span data-ttu-id="c7856-110">A continuación, expanda los nodos del árbol de esquema en el lado izquierdo del cuadro de diálogo para buscar y seleccionar la **elemento de campo** nodo o **atributo de campo** nodo que desea promocionar como un campo de propiedad y, a continuación, haga clic en  **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c7856-110">Next, expand the nodes in the schema tree on the left side of the dialog box to find and select the **Field Element** node or **Field Attribute** node that you want to promote as a property field, and then click **Add**.</span></span> <span data-ttu-id="c7856-111">Por último, utilice la lista desplegable en el **propiedad** columna de la **diccionario de campos de propiedades** tabla para seleccionar un **elemento de campo** nodo en un esquema de propiedad con la que se va a asociar la propiedad promocionada.</span><span class="sxs-lookup"><span data-stu-id="c7856-111">Finally, use the drop-down list in the **Property** column of the **Property-Fields dictionary** table to select a **Field Element** node in a property schema with which to associate the promoted property.</span></span> <span data-ttu-id="c7856-112">Para obtener instrucciones detalladas acerca de la promoción de propiedades para campos de propiedades mediante la **promocionar propiedades** cuadro de diálogo, vea [cómo copiar datos en el contexto del mensaje como campos de propiedades](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span><span class="sxs-lookup"><span data-stu-id="c7856-112">For step-by-step instructions about promoting properties to property fields using the **Promote Properties** dialog ox, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7856-113">También puede promocionar un **registro** nodo a un **elemento de campo** nodo en el esquema de propiedades, pero solo si la **tipo de contenido** propiedad de la **registro**nodo se establece en **SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="c7856-113">You can also promote a **Record** node to a **Field Element** node in the property schema, but only if the **Content Type** property of the **Record** node is set to **SimpleContent**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7856-114">Una propiedad se puede promocionar varias veces dentro de un esquema si dichas promociones se realizan en nodos raíz diferentes.</span><span class="sxs-lookup"><span data-stu-id="c7856-114">The same property can be promoted multiple times within a schema as long as all of these promotions are performed under different root nodes.</span></span> <span data-ttu-id="c7856-115">Esto es así porque el mensaje se valida con respecto a un nodo raíz individual y únicamente las propiedades promocionadas en ese nodo raíz se evalúan en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c7856-115">This is because the message is validated against a single root node and only properties promoted under that root node are evaluated at run time.</span></span>  
  
 <span data-ttu-id="c7856-116">Para quitar un **elemento de campo** nodo o **atributo de campo** nodo del conjunto de propiedades que se va a promocionar como campos de propiedades, seleccione la propiedad promocionada en el **diccionario de campos de propiedades**  de tabla en la **campos de propiedades** ficha y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="c7856-116">To remove a **Field Element** node or **Field Attribute** node from the set of properties being promoted as property fields, select the promoted property in the **Property-Fields dictionary** table on the **Property Fields** tab, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="c7856-117">El **ruta del nodo** columna en el **diccionario de campos de propiedades** tabla muestra la expresión XPath en el nodo de esquema correspondiente a la propiedad promocionada.</span><span class="sxs-lookup"><span data-stu-id="c7856-117">The **Node Path** column in the **Property-Fields dictionary** table shows the XPath to the schema node corresponding to the promoted property.</span></span> <span data-ttu-id="c7856-118">Puede editar este valor directamente mediante el **Editar XPath de instancia** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c7856-118">You can edit this value directly by using the **Edit Instance XPath** dialog box.</span></span> <span data-ttu-id="c7856-119">Puede abrir este cuadro de diálogo, haga clic en el botón de puntos suspensivos (**...** ) botón que aparece en el extremo derecho de la celda correspondiente cuando se selecciona esa celda.</span><span class="sxs-lookup"><span data-stu-id="c7856-119">You can open this dialog box by clicking the ellipsis (**...**) button that appears at the right end of the corresponding cell when you select that cell.</span></span> <span data-ttu-id="c7856-120">Preste atención cuando edite valores XPath directamente, ya que los XPath que no puede resolver el Editor de BizTalk impedirán realizar correctamente operaciones de validación.</span><span class="sxs-lookup"><span data-stu-id="c7856-120">Care must be taken when editing XPath values directly because XPaths that cannot be resolved by BizTalk Editor will prevent proper validation operations.</span></span>  
  
 <span data-ttu-id="c7856-121">El Editor de BizTalk también proporciona un comando sofisticado para promocionar las propiedades mediante el **campo de propiedad** mecanismo.</span><span class="sxs-lookup"><span data-stu-id="c7856-121">BizTalk Editor also provides a streamlined command for promoting properties using the **Property Field** mechanism.</span></span> <span data-ttu-id="c7856-122">Este comando se denomina promoción rápida y está disponible con la **promover &#124; Promoción rápida** comando en los menús BizTalk y contextuales.</span><span class="sxs-lookup"><span data-stu-id="c7856-122">This command is called Quick Promotion, and it is available using the **Promote &#124; Quick Promotion** command on the BizTalk and shortcut menus.</span></span> <span data-ttu-id="c7856-123">Este comando promociona seleccionado **campo** nodo (o **registro** nodo) a un campo de propiedad que se crea automáticamente en el esquema de propiedad especificado por el **nombre de esquema de propiedades predeterminadas**  propiedad en el **páginas de propiedades** cuadro de diálogo para el esquema contenedor.</span><span class="sxs-lookup"><span data-stu-id="c7856-123">This command promotes the selected **Field** node (or **Record** node) to a property field that is automatically created in the property schema specified by the **Default Property Schema Name** property in the **Property Pages** dialog box for the containing schema.</span></span> <span data-ttu-id="c7856-124">Para obtener instrucciones paso a paso acerca de la promoción de propiedades para campos de propiedades mediante el comando promoción rápida, consulte [cómo copiar datos en el contexto del mensaje como campos de propiedades](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span><span class="sxs-lookup"><span data-stu-id="c7856-124">For step-by-step instructions about promoting properties to property fields using the Quick Promotion command, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
 <span data-ttu-id="c7856-125">Cuando promocione una propiedad mediante el mecanismo de campos de propiedades, se agregarán dos fragmentos del lenguaje de definición de esquemas XML (XSD) a la representación XSD del esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7856-125">When you promote a property by using the property field mechanism, two XML Schema definition (XSD) language fragments are added to the XSD representation of the message schema.</span></span> <span data-ttu-id="c7856-126">El primer fragmento XSD es un fragmento de anotación asociado con el **esquema** elemento que identifica el esquema de propiedad correspondiente, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7856-126">The first XSD fragment is an annotation fragment associated with the **schema** element that identifies the corresponding property schema, as in the following example:</span></span>  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:imports>  
            <b:namespace prefix="ns0"  
                uri="http://BizTalk_Server_Project1.PropertySchema1"  
                location=".\propertyschema1.xsd" />  
        </b:imports>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
 <span data-ttu-id="c7856-127">El segundo fragmento XSD es un fragmento de anotación asociado con el **raíz** elemento (independientemente de si se ha cambiado) que identifica el **elemento de campo** nodo o **campo Atributo** valores de los nodos que se han promocionado mediante el uso de la propiedad de campo mecanismo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7856-127">The second XSD fragment is an annotation fragment associated with the **Root** element (regardless of whether it has been renamed) that identifies the **Field Element** node or **Field Attribute** node values that have been promoted by using the property field mechanism, as in the following example:</span></span>  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:properties>  
            <b:property name="ns0:PromProp1"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/@*[local-  
                 name()='Field_x0020_1']" />  
            <b:property name="ns0:PromProp2"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/*[local-  
                 name()='ProgramManager']/*[local-name()='Name']" />  
        </b:properties>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7856-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7856-128">See Also</span></span>  
 <span data-ttu-id="c7856-129">[Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control](../core/ways-to-use-message-content-to-control-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="c7856-129">[Ways to Use Message Content to Control Message Processing](../core/ways-to-use-message-content-to-control-message-processing.md) </span></span>  
 [<span data-ttu-id="c7856-130">Cómo copiar los datos en el contexto del mensaje como campos de propiedades</span><span class="sxs-lookup"><span data-stu-id="c7856-130">How to Copy Data to the Message Context as Property Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)