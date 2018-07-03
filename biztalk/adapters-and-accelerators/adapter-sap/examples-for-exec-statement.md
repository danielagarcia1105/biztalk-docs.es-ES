---
title: Ejemplos de la instrucción EXEC de mySAP adaptador en BizTalk | Microsoft Docs
description: Ejemplos EXEC y los ejemplos de uso del adaptador de mySAP en módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad2691f4-34bb-423c-9b3e-4abe2d55ddac
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59bdabcba48d00bdf1d6c884ae1f2b469d858626
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992597"
---
# <a name="examples-for-exec-statement"></a><span data-ttu-id="c53b0-103">Ejemplos de la instrucción EXEC</span><span class="sxs-lookup"><span data-stu-id="c53b0-103">Examples for EXEC Statement</span></span>
<span data-ttu-id="c53b0-104">En este tema se muestra la sintaxis de ejemplo para diversas instrucciones EXEC.</span><span class="sxs-lookup"><span data-stu-id="c53b0-104">This topic shows example syntax for various EXEC statements.</span></span>

## <a name="sample-statements"></a><span data-ttu-id="c53b0-105">Instrucciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c53b0-105">Sample statements</span></span> 
  
-   <span data-ttu-id="c53b0-106">Para ejecutar una BAPI que no toma ningún parámetro de entrada, utilice la siguiente sintaxis; se devuelven datos a través de un **DataReader** objeto:</span><span class="sxs-lookup"><span data-stu-id="c53b0-106">To execute a BAPI that takes no input parameters, use the following syntax; data is returned through a **DataReader** object:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST  
    ```  
  
-   <span data-ttu-id="c53b0-107">Para ejecutar una solicitud de cambio que toma parámetros de entrada, utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="c53b0-107">To execute an RFC that takes input parameters, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @NAME1='Contoso'  
    ```  
  
-   <span data-ttu-id="c53b0-108">Para ejecutar una solicitud de cambio que toma parámetros de entrada especificados como una variable, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="c53b0-108">To execute an RFC that takes input parameters specified as a variable, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @var=@var  
    ```  
  
     <span data-ttu-id="c53b0-109">En este ejemplo, debe crear un parámetro denominado `@var` y establezca el valor de forma explícita (por ejemplo, para 1001), dado que el primer parámetro para RFC_CUSTOMER_GET corresponde a KUNNR (número de cliente)</span><span class="sxs-lookup"><span data-stu-id="c53b0-109">In this example, you must create a parameter named `@var` and set the value explicitly (for example, to 1001), because the first parameter for RFC_CUSTOMER_GET corresponds to KUNNR (Customer Number)</span></span>  
  
-   <span data-ttu-id="c53b0-110">Para ejecutar una solicitud de cambio que usa una variable para el nombre de parámetro de entrada, utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="c53b0-110">To execute an RFC that uses a variable for the input parameter name, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @KUNNR=@var1, @NAME1='Contoso'  
    ```  
  
     <span data-ttu-id="c53b0-111">Debe crear un parámetro denominado `@var1`, especifique el valor y, a continuación, enlazarlo al objeto de comando correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c53b0-111">You must create a parameter named `@var1`, specify the value, and then bind it to the corresponding command object.</span></span> <span data-ttu-id="c53b0-112">La dirección predeterminada del objeto parameter recién creado es `input`.</span><span class="sxs-lookup"><span data-stu-id="c53b0-112">The default direction of the newly created parameter object is `input`.</span></span>  
  
-   <span data-ttu-id="c53b0-113">Para ejecutar una BAPI y tablas de valor devueltas como un parámetro, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="c53b0-113">To execute a BAPI and return tables as a parameter, use the following syntax:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST @COMPANYCODE_LIST=@var1 OUTPUT  
    ```  
  
     <span data-ttu-id="c53b0-114">Debe crear un parámetro denominado `@var1`, especifique el valor y enlácelo al objeto de comando correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c53b0-114">You must create a parameter named `@var1`, specify the value, and bind it to the corresponding command object.</span></span> <span data-ttu-id="c53b0-115">Debe ser la dirección del objeto parameter recién creado `InputOutput` o `Output`.</span><span class="sxs-lookup"><span data-stu-id="c53b0-115">The direction of the newly created parameter object should be `InputOutput` or `Output`.</span></span>  
  
-   <span data-ttu-id="c53b0-116">El siguiente ejemplo EXEC usa un parámetro de tipo complejo de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c53b0-116">The following EXEC example uses a table complex type parameter.</span></span> <span data-ttu-id="c53b0-117">En el ejemplo, @fields es un parámetro de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c53b0-117">In the example, @fields is a TABLE parameter.</span></span>  
  
    ```  
    exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
                <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKL</FIELDNAME>  
                </RFC_DB_FLD>  
                <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                    <FIELDNAME>BANKS</FIELDNAME>  
                </RFC_DB_FLD>  
              </FIELDS>', @fields=@flds output  
    ```  
  
-   <span data-ttu-id="c53b0-118">En el siguiente ejemplo EXEC usa un tipo complejo de STRUCT.</span><span class="sxs-lookup"><span data-stu-id="c53b0-118">The following EXEC example uses a STRUCT complex type.</span></span> <span data-ttu-id="c53b0-119">En el ejemplo, @equimaster es un parámetro STRUCT.</span><span class="sxs-lookup"><span data-stu-id="c53b0-119">In the example, @equimaster is a STRUCT parameter.</span></span>  
  
    ```  
    exec BAPI_EQMT_MODIFY @equipment='000000000000000637', @equimaster='<EQUIMASTER>           
                <EQUIPMENT xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">equip</EQUIPMENT>  
                <EQUICATGRY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">E</EQUICATGRY>  
                <MATERIAL xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">mat</MATERIAL>  
              </EQUIMASTER >', @equimaster=@em output  
    ```  
  
## <a name="support-for-complex-parameter-types"></a><span data-ttu-id="c53b0-120">Compatibilidad con tipos de parámetros complejos</span><span class="sxs-lookup"><span data-stu-id="c53b0-120">Support for Complex Parameter Types</span></span>  
 <span data-ttu-id="c53b0-121">Hay dos maneras para admitir parámetros complejos de RFC (tablas y estructuras) cuando se usa el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c53b0-121">There are two ways to support complex RFC parameters (tables and structures) when you use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span></span>  
  
- <span data-ttu-id="c53b0-122">Proporcione un valor XML en línea para el tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="c53b0-122">Provide an inline XML value for the complex type.</span></span> <span data-ttu-id="c53b0-123">En este ejemplo se muestra cómo pasar XML al tipo de parámetro complejos *campos*.</span><span class="sxs-lookup"><span data-stu-id="c53b0-123">This example shows how to pass XML to the complex parameter type *fields*.</span></span> <span data-ttu-id="c53b0-124">En el ejemplo siguiente, <em>@fields</em> es un parámetro de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c53b0-124">In the following example, <em>@fields</em> is a table parameter.</span></span>  
  
  ```  
  exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
              <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                <FIELDNAME>BANKL</FIELDNAME>  
              </RFC_DB_FLD>  
              <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKS</FIELDNAME>  
              </RFC_DB_FLD>  
            </FIELDS>', @fields=@flds output  
  ```  
  
- <span data-ttu-id="c53b0-125">Crear un **DataTable** parámetro con columnas de los campos en el tipo complejo y establezca el parámetro SAP valor en **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c53b0-125">Create a **DataTable** parameter with columns for the fields in the complex type and set the SAP parameter value to **DataTable**.</span></span> <span data-ttu-id="c53b0-126">En este ejemplo se muestra cómo establecer el @fields tipo complejo mediante el uso de un **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c53b0-126">This example shows how to set the @fields complex type by using a **DataTable**.</span></span>  
  
  ```  
  cmd.CommandText = "exec rfc_read_table @query_table='BNKA', @fields = @p_fields";  
  DataTable dt = new DataTable();  
  dt.Columns.Add("FIELDNAME");  
  SAPParameter p = new SAPParameter("@p_fields");  
  p.Value = dt;  
  ```  
  
## <a name="limitations"></a><span data-ttu-id="c53b0-127">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="c53b0-127">Limitations</span></span>  
 <span data-ttu-id="c53b0-128">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] tiene las siguientes limitaciones para los tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="c53b0-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] has the following limitations for complex types.</span></span>  
  
- <span data-ttu-id="c53b0-129">Cuando se pasa un tipo complejo en un parámetro mediante un **DataTable**, debe incluir todos los campos (columnas) del tipo complejo en el **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c53b0-129">When you pass a complex type in a parameter by using a **DataTable**, you must include all fields (columns) of the complex type in the **DataTable**.</span></span>  
  
- <span data-ttu-id="c53b0-130">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] no admite **DbNull**.</span><span class="sxs-lookup"><span data-stu-id="c53b0-130">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] does not support **DbNull**.</span></span> <span data-ttu-id="c53b0-131">No puede establecer **DbNull** como un valor para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="c53b0-131">You cannot set **DbNull** as a value for parameters.</span></span>  
  
