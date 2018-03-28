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
# <a name="syntax-for-an-execquery-statement-in-sap"></a>Sintaxis de una instrucción EXECQUERY en SAP
Puede usar la GUI de SAP para crear consultas seleccionando las tablas que desea consultar, las columnas y el orden que desea incluir en el conjunto de resultados, etcetera gráficamente. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] permite a los usuarios ejecutar estas consultas desde una aplicación de ADO.NET proporcionando una operación EXECQUERY que los usuarios pueden utilizar para ejecutar una consulta definida en el sistema SAP.  
  
 El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] utiliza un Z_EXECUTE_SAP_QUERY RFC personalizada para ejecutar las consultas predefinidas en el sistema SAP. La solicitud de cambio personalizada a su vez ejecuta RSAQ_REMOTE_QUERY_CALL, que es un estándar que RFC definida en el sistema SAP. Por lo tanto, antes de realizar la operación de EXECQUERY, debe instalar la solicitud de cambio personalizada en el sistema SAP que se va a ejecutar las consultas contra. Para obtener instrucciones sobre cómo instalar la solicitud de cambio personalizada, consulte [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).  
  
 En este tema se proporciona información sobre la sintaxis de la operación de EXECQUERY y otra información útil relacionada con la operación de EXECQUERY.  
  
## <a name="syntax-for-an-execquery-statement"></a>Sintaxis de una instrucción EXECQUERY  
 En la siguiente sección se describe las especificaciones de gramática para el uso de la operación de EXECQUERY el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 donde:  
  
-   **\<Nombredeconsulta\>**  es el nombre de la consulta definida en el sistema SAP.  
  
-   **USERGROUP** hace referencia al grupo de usuarios en el que esté definida la consulta. Este parámetro es obligatorio.  
  
-   **Área de trabajo** hace referencia al área de trabajo en el que esté definida la consulta. En SAP, hay dos áreas de trabajo: estándar y Global. Proporciona un espacio en blanco para especificar el área de trabajo estándar. Proporcionar `X` para especificar el área de trabajo Global. Valor predeterminado es el espacio vacío.  
  
-   **VARIANT** hace referencia a un conjunto de criterios de selección que puede especificar al ejecutar una consulta SAP almacenado. Por ejemplo, puede usar variantes para especificar valores predeterminados para las consultas.  
  
-   **@Pn** hace referencia al n<sup>th</sup> campo de selección en la definición de consulta SAP.  
  
-   **USEORIGINALCOLUMNNAMES** especifica si el proveedor utiliza los nombres de columna originales del conjunto de datos, tal como aparecen en el sistema SAP. De forma predeterminada, el proveedor utiliza los nombres descriptivos que se definen en la consulta SAP. Sin embargo, si los nombres descriptivos dentro de la consulta no son únicos, el cliente ADO.NET producirá un error al leer los datos del conjunto de datos. En estos escenarios, debe especificar la opción USEORIGINALCOLUMNNAMES, que indica que el proveedor utiliza los nombres de columna originales del conjunto de datos.  
  
    > [!IMPORTANT]
    >  Siempre debe proporcionar el valor de la palabra clave de opción entre comillas simples, por ejemplo, '*USEORIGINALCOLUMNNAMES*'.  
  
> [!NOTE]
>  Para obtener información acerca de cómo se traducen los parámetros de una consulta de SAP en una sintaxis EXECQUERY, consulte [parámetros de consulta de SAP traducir en el comando EXECQUERY](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).  
  
### <a name="framing-an-execquery-syntax"></a>Tramas una sintaxis EXECQUERY  
 Tramas de sintaxis para una operación de EXECQUERY ejecutar una consulta SAP depende de cómo esté definida la consulta en el sistema SAP, incluidos cada valor de parámetro definido en SAP. Para obtener información sobre cómo enmarcar sintaxis EXECQUERY para ejecutar una consulta SAP, consulte [parámetros de consulta de SAP traducir en el comando EXECQUERY](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a>Consideraciones mientras Using adicional la operación EXECQUERY  
 Esta sección enumeran los puntos que debe tener en cuenta al utilizar la instrucción EXECQUERY con [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
-   Los valores especificados para USERGROUP, el área de trabajo y la variante se pasan en como-es el estándar RFC de SAP, RSAQ_REMOTE_QUERY_CALL. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no valida los valores especificados para estos parámetros.  
  
-   Todos los valores devueltos por la operación de EXECQUERY son del tipo de cadena.  
  
-   Palabras clave para nombres de consulta, el grupo de usuarios, el área de trabajo y variantes no distinguen entre mayúsculas y minúsculas. Sin embargo, los nombres de parámetro siempre deben estar en caseP superior como @P1, @P2, etcetera. Por ejemplo:  
  
    ```  
    EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
     es igual que  
  
    ```  
    EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
-   Los operadores admitidos por el EXECQUERY son >, <>, =, < =,! =, no es así y BETWEEN.  
  
-   No se admiten caracteres comodín en la operación de EXECQUERY. Por ejemplo, la instrucción siguiente da el resultado esperado:  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
     Sin embargo, la misma consulta cuando se ejecuta con un carácter comodín produce un error. Observe el uso de caracteres comodín para **@P2**.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
    ```  
  
     En este ejemplo, podría obtener un error que indica que se ha encontrado ningún dato. Esto es porque la consulta busca **'\*&\*'** como una cadena y no tiene en cuenta el asterisco (*) como carácter comodín.  
  
-   Siempre debe especificar los valores de fecha en formato AAAAMMDD.  
  
-   Si va a ejecutar una consulta que tiene una variante definida en el sistema SAP, puede especificar el nombre de la variante como parte del comando. Por ejemplo:  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
    ```  
  
    > [!NOTE]
    >  No es necesario especificar un nombre variant si se define una variante de forma predeterminada para la consulta en el sistema SAP.  
  
## <a name="see-also"></a>Vea también  
 [Uso del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)