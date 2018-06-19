---
title: Ejemplos de la instrucción EXEC en mySAP adaptador en BizTalk | Documentos de Microsoft
description: Ejemplos EXEC y ejemplos de uso del adaptador de mySAP en el módulo de adaptador de BizTalk (BAP)
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
ms.openlocfilehash: 6eaae930d7d94d24bac9d484957ccf02718af60f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22216372"
---
# <a name="examples-for-exec-statement"></a>Ejemplos de la instrucción EXEC
Este tema muestra la sintaxis de ejemplo para diversas instrucciones EXEC.

## <a name="sample-statements"></a>Instrucciones de ejemplo 
  
-   Para ejecutar una BAPI que no toma ningún parámetro de entrada, utilice la sintaxis siguiente; se devuelven datos a través de un **DataReader** objeto:  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST  
    ```  
  
-   Para ejecutar una solicitud de cambio que toma parámetros de entrada, utilice la sintaxis siguiente:  
  
    ```  
    EXEC RFC_CUSTOMER_GET @NAME1='Contoso'  
    ```  
  
-   Para ejecutar una solicitud de cambio que toma parámetros de entrada especificados como una variable, use la sintaxis siguiente:  
  
    ```  
    EXEC RFC_CUSTOMER_GET @var=@var  
    ```  
  
     En este ejemplo, debe crear un parámetro denominado `@var` y establecer el valor de forma explícita (por ejemplo, para 1001), porque el primer parámetro para RFC_CUSTOMER_GET corresponde a KUNNR (número de cliente)  
  
-   Para ejecutar una solicitud de cambio que usa una variable para el nombre de parámetro de entrada, utilice la sintaxis siguiente:  
  
    ```  
    EXEC RFC_CUSTOMER_GET @KUNNR=@var1, @NAME1='Contoso'  
    ```  
  
     Debe crear un parámetro denominado `@var1`, especifique el valor y, a continuación, enlazarlo con el objeto de comando correspondiente. La dirección predeterminada del objeto parameter recién creado es `input`.  
  
-   Para ejecutar una BAPI y tablas devueltos como un parámetro, use la sintaxis siguiente:  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST @COMPANYCODE_LIST=@var1 OUTPUT  
    ```  
  
     Debe crear un parámetro denominado `@var1`, especifique el valor y enlácelo al objeto de comando correspondiente. Debe ser la dirección del objeto parameter recién creado `InputOutput` o `Output`.  
  
-   En el siguiente ejemplo EXEC utiliza un parámetro de tipo complejo de tabla. En el ejemplo, @fields es un parámetro de la tabla.  
  
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
  
-   En el siguiente ejemplo EXEC usa un tipo complejo de STRUCT. En el ejemplo, @equimaster es un parámetro STRUCT.  
  
    ```  
    exec BAPI_EQMT_MODIFY @equipment='000000000000000637', @equimaster='<EQUIMASTER>           
                <EQUIPMENT xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">equip</EQUIPMENT>  
                <EQUICATGRY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">E</EQUICATGRY>  
                <MATERIAL xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">mat</MATERIAL>  
              </EQUIMASTER >', @equimaster=@em output  
    ```  
  
## <a name="support-for-complex-parameter-types"></a>Compatibilidad con tipos de parámetros complejos  
 Hay dos maneras para admitir parámetros complejos de RFC (tablas y estructuras) cuando se usa el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:  
  
-   Proporcione un valor XML en línea para el tipo complejo. Este ejemplo muestra cómo pasar XML al tipo de parámetro complejos *campos*. En el ejemplo siguiente, *@fields* es un parámetro de la tabla.  
  
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
  
-   Crear un **DataTable** parámetro con columnas para los campos en el tipo complejo y establezca el parámetro SAP valor en **DataTable**. Este ejemplo muestra cómo establecer el @fields tipo complejo mediante el uso de un **DataTable**.  
  
    ```  
    cmd.CommandText = "exec rfc_read_table @query_table='BNKA', @fields = @p_fields";  
    DataTable dt = new DataTable();  
    dt.Columns.Add("FIELDNAME");  
    SAPParameter p = new SAPParameter("@p_fields");  
    p.Value = dt;  
    ```  
  
## <a name="limitations"></a>Limitaciones  
 El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] tiene las siguientes limitaciones para los tipos complejos.  
  
-   Cuando se pasa un tipo complejo en un parámetro mediante un **DataTable**, debe incluir todos los campos (columnas) del tipo complejo en el **DataTable**.  
  
-   El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] no admite **DbNull**. No se puede establecer **DbNull** como un valor para los parámetros.  
  
