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
# <a name="syntax-for-an-execquery-statement-in-sap"></a>Sintaxis de una instrucción EXECQUERY en SAP
Puede usar la GUI de SAP para crear consultas seleccionando gráficamente las tablas que desea consultar, las columnas y el orden que desea incluir en el conjunto de resultados, etcetera. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] permite a los usuarios ejecutar estas consultas desde una aplicación de ADO.NET proporcionando una operación de EXECQUERY que los usuarios pueden usar para ejecutar una consulta definida en el sistema SAP.  
  
 El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] usa un Z_EXECUTE_SAP_QUERY RFC personalizadas para ejecutar las consultas predefinidas en el sistema SAP. La RFC personalizada a su vez ejecuta la RSAQ_REMOTE_QUERY_CALL, que es un estándar que RFC definida en el sistema SAP. Por lo tanto, antes de realizar la operación de EXECQUERY, debe instalar la RFC personalizada en el sistema SAP que se va a ejecutar las consultas contra. Para obtener instrucciones sobre cómo instalar la RFC personalizada, consulte [instalar RFC personalizadas para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).  
  
 En este tema se proporciona información sobre la sintaxis de la operación de EXECQUERY y otra información útil relacionada con la operación de EXECQUERY.  
  
## <a name="syntax-for-an-execquery-statement"></a>Sintaxis de una instrucción EXECQUERY  
 La siguiente sección describe las especificaciones de gramática para el uso de la operación de EXECQUERY contra el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 donde:  
  
- **\<QueryName\>**  es el nombre de la consulta definida en el sistema SAP.  
  
- **Grupo de usuarios** hace referencia al grupo de usuarios en el que se define la consulta. Este parámetro es obligatorio.  
  
- **Área de trabajo** hace referencia al área de trabajo en el que se define la consulta. En SAP, hay dos áreas de trabajo, estándar y Global. Proporciona un espacio en blanco para especificar el área de trabajo estándar. Proporcionar `X` para especificar el área de trabajo Global. El valor predeterminado es un espacio vacío.  
  
- **VARIANT** hace referencia a un conjunto de criterios de selección que se pueden especificar al ejecutar una consulta SAP guardadas. Por ejemplo, puede usar las variantes para especificar los valores predeterminados para las consultas.  
  
- <strong>@Pn</strong> hace referencia a la n<sup>th</sup> campo de selección en la definición de consulta SAP.  
  
- **USEORIGINALCOLUMNNAMES** especifica si el proveedor usa los nombres de columna original en el conjunto de datos, tal y como aparecen en el sistema SAP. De forma predeterminada, el proveedor utiliza los nombres descriptivos que se definen en la consulta SAP. Sin embargo, si los nombres descriptivos dentro de la consulta no son únicos, el cliente ADO.NET producirá un error al leer los datos del conjunto de datos. En estos escenarios, debe especificar la opción USEORIGINALCOLUMNNAMES, que indica que el proveedor utiliza los nombres de columna original en el conjunto de datos.  
  
  > [!IMPORTANT]
  >  Siempre debe proporcionar el valor de la palabra clave de opción entre comillas simples, por ejemplo, '*USEORIGINALCOLUMNNAMES*'.  
  
> [!NOTE]
>  Para obtener información acerca de cómo se traducen los parámetros de una consulta de SAP en una sintaxis EXECQUERY, consulte [parámetros de consulta de SAP traducen en comandos de EXECQUERY](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).  
  
### <a name="framing-an-execquery-syntax"></a>Tramas una sintaxis EXECQUERY  
 Tramas de sintaxis para una operación de EXECQUERY ejecutar una consulta SAP depende de cómo se define la consulta en el sistema SAP, incluidos cada valor de parámetro definido en SAP. Para obtener información sobre cómo enmarcar sintaxis EXECQUERY para ejecutar una consulta de SAP, consulte [parámetros de consulta de SAP traducen en comandos de EXECQUERY](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a>Consideraciones mientras Using adicional la operación de EXECQUERY  
 Esta sección enumeran los puntos que debe tener en cuenta al utilizar la instrucción EXECQUERY con [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
- Los valores especificados para el grupo de usuarios, área de trabajo y variante se pasan como-es el estándar RFC de SAP, RSAQ_REMOTE_QUERY_CALL. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no valida los valores especificados para estos parámetros.  
  
- Todos los valores devueltos por la operación de EXECQUERY son del tipo de cadena.  
  
- Palabras clave para los nombres de consulta, grupo de usuarios, área de trabajo y variantes no distinguen mayúsculas de minúsculas. Sin embargo, los nombres de parámetro siempre deben estar en caseP superior como @P1, @P2, etcetera. Por ejemplo:  
  
  ```  
  EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
   es igual que  
  
  ```  
  EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
- Los operadores admitidos por el EXECQUERY son >, <>, =, < =,! =, NOT y BETWEEN.  
  
- No se admiten caracteres comodín por la operación de EXECQUERY. Por ejemplo, la siguiente instrucción proporciona el resultado esperado:  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
  ```  
  
   Sin embargo, en la misma consulta cuando se ejecuta con un carácter comodín se produce un error. Tenga en cuenta el uso de caracteres comodín para <strong>@P2</strong>.  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
  ```  
  
   En este ejemplo, podría obtener un error que indica que se ha encontrado ningún dato. Esto es porque la consulta busca **'\*&\*'** como una cadena y no tiene en cuenta el asterisco (*) como carácter comodín.  
  
- Siempre debe especificar los valores de fecha en formato AAAAMMDD.  
  
- Si va a ejecutar una consulta que tiene una variante definida en el sistema SAP, puede especificar el nombre de la variante como parte del comando. Por ejemplo:  
  
  ```  
  EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
  ```  
  
  > [!NOTE]
  >  No es necesario especificar un nombre de la variante si se define una variante de forma predeterminada para la consulta en el sistema SAP.  
  
## <a name="see-also"></a>Vea también  
 [Uso del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)