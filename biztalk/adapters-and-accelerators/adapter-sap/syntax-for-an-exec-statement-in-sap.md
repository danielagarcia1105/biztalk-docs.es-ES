---
title: Sintaxis para una instrucción EXEC en SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
ms.assetid: 406b1100-39a0-4321-89c9-ec1b8a3cfdc6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362aa1f81158c9d9f1135c9bff25c64d7d745953
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="syntax-for-an-exec-statement-in-sap"></a>Sintaxis para una instrucción EXEC en SAP
La siguiente sección describe las especificaciones de gramática para implementar instrucciones EXEC en la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]. Tenga en cuenta que, en muchos casos, la sintaxis es un poco diferente de la sintaxis de Transact-SQL.  
  
```  
EXEC rfc_name {<argument_element>} [ , …n ]  {;}[0,1] [ OPTION <disabledatavalidation>, <firstresultset> ]  
```  
  
 donde:  
  
-   **rfc_name** especifica el nombre de la llamada de función para ejecutar.  
  
-   **< argument_element >** :: = @param_name = [0,1] \<const\> {[entrada &#124; SALIDA]} [0,1]  
  
    -   **param_name** especifica el nombre de parámetro definido en la interfaz de la función.  
  
    -   **\<¿Const\>**  :: = entero &#124; real &#124; cadena &#124;? &#124; NULL &#124; xml_element  
  
-   **OPCIÓN** proporciona la opción en cómo desea presentar los datos. Las opciones disponibles son:  
  
    -   **disabledatavalidation** opción establece la **EnableSafeTyping** enlace de propiedad en subyacente [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Cuando escriba seguro está habilitado los tipos de datos de archivos DAT, TIM y NUMC se representan como cadenas. Para obtener más información acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
    -   **firstresultset** especifica el primer conjunto de resultados devuelto por la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]. Cuando se ejecute la instrucción en un origen de proveedor ADO, solo el primer conjunto de resultados devuelto está disponible. Para escenarios de RFC EXEC, normalmente varios parámetros de la tabla se devuelven, pero está disponibles para el programa cliente, que no puede ser útil si solo el primer conjunto de resultados. Al especificar la palabra clave "firstresultset" como parte de la cláusula OPTION, los clientes pueden especificar el primer parámetro de la tabla que desean usar el proveedor para devolver. Por ejemplo:  
  
        ```  
        EXEC Z_TEST_ALL_TYPES @P_IN='TestInput' OPTION 'disabledatavalidation', firstresultset TAB_ALLTYPES'  
        ```  
  
         En este ejemplo, la instrucción EXEC especifica que el primer parámetro de tabla devuelto debería ser TAB_ALLTYPES.  
  
    > [!IMPORTANT]
    >  Siempre debe proporcionar los valores de la palabra clave de opción entre comillas simples, por ejemplo, '*disabledatavalidation*'.  
  
 En la sintaxis anterior, xml_element puede utilizarse para proporcionar la entrada para los tipos complejos. La estructura del elemento xml será diferente para las estructuras y tablas. El xml_element de estructura es similar al siguiente:  
  
```  
<PARAM_NAME>  
    <FIELDNAME_1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_1>  
    <FIELDNAME_2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_2>  
    ...  
    ...  
</ PARAM_NAME>  
```  
  
 El xml_element de tabla es similar al siguiente:  
  
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
</ PARAM_NAME>  
```  
  
 Por ejemplo, el elemento XML de un tipo de estructura es similar al siguiente:  
  
```  
<INOUT_STRUCT>  
       <ACCPFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006</ACCPFIELD>  
       <CHARFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">John</CHARFIELD>                 
</INOUT_STRUCT>  
```  
  
 De forma similar, el elemento XML de un tipo de tabla es similar al siguiente:  
  
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
  
 Por ejemplo, vea [ejemplos de la instrucción EXEC](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).  
  
## <a name="handling-named-parameters"></a>Control de parámetros con nombre  
 Éstas son directrices para especificar parámetros con nombre en las consultas EXEC:  
  
-   Debe especificar los parámetros por nombre (por ejemplo, @param_name= value).  
  
    > [!NOTE]
    >  No se admiten parámetros sin nombre  
  
-   Cuando se define un parámetro con un valor predeterminado, puede ejecutar el procedimiento sin especificar un parámetro.  
  
-   Las consultas EXEC no admiten el uso de parámetros con las siguientes propiedades:  
  
    -   Estructuras anidadas (estructuras que contienen estructuras como sus campos).  
  
    -   Tablas anidadas.  
  
    -   Una tabla que contiene una estructura.  
  
    -   Una estructura que contiene una tabla.  
  
    -   Una estructura o una tabla que tiene campos con tipos de cadena compuesta, por ejemplo `SSTRING` o `RAWSTRING`.  
  
     En la tabla siguiente se enumera las asignaciones lógicas entre los tipos de parámetro RFC y direcciones de parámetro al ejecutar una solicitud de cambio.  
  
    |Tipo de parámetro RFC|Palabra clave de consulta|Dirección del parámetro|  
    |--------------------|-------------------|-------------------------|  
    |Importación de parámetros|Nada|Paramdirection.Input|  
    |Parámetros de exportación|Salida|Paramdirection.Output|  
    |Parámetros de la tabla|Salida/Nothing|InputOutput|  
  
 Los siguientes son directrices generales para controlar parámetros:  
  
-   Puede especificar valores de parámetros como constantes o mediante el uso de marcadores de posición en la consulta.  
  
-   Cuando se usa marcadores de posición en la consulta, debe crear un `SAPParameter` y agregarlo al objeto de comando correspondiente. A continuación, pasar el nombre de marcador de posición para el constructor; la dirección y el valor dependen del contexto.  
  
    -   Para `Input` parámetros, no se especifica en la consulta una palabra clave para la dirección del parámetro. El `value` debe establecerse el campo del objeto de parámetro o el proveedor iniciará una excepción. No debe establecer explícitamente la `direction` campo del objeto de parámetro, porque el proveedor predeterminado es `Input`.  
  
    -   Otros parámetros, utilice el formato `@paramname=@placeholder` y especifique el `Output` palabra clave explícitamente en la consulta. A continuación, debe agregar una `SAPParameter` que se corresponde con el marcador de posición y se establece explícitamente la dirección del parámetro como `ParamDirection.Output` o `ParamDirection.InputOutput`, según el tipo de parámetro.  
  
-   Nombres de parámetro y los nombres de marcador de posición no distinguen mayúsculas de minúsculas.  
  
-   No se puede repetir los nombres de parámetro en una consulta a menos que tengan direcciones diferentes.  
  
-   No se puede repetir los nombres de marcador de posición en una consulta.  
  
## <a name="considerations-when-calling-an-exec-statement"></a>Consideraciones al llamar a una instrucción EXEC  
 Esta sección enumeran los puntos que debe tener en cuenta al utilizar la instrucción EXEC con [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
-   Para una instrucción EXEC, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] devuelve `TIMS` valores de campo como .NET `System.DateTime` objetos.  
  
    > [!NOTE]
    >  Para una instrucción SELECT, la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] devuelve `TIMS` valores de campo como .NET `System.TimeSpan` objetos. Para obtener más información acerca de la instrucción SELECT, vea [sintaxis para una instrucción SELECT en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).  
  
## <a name="see-also"></a>Vea también  
 [Acerca del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)