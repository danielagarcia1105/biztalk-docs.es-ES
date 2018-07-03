---
title: Sintaxis de una instrucción EXECQUERY en SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf479438a5b0960a66b35ef7946df63d088284b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982021"
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a><span data-ttu-id="1f75d-102">Sintaxis de una instrucción EXECQUERY en SAP</span><span class="sxs-lookup"><span data-stu-id="1f75d-102">Syntax for an EXECQUERY Statement in SAP</span></span>
<span data-ttu-id="1f75d-103">Puede usar la GUI de SAP para crear consultas seleccionando gráficamente las tablas que desea consultar, las columnas y el orden que desea incluir en el conjunto de resultados, etcetera. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] permite a los usuarios ejecutar estas consultas desde una aplicación de ADO.NET proporcionando una operación de EXECQUERY que los usuarios pueden usar para ejecutar una consulta definida en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="1f75d-103">You can use the SAP GUI to create queries by graphically selecting the tables you want to query, the columns and sort order you want included in the result set, etc. The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] enables users to execute such queries from an ADO.NET application by providing an EXECQUERY operation that users can use to execute a query defined in the SAP system.</span></span>  
  
 <span data-ttu-id="1f75d-104">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] usa un Z_EXECUTE_SAP_QUERY RFC personalizadas para ejecutar las consultas predefinidas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="1f75d-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC Z_EXECUTE_SAP_QUERY to execute the pre-defined queries in the SAP system.</span></span> <span data-ttu-id="1f75d-105">La RFC personalizada a su vez ejecuta la RSAQ_REMOTE_QUERY_CALL, que es un estándar que RFC definida en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="1f75d-105">The custom RFC in turn executes the RSAQ_REMOTE_QUERY_CALL, which is a standard RFC defined in the SAP system.</span></span> <span data-ttu-id="1f75d-106">Por lo tanto, antes de realizar la operación de EXECQUERY, debe instalar la RFC personalizada en el sistema SAP que se va a ejecutar las consultas contra.</span><span class="sxs-lookup"><span data-stu-id="1f75d-106">Hence, before you can use the EXECQUERY operation, you must install the custom RFC in the SAP system you will be running your queries against.</span></span> <span data-ttu-id="1f75d-107">Para obtener instrucciones sobre cómo instalar la RFC personalizada, consulte [instalar RFC personalizadas para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="1f75d-107">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="1f75d-108">En este tema se proporciona información sobre la sintaxis de la operación de EXECQUERY y otra información útil relacionada con la operación de EXECQUERY.</span><span class="sxs-lookup"><span data-stu-id="1f75d-108">This topic provides information on the syntax of the EXECQUERY operation, and other useful information related to the EXECQUERY operation.</span></span>  
  
## <a name="syntax-for-an-execquery-statement"></a><span data-ttu-id="1f75d-109">Sintaxis de una instrucción EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="1f75d-109">Syntax for an EXECQUERY Statement</span></span>  
 <span data-ttu-id="1f75d-110">La siguiente sección describe las especificaciones de gramática para el uso de la operación de EXECQUERY contra el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f75d-110">The following section describes the grammar specifications for using the EXECQUERY operation against the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 <span data-ttu-id="1f75d-111">donde:</span><span class="sxs-lookup"><span data-stu-id="1f75d-111">where:</span></span>  
  
- <span data-ttu-id="1f75d-112">**\<QueryName\>**  es el nombre de la consulta definida en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="1f75d-112">**\<QueryName\>** is the name of the query defined in the SAP system.</span></span>  
  
- <span data-ttu-id="1f75d-113">**Grupo de usuarios** hace referencia al grupo de usuarios en el que se define la consulta.</span><span class="sxs-lookup"><span data-stu-id="1f75d-113">**USERGROUP** refers to the user group in which the query is defined.</span></span> <span data-ttu-id="1f75d-114">Este parámetro es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1f75d-114">This is a mandatory parameter.</span></span>  
  
- <span data-ttu-id="1f75d-115">**Área de trabajo** hace referencia al área de trabajo en el que se define la consulta.</span><span class="sxs-lookup"><span data-stu-id="1f75d-115">**WORKSPACE** refers to the workspace in which the query is defined.</span></span> <span data-ttu-id="1f75d-116">En SAP, hay dos áreas de trabajo, estándar y Global.</span><span class="sxs-lookup"><span data-stu-id="1f75d-116">In SAP, there are two workspaces—Standard and Global.</span></span> <span data-ttu-id="1f75d-117">Proporciona un espacio en blanco para especificar el área de trabajo estándar.</span><span class="sxs-lookup"><span data-stu-id="1f75d-117">Provide an empty space to specify the Standard workspace.</span></span> <span data-ttu-id="1f75d-118">Proporcionar `X` para especificar el área de trabajo Global.</span><span class="sxs-lookup"><span data-stu-id="1f75d-118">Provide `X` to specify the Global workspace.</span></span> <span data-ttu-id="1f75d-119">El valor predeterminado es un espacio vacío.</span><span class="sxs-lookup"><span data-stu-id="1f75d-119">Default is empty space.</span></span>  
  
- <span data-ttu-id="1f75d-120">**VARIANT** hace referencia a un conjunto de criterios de selección que se pueden especificar al ejecutar una consulta SAP guardadas.</span><span class="sxs-lookup"><span data-stu-id="1f75d-120">**VARIANT** refers to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="1f75d-121">Por ejemplo, puede usar las variantes para especificar los valores predeterminados para las consultas.</span><span class="sxs-lookup"><span data-stu-id="1f75d-121">For example, you can use variants to specify default values for queries.</span></span>  
  
- <span data-ttu-id="1f75d-122"><strong>@Pn</strong> hace referencia a la n<sup>th</sup> campo de selección en la definición de consulta SAP.</span><span class="sxs-lookup"><span data-stu-id="1f75d-122"><strong>@Pn</strong> refers to the n<sup>th</sup> selection field in the SAP query definition.</span></span>  
  
- <span data-ttu-id="1f75d-123">**USEORIGINALCOLUMNNAMES** especifica si el proveedor usa los nombres de columna original en el conjunto de datos, tal y como aparecen en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="1f75d-123">**USEORIGINALCOLUMNNAMES** specifies whether the provider uses the original column names in the DataSet, as they exist in the SAP system.</span></span> <span data-ttu-id="1f75d-124">De forma predeterminada, el proveedor utiliza los nombres descriptivos que se definen en la consulta SAP.</span><span class="sxs-lookup"><span data-stu-id="1f75d-124">By default, the provider uses the friendly names defined in the SAP query.</span></span> <span data-ttu-id="1f75d-125">Sin embargo, si los nombres descriptivos dentro de la consulta no son únicos, el cliente ADO.NET producirá un error al leer los datos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="1f75d-125">However, if the friendly names within the query are not unique, the ADO.NET client will throw an error while reading the data from the DataSet.</span></span> <span data-ttu-id="1f75d-126">En estos escenarios, debe especificar la opción USEORIGINALCOLUMNNAMES, que indica que el proveedor utiliza los nombres de columna original en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="1f75d-126">In such scenarios, you must specify the USEORIGINALCOLUMNNAMES option, indicating that the provider uses the original column names in the DataSet.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="1f75d-127">Siempre debe proporcionar el valor de la palabra clave de opción entre comillas simples, por ejemplo, '*USEORIGINALCOLUMNNAMES*'.</span><span class="sxs-lookup"><span data-stu-id="1f75d-127">You must always provide the value for the OPTION keyword within single quotes, for example, '*USEORIGINALCOLUMNNAMES*'.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f75d-128">Para obtener información acerca de cómo se traducen los parámetros de una consulta de SAP en una sintaxis EXECQUERY, consulte [parámetros de consulta de SAP traducen en comandos de EXECQUERY](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span><span class="sxs-lookup"><span data-stu-id="1f75d-128">For information about how the parameters of an SAP Query translate into an EXECQUERY syntax, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="framing-an-execquery-syntax"></a><span data-ttu-id="1f75d-129">Tramas una sintaxis EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="1f75d-129">Framing an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="1f75d-130">Tramas de sintaxis para una operación de EXECQUERY ejecutar una consulta SAP depende de cómo se define la consulta en el sistema SAP, incluidos cada valor de parámetro definido en SAP.</span><span class="sxs-lookup"><span data-stu-id="1f75d-130">Framing syntax for an EXECQUERY operation to execute an SAP query depends on how the query is defined in the SAP system, including each parameter value defined in SAP.</span></span> <span data-ttu-id="1f75d-131">Para obtener información sobre cómo enmarcar sintaxis EXECQUERY para ejecutar una consulta de SAP, consulte [parámetros de consulta de SAP traducen en comandos de EXECQUERY](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span><span class="sxs-lookup"><span data-stu-id="1f75d-131">For information about how to frame EXECQUERY syntax to execute an SAP query, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a><span data-ttu-id="1f75d-132">Consideraciones mientras Using adicional la operación de EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="1f75d-132">Additional Considerations While Using the EXECQUERY operation</span></span>  
 <span data-ttu-id="1f75d-133">Esta sección enumeran los puntos que debe tener en cuenta al utilizar la instrucción EXECQUERY con [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f75d-133">This section lists the points that you must keep in mind when using the EXECQUERY statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
- <span data-ttu-id="1f75d-134">Los valores especificados para el grupo de usuarios, área de trabajo y variante se pasan como-es el estándar RFC de SAP, RSAQ_REMOTE_QUERY_CALL.</span><span class="sxs-lookup"><span data-stu-id="1f75d-134">The values specified for USERGROUP, WORKSPACE, and VARIANT are passed on as-is to the standard SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="1f75d-135">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no valida los valores especificados para estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="1f75d-135">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values specified for these parameters.</span></span>  
  
- <span data-ttu-id="1f75d-136">Todos los valores devueltos por la operación de EXECQUERY son del tipo de cadena.</span><span class="sxs-lookup"><span data-stu-id="1f75d-136">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
- <span data-ttu-id="1f75d-137">Palabras clave para los nombres de consulta, grupo de usuarios, área de trabajo y variantes no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1f75d-137">Keywords for query names, user group, workspace, and variants are not case sensitive.</span></span> <span data-ttu-id="1f75d-138">Sin embargo, los nombres de parámetro siempre deben estar en caseP superior como @P1, @P2, etcetera. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1f75d-138">However, the parameter names must always be in upper caseP such as @P1, @P2, etc. For example:</span></span>  
  
  ```  
  EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
   <span data-ttu-id="1f75d-139">es igual que</span><span class="sxs-lookup"><span data-stu-id="1f75d-139">is the same as</span></span>  
  
  ```  
  EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
- <span data-ttu-id="1f75d-140">Los operadores admitidos por el EXECQUERY son >, <>, =, < =,! =, NOT y BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="1f75d-140">The operators supported by the EXECQUERY are >, <, >=, <=, !=, NOT, and BETWEEN.</span></span>  
  
- <span data-ttu-id="1f75d-141">No se admiten caracteres comodín por la operación de EXECQUERY.</span><span class="sxs-lookup"><span data-stu-id="1f75d-141">Wildcard characters are not supported by the EXECQUERY operation.</span></span> <span data-ttu-id="1f75d-142">Por ejemplo, la siguiente instrucción proporciona el resultado esperado:</span><span class="sxs-lookup"><span data-stu-id="1f75d-142">For example, the following statement gives the expected output:</span></span>  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
  ```  
  
   <span data-ttu-id="1f75d-143">Sin embargo, en la misma consulta cuando se ejecuta con un carácter comodín se produce un error.</span><span class="sxs-lookup"><span data-stu-id="1f75d-143">However, the same query when executed with a wildcard character gives an error.</span></span> <span data-ttu-id="1f75d-144">Tenga en cuenta el uso de caracteres comodín para <strong>@P2</strong>.</span><span class="sxs-lookup"><span data-stu-id="1f75d-144">Notice the use of wildcard characters for <strong>@P2</strong>.</span></span>  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
  ```  
  
   <span data-ttu-id="1f75d-145">En este ejemplo, podría obtener un error que indica que se ha encontrado ningún dato.</span><span class="sxs-lookup"><span data-stu-id="1f75d-145">In this example, you might get an error stating that no data was found.</span></span> <span data-ttu-id="1f75d-146">Esto es porque la consulta busca **'\*&\*'** como una cadena y no tiene en cuenta el asterisco (\*) como carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="1f75d-146">This is because the query searches for **'\*&\*'** as a string and does not consider asterisk (\*) as a wildcard character.</span></span>  
  
- <span data-ttu-id="1f75d-147">Siempre debe especificar los valores de fecha en formato AAAAMMDD.</span><span class="sxs-lookup"><span data-stu-id="1f75d-147">You must always specify a date values in YYYYMMDD format.</span></span>  
  
- <span data-ttu-id="1f75d-148">Si va a ejecutar una consulta que tiene una variante definida en el sistema SAP, puede especificar el nombre de la variante como parte del comando.</span><span class="sxs-lookup"><span data-stu-id="1f75d-148">If you are executing a query that has a variant defined in the SAP system, you can specify the name of the variant as part of the command.</span></span> <span data-ttu-id="1f75d-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1f75d-149">For example:</span></span>  
  
  ```  
  EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
  ```  
  
  > [!NOTE]
  >  <span data-ttu-id="1f75d-150">No es necesario especificar un nombre de la variante si se define una variante de forma predeterminada para la consulta en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="1f75d-150">You do not need to specify a variant name if a default variant is defined for the query in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f75d-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f75d-151">See Also</span></span>  
 [<span data-ttu-id="1f75d-152">Uso del proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="1f75d-152">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)