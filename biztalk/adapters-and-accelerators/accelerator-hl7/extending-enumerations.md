---
title: Extender las enumeraciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enumeration values
- 2.X schemas, enumeration values
ms.assetid: 043def35-b644-4502-a2e2-cc1a5fc0328a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc5b91513833b76ba7dc3697f9eee409bf9752bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987853"
---
# <a name="extending-enumerations"></a><span data-ttu-id="2dd90-102">Extender las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="2dd90-102">Extending Enumerations</span></span>
<span data-ttu-id="2dd90-103">Puede agregar valores a las enumeraciones que establecer los valores aceptados para muchos tipos de datos, segmentos y campos en el cuerpo del mensaje HL7, confirmación y esquemas de cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2dd90-103">You can add values to the enumerations that establish accepted values for many fields, segments, and data types in HL7 message body, acknowledgment, and message body schemas.</span></span> <span data-ttu-id="2dd90-104">Esto implica cambiar el conjunto de valores en una tabla específica en el archivo de esquema de los valores de tabla común para la versión de HL7 en el que está trabajando (el **Tablevalues_\<**<em>versión</em>  **\>.xsd** archivo de esquema).</span><span class="sxs-lookup"><span data-stu-id="2dd90-104">This involves changing the set of values in a specific table in the common table values schema file for the HL7 version in which you are working (the **Tablevalues_\<**<em>version</em>**\>.xsd** schema file).</span></span>  
  
 <span data-ttu-id="2dd90-105">Agregar a la enumeración de forma diferente para el esquema de encabezado de mensaje a como lo hace en otro esquema, como el esquema de cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2dd90-105">You add to the enumeration in a different way for the message header schema than you do in other schemas, such as the message body schema.</span></span> <span data-ttu-id="2dd90-106">Para el esquema de encabezado de mensaje, debe cambiar la tabla en el archivo MSH_25_GLO_DEF.xsd.</span><span class="sxs-lookup"><span data-stu-id="2dd90-106">For the message header schema, you must change the table within the MSH_25_GLO_DEF.xsd file.</span></span> <span data-ttu-id="2dd90-107">Para otros esquemas, cambia la tabla en el archivo de esquema de los valores de tabla (tablevalues_\<versión\>.xsd).</span><span class="sxs-lookup"><span data-stu-id="2dd90-107">For other schemas, you change the table in the table values schema file (tablevalues_\<version\>.xsd).</span></span>  
  
### <a name="to-add-an-enumeration-value-to-the-table-values-common-schema-file"></a><span data-ttu-id="2dd90-108">Para agregar un valor de enumeración para el archivo de esquema común de valores de tabla</span><span class="sxs-lookup"><span data-stu-id="2dd90-108">To add an enumeration value to the table values common schema file</span></span>  
  
1. <span data-ttu-id="2dd90-109">En primer lugar, deberá determinar la tabla que contiene la enumeración que se desea agregar a.</span><span class="sxs-lookup"><span data-stu-id="2dd90-109">You first need to determine the table that contains the enumeration that you want to add to.</span></span> <span data-ttu-id="2dd90-110">En el Explorador de soluciones de Visual Studio, abra el archivo de esquema que contiene el elemento que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="2dd90-110">In Solution Explorer of Visual Studio, open the schema file that contains the element that you want to change.</span></span> <span data-ttu-id="2dd90-111">En el Explorador de BizTalk, haga clic en el elemento de campo que desea agregar un valor para.</span><span class="sxs-lookup"><span data-stu-id="2dd90-111">In BizTalk Explorer, click the field element that you want to add a value for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2dd90-112">Al cambiar una enumeración en el archivo de esquema común de valores de tabla, todos los objetos que hacen referencia a dicha enumeración se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="2dd90-112">When you change an enumeration in the table values common schema file, all objects that reference that enumeration are affected.</span></span>  
  
2. <span data-ttu-id="2dd90-113">En el **propiedades** panel, tenga en cuenta el nombre de la tabla en la **Base Data Type** campo.</span><span class="sxs-lookup"><span data-stu-id="2dd90-113">In the **Properties** pane, note the name of the table in the **Base Data Type** field.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2dd90-114">Si no hay ninguna tabla se enumeran en **Base Data Type** campo y el **Derived By** propiedad no está establecida en **Restricted**, significa que el campo no tiene una enumeración asociada con él .</span><span class="sxs-lookup"><span data-stu-id="2dd90-114">If there is no table listed in **Base Data Type** field, and the **Derived By** property is not set to **Restricted**, then the field does not have an enumeration associated with it.</span></span>  
  
3. <span data-ttu-id="2dd90-115">En el Explorador de soluciones, abra el **Tablevalues_\<**<em>versión</em>**\>.xsd**y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="2dd90-115">In Solution Explorer, open the **Tablevalues_\<**<em>version</em>**\>.xsd**, and then click **Open**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2dd90-116">Debe realizar este procedimiento por separado para cada versión del esquema HL7 que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="2dd90-116">You must perform this procedure separately for each version of the HL7 schema that you want to change.</span></span>  
  
4. <span data-ttu-id="2dd90-117">En el Editor de BizTalk, vaya a la tabla que desea cambiar y, a continuación, haga clic en ese nodo de tabla.</span><span class="sxs-lookup"><span data-stu-id="2dd90-117">In BizTalk Editor, browse to the table you want to change, and then click that table node.</span></span>  
  
5. <span data-ttu-id="2dd90-118">En la ventana Propiedades, en el **restricción** sección, haga clic en **enumeración**y, a continuación, haga clic en el botón de puntos suspensivos (...) para abrir el Editor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="2dd90-118">In the Properties window, in the **Restriction** section, click **Enumeration**, and then click the ellipsis (…) button to open the Enumeration Editor.</span></span>  
  
6. <span data-ttu-id="2dd90-119">En el Editor de enumeración, agregar el nuevo valor a la lista de valores existentes y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2dd90-119">In the Enumeration Editor, add the new value to the list of existing values, and then click **OK**.</span></span>  
  
### <a name="to-add-an-enumeration-value-to-a-message-header-schema"></a><span data-ttu-id="2dd90-120">Para agregar un valor de enumeración a un esquema de encabezado de mensaje</span><span class="sxs-lookup"><span data-stu-id="2dd90-120">To add an enumeration value to a message header schema</span></span>  
  
1. <span data-ttu-id="2dd90-121">En el Explorador de soluciones, abra el esquema MSH_25_GLO_DEF y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="2dd90-121">In Solution Explorer, open the MSH_25_GLO_DEF schema, and then click **Open**.</span></span>  
  
2. <span data-ttu-id="2dd90-122">Haga clic en el **MSH** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario**.</span><span class="sxs-lookup"><span data-stu-id="2dd90-122">Right-click the **MSH** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="2dd90-123"> Agrega un nodo de campo a MSH, llamado **campo**.</span><span class="sxs-lookup"><span data-stu-id="2dd90-123"> adds a field node to MSH, called **Field**.</span></span> <span data-ttu-id="2dd90-124">Haga clic en **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="2dd90-124">Click **ENTER**.</span></span>  
  
3. <span data-ttu-id="2dd90-125">En el **propiedades** ventana, haga clic en el **tipo de datos** nodo, a continuación, desde la lista desplegable, seleccione la tabla a la que desea agregar el valor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="2dd90-125">In the **Properties** window, click the **Data Type** node, then from the drop-down list, select the table to which you want to add the enumeration value.</span></span>  
  
4. <span data-ttu-id="2dd90-126">En el **propiedades** ventana, en el **restricción** sección, haga clic en **enumeración**y, a continuación, haga clic en el botón de puntos suspensivos (...) para abrir el Editor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="2dd90-126">In the **Properties** window, in the **Restriction** section, click **Enumeration**, and then click the ellipsis (…) button to open the Enumeration Editor.</span></span>  
  
5. <span data-ttu-id="2dd90-127">En el Editor de enumeración, agregar el nuevo valor a la lista de valores existentes y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2dd90-127">In the Enumeration Editor, add the new value to the list of existing values, and then click **OK**.</span></span>  
  
    <span data-ttu-id="2dd90-128">Cuando agrega un valor a la enumeración de cualquier nodo, como el **campo** nodo, se agrega ese valor globalmente para todos los objetos que utilicen esa tabla.</span><span class="sxs-lookup"><span data-stu-id="2dd90-128">When you add a value to the enumeration for any node, such as the **Field** node, you add that value globally for all objects that use that table.</span></span> <span data-ttu-id="2dd90-129">Como resultado, ahora puede eliminar el **campo** nodo y el valor seguirán estando presentes en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2dd90-129">As a result, you can now delete the **Field** node, and the value will still be present for the table.</span></span> <span data-ttu-id="2dd90-130">Para comprobarlo, desplazamiento en el panel derecho del Editor de BizTalk a la tabla y comprobar que el valor que ha agregado está presente.</span><span class="sxs-lookup"><span data-stu-id="2dd90-130">You can verify this by scrolling in the right pane of BizTalk Editor to the table, and verifying that the value that you added is present.</span></span>  
  
6. <span data-ttu-id="2dd90-131">Haga clic en el **campo** nodo en el Editor de BizTalk, haga clic en **eliminar**y, a continuación, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2dd90-131">Right-click the **Field** node in BizTalk Editor, click **Delete**, and then click **Yes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd90-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2dd90-132">See Also</span></span>  
 <span data-ttu-id="2dd90-133">[Valores de tabla de esquemas comunes](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="2dd90-133">[Table Values Common Schemas](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md) </span></span>  
 <span data-ttu-id="2dd90-134">[Extender esquemas HL7 2.X con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="2dd90-134">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="2dd90-135">[Creación de segmentos Z declarados](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="2dd90-135">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="2dd90-136">[Creación de tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="2dd90-136">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="2dd90-137">[Creación de tablas personalizadas en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="2dd90-137">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 [<span data-ttu-id="2dd90-138">Control de segmentos de Z no declarados</span><span class="sxs-lookup"><span data-stu-id="2dd90-138">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)