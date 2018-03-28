---
title: Sintaxis de una instrucción EXECQUERY en SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5198335cfa1a7d2036ca05759edc7d04e28cc20b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a><span data-ttu-id="fc92e-102">Sintaxis de una instrucción EXECQUERY en SAP</span><span class="sxs-lookup"><span data-stu-id="fc92e-102">Syntax for an EXECQUERY Statement in SAP</span></span>
<span data-ttu-id="fc92e-103">Puede usar la GUI de SAP para crear consultas seleccionando las tablas que desea consultar, las columnas y el orden que desea incluir en el conjunto de resultados, etcetera gráficamente. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] permite a los usuarios ejecutar estas consultas desde una aplicación de ADO.NET proporcionando una operación EXECQUERY que los usuarios pueden utilizar para ejecutar una consulta definida en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fc92e-103">You can use the SAP GUI to create queries by graphically selecting the tables you want to query, the columns and sort order you want included in the result set, etc. The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] enables users to execute such queries from an ADO.NET application by providing an EXECQUERY operation that users can use to execute a query defined in the SAP system.</span></span>  
  
 <span data-ttu-id="fc92e-104">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] utiliza un Z_EXECUTE_SAP_QUERY RFC personalizada para ejecutar las consultas predefinidas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fc92e-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC Z_EXECUTE_SAP_QUERY to execute the pre-defined queries in the SAP system.</span></span> <span data-ttu-id="fc92e-105">La solicitud de cambio personalizada a su vez ejecuta RSAQ_REMOTE_QUERY_CALL, que es un estándar que RFC definida en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fc92e-105">The custom RFC in turn executes the RSAQ_REMOTE_QUERY_CALL, which is a standard RFC defined in the SAP system.</span></span> <span data-ttu-id="fc92e-106">Por lo tanto, antes de realizar la operación de EXECQUERY, debe instalar la solicitud de cambio personalizada en el sistema SAP que se va a ejecutar las consultas contra.</span><span class="sxs-lookup"><span data-stu-id="fc92e-106">Hence, before you can use the EXECQUERY operation, you must install the custom RFC in the SAP system you will be running your queries against.</span></span> <span data-ttu-id="fc92e-107">Para obtener instrucciones sobre cómo instalar la solicitud de cambio personalizada, consulte [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="fc92e-107">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="fc92e-108">En este tema se proporciona información sobre la sintaxis de la operación de EXECQUERY y otra información útil relacionada con la operación de EXECQUERY.</span><span class="sxs-lookup"><span data-stu-id="fc92e-108">This topic provides information on the syntax of the EXECQUERY operation, and other useful information related to the EXECQUERY operation.</span></span>  
  
## <a name="syntax-for-an-execquery-statement"></a><span data-ttu-id="fc92e-109">Sintaxis de una instrucción EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="fc92e-109">Syntax for an EXECQUERY Statement</span></span>  
 <span data-ttu-id="fc92e-110">En la siguiente sección se describe las especificaciones de gramática para el uso de la operación de EXECQUERY el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc92e-110">The following section describes the grammar specifications for using the EXECQUERY operation against the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 <span data-ttu-id="fc92e-111">donde:</span><span class="sxs-lookup"><span data-stu-id="fc92e-111">where:</span></span>  
  
-   <span data-ttu-id="fc92e-112">**\<Nombredeconsulta\>**  es el nombre de la consulta definida en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fc92e-112">**\<QueryName\>** is the name of the query defined in the SAP system.</span></span>  
  
-   <span data-ttu-id="fc92e-113">**USERGROUP** hace referencia al grupo de usuarios en el que esté definida la consulta.</span><span class="sxs-lookup"><span data-stu-id="fc92e-113">**USERGROUP** refers to the user group in which the query is defined.</span></span> <span data-ttu-id="fc92e-114">Este parámetro es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fc92e-114">This is a mandatory parameter.</span></span>  
  
-   <span data-ttu-id="fc92e-115">**Área de trabajo** hace referencia al área de trabajo en el que esté definida la consulta.</span><span class="sxs-lookup"><span data-stu-id="fc92e-115">**WORKSPACE** refers to the workspace in which the query is defined.</span></span> <span data-ttu-id="fc92e-116">En SAP, hay dos áreas de trabajo: estándar y Global.</span><span class="sxs-lookup"><span data-stu-id="fc92e-116">In SAP, there are two workspaces—Standard and Global.</span></span> <span data-ttu-id="fc92e-117">Proporciona un espacio en blanco para especificar el área de trabajo estándar.</span><span class="sxs-lookup"><span data-stu-id="fc92e-117">Provide an empty space to specify the Standard workspace.</span></span> <span data-ttu-id="fc92e-118">Proporcionar `X` para especificar el área de trabajo Global.</span><span class="sxs-lookup"><span data-stu-id="fc92e-118">Provide `X` to specify the Global workspace.</span></span> <span data-ttu-id="fc92e-119">Valor predeterminado es el espacio vacío.</span><span class="sxs-lookup"><span data-stu-id="fc92e-119">Default is empty space.</span></span>  
  
-   <span data-ttu-id="fc92e-120">**VARIANT** hace referencia a un conjunto de criterios de selección que puede especificar al ejecutar una consulta SAP almacenado.</span><span class="sxs-lookup"><span data-stu-id="fc92e-120">**VARIANT** refers to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="fc92e-121">Por ejemplo, puede usar variantes para especificar valores predeterminados para las consultas.</span><span class="sxs-lookup"><span data-stu-id="fc92e-121">For example, you can use variants to specify default values for queries.</span></span>  
  
-   <span data-ttu-id="fc92e-122">**@Pn** hace referencia al n<sup>th</sup> campo de selección en la definición de consulta SAP.</span><span class="sxs-lookup"><span data-stu-id="fc92e-122">**@Pn** refers to the n<sup>th</sup> selection field in the SAP query definition.</span></span>  
  
-   <span data-ttu-id="fc92e-123">**USEORIGINALCOLUMNNAMES** especifica si el proveedor utiliza los nombres de columna originales del conjunto de datos, tal como aparecen en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fc92e-123">**USEORIGINALCOLUMNNAMES** specifies whether the provider uses the original column names in the DataSet, as they exist in the SAP system.</span></span> <span data-ttu-id="fc92e-124">De forma predeterminada, el proveedor utiliza los nombres descriptivos que se definen en la consulta SAP.</span><span class="sxs-lookup"><span data-stu-id="fc92e-124">By default, the provider uses the friendly names defined in the SAP query.</span></span> <span data-ttu-id="fc92e-125">Sin embargo, si los nombres descriptivos dentro de la consulta no son únicos, el cliente ADO.NET producirá un error al leer los datos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="fc92e-125">However, if the friendly names within the query are not unique, the ADO.NET client will throw an error while reading the data from the DataSet.</span></span> <span data-ttu-id="fc92e-126">En estos escenarios, debe especificar la opción USEORIGINALCOLUMNNAMES, que indica que el proveedor utiliza los nombres de columna originales del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="fc92e-126">In such scenarios, you must specify the USEORIGINALCOLUMNNAMES option, indicating that the provider uses the original column names in the DataSet.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fc92e-127">Siempre debe proporcionar el valor de la palabra clave de opción entre comillas simples, por ejemplo, '*USEORIGINALCOLUMNNAMES*'.</span><span class="sxs-lookup"><span data-stu-id="fc92e-127">You must always provide the value for the OPTION keyword within single quotes, for example, '*USEORIGINALCOLUMNNAMES*'.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc92e-128">Para obtener información acerca de cómo se traducen los parámetros de una consulta de SAP en una sintaxis EXECQUERY, consulte [parámetros de consulta de SAP traducir en el comando EXECQUERY](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span><span class="sxs-lookup"><span data-stu-id="fc92e-128">For information about how the parameters of an SAP Query translate into an EXECQUERY syntax, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="framing-an-execquery-syntax"></a><span data-ttu-id="fc92e-129">Tramas una sintaxis EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="fc92e-129">Framing an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="fc92e-130">Tramas de sintaxis para una operación de EXECQUERY ejecutar una consulta SAP depende de cómo esté definida la consulta en el sistema SAP, incluidos cada valor de parámetro definido en SAP.</span><span class="sxs-lookup"><span data-stu-id="fc92e-130">Framing syntax for an EXECQUERY operation to execute an SAP query depends on how the query is defined in the SAP system, including each parameter value defined in SAP.</span></span> <span data-ttu-id="fc92e-131">Para obtener información sobre cómo enmarcar sintaxis EXECQUERY para ejecutar una consulta SAP, consulte [parámetros de consulta de SAP traducir en el comando EXECQUERY](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span><span class="sxs-lookup"><span data-stu-id="fc92e-131">For information about how to frame EXECQUERY syntax to execute an SAP query, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a><span data-ttu-id="fc92e-132">Consideraciones mientras Using adicional la operación EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="fc92e-132">Additional Considerations While Using the EXECQUERY operation</span></span>  
 <span data-ttu-id="fc92e-133">Esta sección enumeran los puntos que debe tener en cuenta al utilizar la instrucción EXECQUERY con [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc92e-133">This section lists the points that you must keep in mind when using the EXECQUERY statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="fc92e-134">Los valores especificados para USERGROUP, el área de trabajo y la variante se pasan en como-es el estándar RFC de SAP, RSAQ_REMOTE_QUERY_CALL.</span><span class="sxs-lookup"><span data-stu-id="fc92e-134">The values specified for USERGROUP, WORKSPACE, and VARIANT are passed on as-is to the standard SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="fc92e-135">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no valida los valores especificados para estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="fc92e-135">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values specified for these parameters.</span></span>  
  
-   <span data-ttu-id="fc92e-136">Todos los valores devueltos por la operación de EXECQUERY son del tipo de cadena.</span><span class="sxs-lookup"><span data-stu-id="fc92e-136">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
-   <span data-ttu-id="fc92e-137">Palabras clave para nombres de consulta, el grupo de usuarios, el área de trabajo y variantes no distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fc92e-137">Keywords for query names, user group, workspace, and variants are not case sensitive.</span></span> <span data-ttu-id="fc92e-138">Sin embargo, los nombres de parámetro siempre deben estar en caseP superior como @P1, @P2, etcetera. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc92e-138">However, the parameter names must always be in upper caseP such as @P1, @P2, etc. For example:</span></span>  
  
    ```  
    EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
     <span data-ttu-id="fc92e-139">es igual que</span><span class="sxs-lookup"><span data-stu-id="fc92e-139">is the same as</span></span>  
  
    ```  
    EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
-   <span data-ttu-id="fc92e-140">Los operadores admitidos por el EXECQUERY son >, <>, =, < =,! =, no es así y BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="fc92e-140">The operators supported by the EXECQUERY are >, <, >=, <=, !=, NOT, and BETWEEN.</span></span>  
  
-   <span data-ttu-id="fc92e-141">No se admiten caracteres comodín en la operación de EXECQUERY.</span><span class="sxs-lookup"><span data-stu-id="fc92e-141">Wildcard characters are not supported by the EXECQUERY operation.</span></span> <span data-ttu-id="fc92e-142">Por ejemplo, la instrucción siguiente da el resultado esperado:</span><span class="sxs-lookup"><span data-stu-id="fc92e-142">For example, the following statement gives the expected output:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
     <span data-ttu-id="fc92e-143">Sin embargo, la misma consulta cuando se ejecuta con un carácter comodín produce un error.</span><span class="sxs-lookup"><span data-stu-id="fc92e-143">However, the same query when executed with a wildcard character gives an error.</span></span> <span data-ttu-id="fc92e-144">Observe el uso de caracteres comodín para **@P2**.</span><span class="sxs-lookup"><span data-stu-id="fc92e-144">Notice the use of wildcard characters for **@P2**.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
    ```  
  
     <span data-ttu-id="fc92e-145">En este ejemplo, podría obtener un error que indica que se ha encontrado ningún dato.</span><span class="sxs-lookup"><span data-stu-id="fc92e-145">In this example, you might get an error stating that no data was found.</span></span> <span data-ttu-id="fc92e-146">Esto es porque la consulta busca **'\*&\*'** como una cadena y no tiene en cuenta el asterisco (\*) como carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="fc92e-146">This is because the query searches for **'\*&\*'** as a string and does not consider asterisk (\*) as a wildcard character.</span></span>  
  
-   <span data-ttu-id="fc92e-147">Siempre debe especificar los valores de fecha en formato AAAAMMDD.</span><span class="sxs-lookup"><span data-stu-id="fc92e-147">You must always specify a date values in YYYYMMDD format.</span></span>  
  
-   <span data-ttu-id="fc92e-148">Si va a ejecutar una consulta que tiene una variante definida en el sistema SAP, puede especificar el nombre de la variante como parte del comando.</span><span class="sxs-lookup"><span data-stu-id="fc92e-148">If you are executing a query that has a variant defined in the SAP system, you can specify the name of the variant as part of the command.</span></span> <span data-ttu-id="fc92e-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc92e-149">For example:</span></span>  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fc92e-150">No es necesario especificar un nombre variant si se define una variante de forma predeterminada para la consulta en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fc92e-150">You do not need to specify a variant name if a default variant is defined for the query in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc92e-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc92e-151">See Also</span></span>  
 [<span data-ttu-id="fc92e-152">Uso del proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="fc92e-152">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)