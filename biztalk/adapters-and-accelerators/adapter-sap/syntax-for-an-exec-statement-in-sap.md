---
title: "Sintaxis para una instrucción EXEC en SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: EXEC statement, syntax for
ms.assetid: 406b1100-39a0-4321-89c9-ec1b8a3cfdc6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9b2299407986ef2fca53304b536c5ce89625941
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="syntax-for-an-exec-statement-in-sap"></a><span data-ttu-id="44ff6-102">Sintaxis para una instrucción EXEC en SAP</span><span class="sxs-lookup"><span data-stu-id="44ff6-102">Syntax for an EXEC Statement in SAP</span></span>
<span data-ttu-id="44ff6-103">La siguiente sección describe las especificaciones de gramática para implementar instrucciones EXEC en la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44ff6-103">The following section describes grammar specifications for implementing EXEC statements against the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="44ff6-104">Tenga en cuenta que, en muchos casos, la sintaxis es un poco diferente de la sintaxis de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="44ff6-104">Notice that in several cases, the syntax is somewhat different from Transact-SQL syntax.</span></span>  
  
```  
EXEC rfc_name {<argument_element>} [ , …n ]  {;}[0,1] [ OPTION <disabledatavalidation>, <firstresultset> ]  
```  
  
 <span data-ttu-id="44ff6-105">donde:</span><span class="sxs-lookup"><span data-stu-id="44ff6-105">where:</span></span>  
  
-   <span data-ttu-id="44ff6-106">**rfc_name** especifica el nombre de la llamada de función para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="44ff6-106">**rfc_name** specifies the name of the function call to execute.</span></span>  
  
-   <span data-ttu-id="44ff6-107">**< argument_element >** :: = @param_name = [0,1] \<const > {[entrada &#124; SALIDA]} [0,1]</span><span class="sxs-lookup"><span data-stu-id="44ff6-107">**<argument_element>** ::= @param_name = [0,1] \<const> {[ INPUT &#124; OUTPUT ]}[0,1]</span></span>  
  
    -   <span data-ttu-id="44ff6-108">**param_name** especifica el nombre de parámetro definido en la interfaz de la función.</span><span class="sxs-lookup"><span data-stu-id="44ff6-108">**param_name** specifies the parameter name defined in the function interface.</span></span>  
  
    -   <span data-ttu-id="44ff6-109">**\<¿Const >** :: = entero &#124; real &#124; cadena &#124;?</span><span class="sxs-lookup"><span data-stu-id="44ff6-109">**\<const>** ::= integer &#124; real &#124; string &#124; ?</span></span> <span data-ttu-id="44ff6-110">&#124; NULL &#124; xml_element</span><span class="sxs-lookup"><span data-stu-id="44ff6-110">&#124; NULL &#124; xml_element</span></span>  
  
-   <span data-ttu-id="44ff6-111">**OPCIÓN** proporciona la opción en cómo desea presentar los datos.</span><span class="sxs-lookup"><span data-stu-id="44ff6-111">**OPTION**  provides option on how you want to present the data.</span></span> <span data-ttu-id="44ff6-112">Las opciones disponibles son:</span><span class="sxs-lookup"><span data-stu-id="44ff6-112">The available options are:</span></span>  
  
    -   <span data-ttu-id="44ff6-113">**disabledatavalidation** opción establece la **EnableSafeTyping** enlace de propiedad en subyacente [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44ff6-113">**disabledatavalidation** option sets the **EnableSafeTyping** binding property in the underlying [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="44ff6-114">Cuando escriba seguro está habilitado los tipos de datos de archivos DAT, TIM y NUMC se representan como cadenas.</span><span class="sxs-lookup"><span data-stu-id="44ff6-114">When safe typing is enabled the DATS, TIMS, and NUMC data types are represented as strings.</span></span> <span data-ttu-id="44ff6-115">Para obtener más información acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="44ff6-115">For more information about this binding property, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    -   <span data-ttu-id="44ff6-116">**firstresultset** especifica el primer conjunto de resultados devuelto por la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44ff6-116">**firstresultset** specifies the first result set that is returned by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="44ff6-117">Cuando se ejecute la instrucción en un origen de proveedor ADO, solo el primer conjunto de resultados devuelto está disponible.</span><span class="sxs-lookup"><span data-stu-id="44ff6-117">When any statement is executed on an ADO Provider source, only the first result set returned is available.</span></span> <span data-ttu-id="44ff6-118">Para escenarios de RFC EXEC, normalmente varios parámetros de la tabla se devuelven, pero está disponibles para el programa cliente, que no puede ser útil si solo el primer conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="44ff6-118">For RFC EXEC scenarios, usually multiple table parameters are returned but if only the first result set is available for the client program, which might not be of use.</span></span> <span data-ttu-id="44ff6-119">Al especificar la palabra clave "firstresultset" como parte de la cláusula OPTION, los clientes pueden especificar el primer parámetro de la tabla que desean usar el proveedor para devolver.</span><span class="sxs-lookup"><span data-stu-id="44ff6-119">By specifying the “firstresultset” keyword as part of the OPTION clause, clients can specify the first table parameter that they want the Provider to return.</span></span> <span data-ttu-id="44ff6-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="44ff6-120">For example:</span></span>  
  
        ```  
        EXEC Z_TEST_ALL_TYPES @P_IN='TestInput' OPTION 'disabledatavalidation', firstresultset TAB_ALLTYPES'  
        ```  
  
         <span data-ttu-id="44ff6-121">En este ejemplo, la instrucción EXEC especifica que el primer parámetro de tabla devuelto debería ser TAB_ALLTYPES.</span><span class="sxs-lookup"><span data-stu-id="44ff6-121">In this example, the EXEC statement specifies that the first table parameter returned should be TAB_ALLTYPES.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="44ff6-122">Siempre debe proporcionar los valores de la palabra clave de opción entre comillas simples, por ejemplo, '*disabledatavalidation*'.</span><span class="sxs-lookup"><span data-stu-id="44ff6-122">You must always provide the values for the OPTION keyword within single quotes, for example, '*disabledatavalidation*'.</span></span>  
  
 <span data-ttu-id="44ff6-123">En la sintaxis anterior, xml_element puede utilizarse para proporcionar la entrada para los tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="44ff6-123">In the preceding syntax, xml_element can be used to provide input for complex types.</span></span> <span data-ttu-id="44ff6-124">La estructura del elemento xml será diferente para las estructuras y tablas.</span><span class="sxs-lookup"><span data-stu-id="44ff6-124">The xml element structure will be different for structures and tables.</span></span> <span data-ttu-id="44ff6-125">El xml_element de estructura es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="44ff6-125">The xml_element for structure resembles the following:</span></span>  
  
```  
<PARAM_NAME>  
    <FIELDNAME_1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_1>  
    <FIELDNAME_2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_2>  
    ...  
    ...  
\</ PARAM_NAME>  
```  
  
 <span data-ttu-id="44ff6-126">El xml_element de tabla es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="44ff6-126">The xml_element for table resembles the following:</span></span>  
  
```  
<PARAM_NAME>  
    <STRUCT_NAME  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
        <FIELDNAME_1>value</FIELDNAME_1>  
    <STRUCT_NAME/>  
    <STRUCT_NAME  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
        <FIELDNAME_1>value</FIELDNAME_1>  
    <STRUCT_NAME/>  
    ...  
    ...  
\</ PARAM_NAME>  
```  
  
 <span data-ttu-id="44ff6-127">Por ejemplo, el elemento XML de un tipo de estructura es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="44ff6-127">For example, the XML element for a structure type resembles the following:</span></span>  
  
```  
<INOUT_STRUCT>  
       <ACCPFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006</ACCPFIELD>  
       <CHARFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">John</CHARFIELD>                 
</INOUT_STRUCT>  
```  
  
 <span data-ttu-id="44ff6-128">De forma similar, el elemento XML de un tipo de tabla es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="44ff6-128">Similarly, the XML element for a table type resembles the following:</span></span>  
  
```  
<TAB_ALLTYPES>   
<ZZSTRUCTALLTYPES_RFC xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
       <ACCPFIELD>2006</ACCPFIELD>  
       <CHARFIELD>John</CHARFIELD>                          
</ZZSTRUCTALLTYPES_RFC>  
<ZZSTRUCTALLTYPES_RFC xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
       <ACCPFIELD>2007</ACCPFIELD>  
       <CHARFIELD>James</CHARFIELD>                          
</ZZSTRUCTALLTYPES_RFC>  
</TAB_ALLTYPES>  
```  
  
 <span data-ttu-id="44ff6-129">Por ejemplo, vea [ejemplos de la instrucción EXEC](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).</span><span class="sxs-lookup"><span data-stu-id="44ff6-129">For example statements, see [Examples for EXEC Statement](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).</span></span>  
  
## <a name="handling-named-parameters"></a><span data-ttu-id="44ff6-130">Control de parámetros con nombre</span><span class="sxs-lookup"><span data-stu-id="44ff6-130">Handling Named Parameters</span></span>  
 <span data-ttu-id="44ff6-131">Éstas son directrices para especificar parámetros con nombre en las consultas EXEC:</span><span class="sxs-lookup"><span data-stu-id="44ff6-131">The following are guidelines for specifying named parameters in EXEC queries:</span></span>  
  
-   <span data-ttu-id="44ff6-132">Debe especificar los parámetros por nombre (por ejemplo, @param_name= value).</span><span class="sxs-lookup"><span data-stu-id="44ff6-132">You must specify parameters by naming them (for example, @param_name=value).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44ff6-133">No se admiten parámetros sin nombre</span><span class="sxs-lookup"><span data-stu-id="44ff6-133">Unnamed parameters are not supported</span></span>  
  
-   <span data-ttu-id="44ff6-134">Cuando se define un parámetro con un valor predeterminado, puede ejecutar el procedimiento sin especificar un parámetro.</span><span class="sxs-lookup"><span data-stu-id="44ff6-134">When a parameter is defined using a default value, you can execute the procedure without specifying a parameter.</span></span>  
  
-   <span data-ttu-id="44ff6-135">Las consultas EXEC no admiten el uso de parámetros con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="44ff6-135">EXEC queries do not support using parameters with the following properties:</span></span>  
  
    -   <span data-ttu-id="44ff6-136">Estructuras anidadas (estructuras que contienen estructuras como sus campos).</span><span class="sxs-lookup"><span data-stu-id="44ff6-136">Nested structures (structures that contain structures as their fields).</span></span>  
  
    -   <span data-ttu-id="44ff6-137">Tablas anidadas.</span><span class="sxs-lookup"><span data-stu-id="44ff6-137">Nested tables.</span></span>  
  
    -   <span data-ttu-id="44ff6-138">Una tabla que contiene una estructura.</span><span class="sxs-lookup"><span data-stu-id="44ff6-138">A table containing a structure.</span></span>  
  
    -   <span data-ttu-id="44ff6-139">Una estructura que contiene una tabla.</span><span class="sxs-lookup"><span data-stu-id="44ff6-139">A structure containing a table.</span></span>  
  
    -   <span data-ttu-id="44ff6-140">Una estructura o una tabla que tiene campos con tipos de cadena compuesta, por ejemplo `SSTRING` o `RAWSTRING`.</span><span class="sxs-lookup"><span data-stu-id="44ff6-140">A structure or table that has fields with composite string types, for example `SSTRING` or `RAWSTRING`.</span></span>  
  
     <span data-ttu-id="44ff6-141">En la tabla siguiente se enumera las asignaciones lógicas entre los tipos de parámetro RFC y direcciones de parámetro al ejecutar una solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="44ff6-141">The following table lists logical mappings between RFC parameter types and parameter directions when executing an RFC.</span></span>  
  
    |<span data-ttu-id="44ff6-142">Tipo de parámetro RFC</span><span class="sxs-lookup"><span data-stu-id="44ff6-142">RFC Param Type</span></span>|<span data-ttu-id="44ff6-143">Palabra clave de consulta</span><span class="sxs-lookup"><span data-stu-id="44ff6-143">Query Keyword</span></span>|<span data-ttu-id="44ff6-144">Dirección del parámetro</span><span class="sxs-lookup"><span data-stu-id="44ff6-144">Parameter Direction</span></span>|  
    |--------------------|-------------------|-------------------------|  
    |<span data-ttu-id="44ff6-145">Importación de parámetros</span><span class="sxs-lookup"><span data-stu-id="44ff6-145">Import parameters</span></span>|<span data-ttu-id="44ff6-146">Nada</span><span class="sxs-lookup"><span data-stu-id="44ff6-146">Nothing</span></span>|<span data-ttu-id="44ff6-147">Paramdirection.Input</span><span class="sxs-lookup"><span data-stu-id="44ff6-147">Paramdirection.Input</span></span>|  
    |<span data-ttu-id="44ff6-148">Parámetros de exportación</span><span class="sxs-lookup"><span data-stu-id="44ff6-148">Export parameters</span></span>|<span data-ttu-id="44ff6-149">Salida</span><span class="sxs-lookup"><span data-stu-id="44ff6-149">Output</span></span>|<span data-ttu-id="44ff6-150">Paramdirection.Output</span><span class="sxs-lookup"><span data-stu-id="44ff6-150">Paramdirection.Output</span></span>|  
    |<span data-ttu-id="44ff6-151">Parámetros de la tabla</span><span class="sxs-lookup"><span data-stu-id="44ff6-151">Table parameters</span></span>|<span data-ttu-id="44ff6-152">Salida/Nothing</span><span class="sxs-lookup"><span data-stu-id="44ff6-152">Output/Nothing</span></span>|<span data-ttu-id="44ff6-153">InputOutput</span><span class="sxs-lookup"><span data-stu-id="44ff6-153">InputOutput</span></span>|  
  
 <span data-ttu-id="44ff6-154">Los siguientes son directrices generales para controlar parámetros:</span><span class="sxs-lookup"><span data-stu-id="44ff6-154">The following are general guidelines for handling parameters:</span></span>  
  
-   <span data-ttu-id="44ff6-155">Puede especificar valores de parámetros como constantes o mediante el uso de marcadores de posición en la consulta.</span><span class="sxs-lookup"><span data-stu-id="44ff6-155">You can specify parameter values either as constants or by using placeholders in the query.</span></span>  
  
-   <span data-ttu-id="44ff6-156">Cuando se usa marcadores de posición en la consulta, debe crear un `SAPParameter` y agregarlo al objeto de comando correspondiente.</span><span class="sxs-lookup"><span data-stu-id="44ff6-156">When using placeholders in the query, you must create a `SAPParameter` object and add it to the corresponding command object.</span></span> <span data-ttu-id="44ff6-157">A continuación, pasar el nombre de marcador de posición para el constructor; la dirección y el valor dependen del contexto.</span><span class="sxs-lookup"><span data-stu-id="44ff6-157">You then pass the placeholder name to the constructor; the direction and value depend on the context.</span></span>  
  
    -   <span data-ttu-id="44ff6-158">Para `Input` parámetros, no se especifica en la consulta una palabra clave para la dirección del parámetro.</span><span class="sxs-lookup"><span data-stu-id="44ff6-158">For `Input` parameters, do not specify in the query a keyword for the parameter direction.</span></span> <span data-ttu-id="44ff6-159">El `value` debe establecerse el campo del objeto de parámetro o el proveedor iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="44ff6-159">The `value` field of the parameter object must be set, or the provider will throw an exception.</span></span> <span data-ttu-id="44ff6-160">No debe establecer explícitamente la `direction` campo del objeto de parámetro, porque el proveedor predeterminado es `Input`.</span><span class="sxs-lookup"><span data-stu-id="44ff6-160">You must not explicitly set the `direction` field of the parameter object, because the provider defaults to `Input`.</span></span>  
  
    -   <span data-ttu-id="44ff6-161">Otros parámetros, utilice el formato `@paramname=@placeholder` y especifique el `Output` palabra clave explícitamente en la consulta.</span><span class="sxs-lookup"><span data-stu-id="44ff6-161">For other parameters, use the form `@paramname=@placeholder` and specify the `Output` keyword explicitly in the query.</span></span> <span data-ttu-id="44ff6-162">A continuación, debe agregar una `SAPParameter` que se corresponde con el marcador de posición y se establece explícitamente la dirección del parámetro como `ParamDirection.Output` o `ParamDirection.InputOutput`, según el tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="44ff6-162">You must then add a `SAPParameter` that corresponds with the placeholder and explicitly set the parameter direction to either `ParamDirection.Output` or `ParamDirection.InputOutput`, depending on the parameter type.</span></span>  
  
-   <span data-ttu-id="44ff6-163">Nombres de parámetro y los nombres de marcador de posición no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="44ff6-163">Parameter names and placeholder names are not case-sensitive.</span></span>  
  
-   <span data-ttu-id="44ff6-164">No se puede repetir los nombres de parámetro en una consulta a menos que tengan direcciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="44ff6-164">Parameter names cannot be repeated in a query unless they have different directions.</span></span>  
  
-   <span data-ttu-id="44ff6-165">No se puede repetir los nombres de marcador de posición en una consulta.</span><span class="sxs-lookup"><span data-stu-id="44ff6-165">Placeholder names cannot be repeated in a query.</span></span>  
  
## <a name="considerations-when-calling-an-exec-statement"></a><span data-ttu-id="44ff6-166">Consideraciones al llamar a una instrucción EXEC</span><span class="sxs-lookup"><span data-stu-id="44ff6-166">Considerations When Calling an EXEC Statement</span></span>  
 <span data-ttu-id="44ff6-167">Esta sección enumeran los puntos que debe tener en cuenta al utilizar la instrucción EXEC con [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44ff6-167">This section lists the points that you must keep in mind when using the EXEC statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="44ff6-168">Para una instrucción EXEC, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] devuelve `TIMS` valores de campo como .NET `System.DateTime` objetos.</span><span class="sxs-lookup"><span data-stu-id="44ff6-168">For an EXEC statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `TIMS` field values as .NET `System.DateTime` objects.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44ff6-169">Para una instrucción SELECT, la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] devuelve `TIMS` valores de campo como .NET `System.TimeSpan` objetos.</span><span class="sxs-lookup"><span data-stu-id="44ff6-169">For a SELECT statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `TIMS` field values as .NET `System.TimeSpan` objects.</span></span> <span data-ttu-id="44ff6-170">Para obtener más información acerca de la instrucción SELECT, vea [sintaxis para una instrucción SELECT en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="44ff6-170">For more information about the SELECT statement, see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44ff6-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="44ff6-171">See Also</span></span>  
 [<span data-ttu-id="44ff6-172">Sobre el proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="44ff6-172">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)