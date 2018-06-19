---
title: Administrar el comportamiento de asignador predeterminado mediante &lt;mapsource&gt; | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deea839c-e52e-44c6-ac0d-4396dc5b10d8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44e2e66350709c6b857d875ec3979fe3f7059648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263380"
---
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a><span data-ttu-id="d6702-102">Administrar el comportamiento de asignador predeterminado mediante &lt;mapsource&gt;</span><span class="sxs-lookup"><span data-stu-id="d6702-102">Managing Default Mapper Behavior Using &lt;mapsource&gt;</span></span>
<span data-ttu-id="d6702-103">Puede modificar ciertos comportamientos predeterminados del asignador de BizTalk mediante la modificación de atributos de la **mapsource** elemento directamente en un archivo de origen (.btm) de asignación.</span><span class="sxs-lookup"><span data-stu-id="d6702-103">You can modify certain default behaviors of BizTalk Mapper by modifying attributes of the **mapsource** element directly in a map source (.btm) file.</span></span>  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a><span data-ttu-id="d6702-104">Optimizar la generación del código de functoid Asignación de valores</span><span class="sxs-lookup"><span data-stu-id="d6702-104">Optimizing Value Mapping Functoid Code Generation</span></span>  
 <span data-ttu-id="d6702-105">Cuando el asignador genera código XSLT para llamar a la **Value Mapping** functoid, una variable se usa para almacenar el resultado.</span><span class="sxs-lookup"><span data-stu-id="d6702-105">When the Mapper generates XSLT code to call the **Value Mapping** functoid, a variable is used to store the result.</span></span> <span data-ttu-id="d6702-106">Puede usar el **OptimizeValueMapping** marca para optimizar el **Value Mapping** functoid para que se genere una variable solo cuando la `if` instrucción se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="d6702-106">You can use the **OptimizeValueMapping** flag to optimize the **Value Mapping** functoid so that a variable is generated only when the `if` statement evaluates to `True`.</span></span> <span data-ttu-id="d6702-107">Por ejemplo, con **OptimizeValueMapping** establecido en **n**:</span><span class="sxs-lookup"><span data-stu-id="d6702-107">For example, with **OptimizeValueMapping** set to **No**:</span></span>  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="d6702-108">Este código podría optimizarse trasladando la **Value Mapping** invocación al functoid en el cuerpo de la `if` instrucción, asegurándose de que la invocación produce solo cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="d6702-108">This code could be optimized by moving the **Value Mapping** functoid invocation into the body of the `if` statement, ensuring that invocation occurs only when it is required.</span></span> <span data-ttu-id="d6702-109">Establecer **OptimizeValueMapping** a **Sí** produce el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="d6702-109">Setting **OptimizeValueMapping** to **Yes** yields the following code:</span></span>  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="d6702-110">El asignador realiza esta optimización automáticamente si se establece la **OptimizeValueMapping** atributo de la **mapsource** elemento en el archivo de origen (.btm) asignación **Sí** como se muestra:</span><span class="sxs-lookup"><span data-stu-id="d6702-110">The Mapper does this optimization automatically if you set the **OptimizeValueMapping** attribute of the **mapsource** element in the map source (.btm) file to **Yes** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a><span data-ttu-id="d6702-111">Dar cabida a esquemas con huellas grandes</span><span class="sxs-lookup"><span data-stu-id="d6702-111">Accommodating Schemas with Large Footprints</span></span>  
 <span data-ttu-id="d6702-112">Cuando el Asignador usa un esquema que tiene una huella de instancia muy grande, con estructuras complejas profundas o nodos recursivos, puede ser necesario mucho tiempo para probar, validar o compilar la asignación; en el peor de los casos, puede producirse un error por memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="d6702-112">When the Mapper is using a schema that has a very large instance footprint with deep complex structures and/or recursive nodes, testing the map, validating the map, or compiling the map could take a long time or, in the worse case, result in an "out of memory" error.</span></span> <span data-ttu-id="d6702-113">Esto puede ocurrir tanto con pequeños esquemas complejos como con esquemas grandes.</span><span class="sxs-lookup"><span data-stu-id="d6702-113">This could happen with small, complex schemas as well as with large schemas.</span></span>  
  
 <span data-ttu-id="d6702-114">El problema con esquemas complejos es debido al hecho de que el asignador tiene que cargar recursivamente el árbol de esquema todo busca de nodos que tienen vínculos conectados o la **valor** propiedad establecida en ellos.</span><span class="sxs-lookup"><span data-stu-id="d6702-114">The problem with complex schemas is due to the fact that the Mapper has to recursively load the entire schema tree looking for nodes that either have links connected to them or have the **Value** property set on them.</span></span> <span data-ttu-id="d6702-115">Puede mitigar este problema estableciendo la **GenerateDefaultFixedNodes** marca de la **mapsource** elemento en los archivos .btm en **n** tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="d6702-115">You can alleviate this problem by setting the **GenerateDefaultFixedNodes** flag of the **mapsource** element in the .btm files to **No** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="d6702-116">Con esta configuración, el Asignador no necesita crear nodos de compilador interno asociados a cada nodo de esquema de un esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="d6702-116">With this setting, the Mapper does not need to create internal compiler nodes associated with each schema node of a target schema.</span></span> <span data-ttu-id="d6702-117">El compilador sólo tendrá en cuenta los nodos vinculados.</span><span class="sxs-lookup"><span data-stu-id="d6702-117">Only linked nodes are taken into account by the compiler.</span></span> <span data-ttu-id="d6702-118">Esto reduce significativamente el consumo de memoria y agiliza el proceso al realizar una operación "comprobar asignación" o "validar asignación", al compilar una asignación o al guardarla.</span><span class="sxs-lookup"><span data-stu-id="d6702-118">This significantly reduces the memory consumption and speeds up the process when doing a "test map" or "validate map" operation, compiling the map, or saving the map.</span></span>  
  
 <span data-ttu-id="d6702-119">Sin embargo, cuando la **GenerateDefaultFixedNodes** marca se establece en **No**, los valores de campo predeterminados, establecidos en el esquema de destino no se conservan en la instancia producida por la asignación.</span><span class="sxs-lookup"><span data-stu-id="d6702-119">However, when the **GenerateDefaultFixedNodes** flag is set to **No**, the default field values set in the target schema are not preserved in the instance produced by the map.</span></span> <span data-ttu-id="d6702-120">Esto supone un problema cuando la instancia de destino necesita esos valores.</span><span class="sxs-lookup"><span data-stu-id="d6702-120">This is a problem when these values are required in the target instance.</span></span> <span data-ttu-id="d6702-121">Para evitarlo, hay que establecer los valores necesarios explícitamente en la asignación.</span><span class="sxs-lookup"><span data-stu-id="d6702-121">To circumvent this, the required values have to be set again explicitly in the map.</span></span> <span data-ttu-id="d6702-122">Puede establecer la **GenerateDefaultFixedNodes** indicador en **RequiredDefaults**, lo que significa que las necesarias nodos se tienen en cuenta.</span><span class="sxs-lookup"><span data-stu-id="d6702-122">You can set the **GenerateDefaultFixedNodes** flag to **RequiredDefaults**, which means that all required nodes are taken into account.</span></span> <span data-ttu-id="d6702-123">Esto cubre nodos vinculados, los valores de los nodos que han predeterminado, nodos con el **MinOccurs** propiedad establecida en mayor que o igual a uno y nodos cuyos elementos primarios son necesarios.</span><span class="sxs-lookup"><span data-stu-id="d6702-123">This covers linked nodes, nodes that have default values, nodes with the **MinOccurs** property set to greater than or equal to one, and nodes whose parents are required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6702-124">Después de establecer **GenerateDefaultFixedNodes** a **No** o **RequiredDefaults**, debe comprobar la asignación y comprobar que el resultado es el mismo que cuando  **GenerateDefaultFixedNodes** se establece en su valor predeterminado de **Sí**, en que todos los nodos se tienen en cuenta el compilador.</span><span class="sxs-lookup"><span data-stu-id="d6702-124">After you set **GenerateDefaultFixedNodes** to **No** or **RequiredDefaults**, you should test the map and verify that the output is the same as when **GenerateDefaultFixedNodes** is set to its default value of **Yes**, in which all nodes are taken into account by the compiler.</span></span>  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a><span data-ttu-id="d6702-125">Administrar el uso de for-each con los functoids de condicional, Bucle y Asignación de valores</span><span class="sxs-lookup"><span data-stu-id="d6702-125">Managing for-each Usage with Looping, Conditional, and Value Mapping Functoids</span></span>  
 <span data-ttu-id="d6702-126">Cuando se usa un **bucle** functoid, un **condicional** functoid, o una **Value Mapping** functoid, un `xsl:for-each` instrucción se genera en la asignación compilada.</span><span class="sxs-lookup"><span data-stu-id="d6702-126">When you use a **Looping** functoid, a **Conditional** functoid, or a **Value Mapping** functoid, an `xsl:for-each` statement is generated in the compiled map.</span></span> <span data-ttu-id="d6702-127">Si el campo secundario del esquema de destino tiene un número máximo de apariciones sin enlazar, la instrucción `xsl:for-each` se inserta en el campo secundario.</span><span class="sxs-lookup"><span data-stu-id="d6702-127">If the child field of the destination schema has unbounded maximum occurrences, the `xsl:for-each` statement is put at the child field.</span></span> <span data-ttu-id="d6702-128">Si el campo secundario no tiene un número máximo de apariciones sin enlazar, la instrucción `xsl:for-each` se inserta en el campo primario de ese campo secundario.</span><span class="sxs-lookup"><span data-stu-id="d6702-128">If the child field does not have unbounded maximum occurrences, the `xsl:for-each` statement is put at the parent field of the child field.</span></span>  
  
 <span data-ttu-id="d6702-129">Sin embargo, dado que la ubicación de la `xsl:for-each` instrucción afecta al resultado de la asignación, puede que desee la `xsl:for-each` instrucción se deben colocar en el campo secundario del esquema de destino, independientemente de si se establece el número máximo de apariciones del campo secundario a **1**.</span><span class="sxs-lookup"><span data-stu-id="d6702-129">However, because the location of the `xsl:for-each` statement affects the map result, you may want the `xsl:for-each` statement to be put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
 <span data-ttu-id="d6702-130">Puede controlar la posición de la `xsl:for-each` instrucción modificando el valor de la **TreatElementsAsRecords** de atributo en el archivo de asignación (.btm) tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="d6702-130">You can control the placement of the `xsl:for-each` statement by modifying the value of the **TreatElementsAsRecords** attribute in the map (.btm) file as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="d6702-131">Cuando este atributo se establece en **Sí**, `xsl:for-each` instrucción se coloca en el campo secundario del esquema de destino, independientemente de si el número máximo de apariciones del campo secundario está establecido en **1**.</span><span class="sxs-lookup"><span data-stu-id="d6702-131">When this attribute is set to **Yes**, the `xsl:for-each` statement is put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a><span data-ttu-id="d6702-132">Conservar el orden al asignar un grupo de secuencias repetidas</span><span class="sxs-lookup"><span data-stu-id="d6702-132">Preserving the Order When Mapping a Repeating Sequence Group</span></span>  
 <span data-ttu-id="d6702-133">Los grupos de secuencias de los esquemas XSD no proporcionan un contexto de bucle porque no están representados en la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d6702-133">Sequence groups in XSD schemas do not provide a looping context because they are not represented in the message instance.</span></span> <span data-ttu-id="d6702-134">Al no poder realizar bucles en el grupo de secuencias, el compilador del Asignador no genera el XSLT apropiado para mantener el orden de segmentos.</span><span class="sxs-lookup"><span data-stu-id="d6702-134">Without looping possibilities on the sequence group, the Mapper compiler does not generate the appropriate XSLT to maintain the segment order.</span></span> <span data-ttu-id="d6702-135">Como resultado se pierde el contexto relativo presente en la instancia de entrada, lo que hace a las instancias de salida inútiles para procesamientos posteriores que dependan de dicho contexto relativo.</span><span class="sxs-lookup"><span data-stu-id="d6702-135">As a result, relative context that is present in the input instance is lost, which makes the output instances useless for further processing that depends on the relative context.</span></span>  
  
 <span data-ttu-id="d6702-136">Puede usar el **PreserveSequenceOrder** marca para mantener el orden de los registros al asignar una repetición de secuencia a otra secuencia repetida.</span><span class="sxs-lookup"><span data-stu-id="d6702-136">You can use the **PreserveSequenceOrder** flag to maintain record order when mapping a repeating sequence to another repeating sequence.</span></span> <span data-ttu-id="d6702-137">De forma predeterminada, el valor de la marca se establece en **No** para conservar la funcionalidad de las asignaciones existentes creadas en versiones anteriores [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versiones donde la marca no está presente.</span><span class="sxs-lookup"><span data-stu-id="d6702-137">By default, the value of the flag is set to **No** to preserve the functionality of existing maps created in earlier [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versions where the flag is not present.</span></span> <span data-ttu-id="d6702-138">En las nuevas asignaciones creadas, la marca estará presente con su valor establecido en **No**.</span><span class="sxs-lookup"><span data-stu-id="d6702-138">In the newly created maps, the flag will be present with its value set to **No**.</span></span> <span data-ttu-id="d6702-139">Para mantener el orden de los segmentos, debe establecer explícitamente el valor en **Sí** en los archivos .btm, tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="d6702-139">To maintain segment order, you must explicitly set the value to **Yes** in the .btm files as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="d6702-140">A continuación se da un ejemplo de instancia de entrada:</span><span class="sxs-lookup"><span data-stu-id="d6702-140">The following is a sample input instance:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="d6702-141">Con el **PreserveSequenceOrder** marca establecida en **n**, la instancia de salida tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6702-141">With the **PreserveSequenceOrder** flag set to **No**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="d6702-142">Con el **PreserveSequenceOrder** marca establecida en **Sí**, la instancia de salida tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6702-142">With the **PreserveSequenceOrder** flag set to **Yes**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6702-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6702-143">See Also</span></span>  
 [<span data-ttu-id="d6702-144">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d6702-144">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)