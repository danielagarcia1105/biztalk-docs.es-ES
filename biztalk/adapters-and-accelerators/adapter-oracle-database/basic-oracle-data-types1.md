---
title: Types1 de datos de Oracle básica | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, supported
- data types, unsupported
ms.assetid: 491230b9-b946-4681-a048-5da46102c370
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86349adae1a3ae061cb07c6c770532cf92c74dc8
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="basic-oracle-data-types"></a>Tipos de datos de Oracle básica
Este tema se describe cómo la [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de datos básicos de Oracle.  
  
## <a name="supported-oracle-data-types"></a>Tipos de datos de Oracle admitidos  
 El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es compatible con tipos seguros para algunos tipos de datos de Oracle. Cuando escriba seguro está habilitado, estos tipos de datos se representan como cadenas. Configurar escribiendo seguro estableciendo la **EnableSafeTyping** propiedad de enlace. Escriba seguro está deshabilitado de forma predeterminada. Para obtener más información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] propiedades de enlace, consulte [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
> [!NOTE]
>  Escriba seguro no se admite si son tipos de datos dentro de tipos definidos por el usuario (UDT).  
  
 En la tabla siguiente se muestra cómo aparecen los tipos de datos de Oracle con escribir seguro deshabilitado (**EnableSafeTyping** es false). Tipos de datos de Oracle que se ven afectados por la **EnableSafeTyping** propiedad de enlace se marcan con un asterisco (*).  
  
|Tipo de datos de Oracle|Tipo XSD|Tipo de .NET|Comentarios|  
|----------------------|--------------|---------------|--------------|  
|BFile|entrada: xsd: String<br />salida: xsd: base64Binary|String<br />Byte[]|No se admite el tipo de datos BFile dentro de los tipos complejos (por ejemplo, el tipo de registro, TableType, UDT y VArray).|  
|BLOB|xsd:base64Binary|Byte[]|Se admite para los procedimientos y las operaciones de tabla.|  
|Char|xsd:cadena|String|Se admite para los procedimientos y las operaciones de tabla.|  
|CLOB|xsd:cadena|String|Se admite para los procedimientos y las operaciones de tabla.|  
|Fecha *<br /><br /> (No escriba seguro si dentro de un UDT)|xsd:dateTime|DateTime|Los valores de fecha no pueden contener información de zona horaria (hora UTC o UTC offsets):<br /><br /> -no deben contener valores de XSD: DateTime UTC o UTC desplazamientos<br />-   **DateTime.Kind** debe ser **DateTimeKind.Unspecified**<br /><br /> Si se especifica la información de zona horaria, el adaptador lanza una **XmlReaderParsingException** excepción con un mensaje que indica el campo.|  
|Float **|float si prec < = 7<br />xsd: Double si prec > 7 y < = 15<br />xsd: String si prec > 15|Float<br />Doble<br />String|-|  
|IntervalYM|xsd:cadena<br /><br /> xsd: Long si dentro de un UDT|String<br /><br /> Si están largo dentro de un UDT|El valor debe expresarse en formato nativo de Oracle: mes del año; Por ejemplo, "1-2" (1 y 2 meses del año).|  
|IntervalDS|xsd:cadena<br /><br /> xsd:Duration si dentro de un UDT|String<br /><br /> Intervalo de tiempo si dentro de un UDT|El valor debe expresarse en formato nativo de Oracle: día HH:MI:SSxFF; Por ejemplo, "5 15:30:12.99"|  
|Long|xsd:cadena|String|Se admite en todas las operaciones de tablas, procedimientos almacenados y funciones. **Nota:** a partir de la versión 9i de base de datos de Oracle, el tipo de datos LONG está en desuso. Oracle recomienda utilizar los tipos de datos LOB en su lugar. Por lo tanto, al realizar operaciones en el Oracle base de datos utilizando el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], se recomienda usar los artefactos de base de datos de Oracle que funcionan en tipos de datos LOB y no los datos grandes de tipo.|  
|LongRaw|xsd:base64Binary|Byte[]|-|  
|NChar|xsd:cadena|String|-|  
|NClob|xsd:cadena|String|Se admite para los procedimientos y las operaciones de tabla.|  
|Número **|xsd: decimal si prec < = 28<br />xsd: String si prec > 28|Decimal<br />String|-|  
|NVarchar2|xsd:cadena|String|-|  
|Sin formato|xsd:base64Binary|Byte[]|Se admite para los procedimientos y las operaciones de tabla.|  
|RowID|xsd:cadena|String|-|  
|TimeStamp*<br /><br /> (No escriba seguro si dentro de un UDT)|xsd: DateTime si prec < = 7<br />xsd: String si prec > 7|DateTime<br />String|Valores de marca de tiempo no pueden contener información de zona horaria (hora UTC o UTC offsets):<br /><br /> -no deben contener valores de XSD: DateTime UTC o UTC desplazamientos<br />-   **DateTime.Kind** debe ser **DateTimeKind.Unspecified**<br /><br /> Si se especifica la información de zona horaria, el adaptador lanza una **XmlReaderParsingException** excepción con un mensaje que indica el campo.|  
|TimeStampLTZ|xsd:cadena|String|No se admite TimeStampLTZ dentro de los UDT.<br /><br /> **Fuera de un UDT**: el valor se debe expresar en NLS_TIMESTAMP_TZ_FORMAT.|  
|TimeStampTZ|xsd:cadena<br /><br /> xsd: DateTime si dentro de un UDT|String<br /><br /> Fecha y hora si dentro de un UDT|**Fuera de un UDT**: el valor se debe expresar en NLS_TIMESTAMP_TZ_FORMAT.|  
|Decimal**|xsd: decimal si prec < = 28<br />xsd: String si prec > 28|Decimal<br />String|-|  
|Varchar2|xsd:cadena|String|-|  
|Binario Float **|float si prec < = 7<br />xsd: String si prec > 7|Float<br />String|Debe especificar el valor en un formato coherente con la configuración regional (**System.Globalization.CultureInfo.CurrentCulture**). Por ejemplo, para la configuración regional en inglés, use un carácter de punto ('. ') para especificar la coma decimal; para la configuración regional en francés, utilice un carácter de coma (',').|  
|Binario doble **|xsd: Double si prec < = 15<br />xsd: String si prec > 15|Doble<br />String|-|  
|Entero binario **|xsd:integer|Int32|Se admite para los procedimientos, funciones y paquetes.|  
|Boolean|xsd:boolean|Valor booleano que acepta valores null||  
|XMLTYPE|xsd:cadena|String|Se admite para parámetros de procedimiento de nivel superior.<br /><br /> Los caracteres XML como reservados '**\<**','**\>**' debe sustituirse por su representación de entidad **(&lt;, &gt;)**al desarrollar aplicaciones de BizTalk y al modelo del canal con WCF. Esto no es necesario en el caso del modelo de servicio de WCF.|  
  
 \*La manera en que se producen estos tipos de datos de Oracle se ve afectada por la **EnableSafeTyping** propiedad de enlace.  
  
 \*\*La manera en que estos aparecen los tipos de datos numéricos dentro de los conjuntos de datos y débilmente tipada cursores REF cursor de Oracle se ve afectado por la **EnableSafeTyping** propiedad de enlace.  
  
> [!IMPORTANT]
>  -   La longitud máxima del valor de un tipo de datos de Oracle en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] está limitado por la longitud máxima del valor compatible con ODP.NET para el tipo de datos de Oracle.  
> -   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] internamente trata los tipos de datos numéricos de Oracle dentro de los UDT como Decimal. NET. Sin embargo, en general (es decir, fuera UDT), el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] internamente trata los tipos de datos numéricos de Oracle como OracleDecimal.  
  
### <a name="safe-typing-enabled"></a>Escriba seguro habilitado  
 En la tabla siguiente se muestra cómo se cambian los tipos de datos de Oracle que se ven afectados escribiendo seguro cuando la **EnableSafeTyping** enlaza la propiedad es true.  
  
|Tipo de datos de Oracle|Tipo XSD|Tipo de .NET|Comentario|  
|----------------------|--------------|---------------|-------------|  
|Date|xsd:cadena|String|El valor debe expresarse en NLS_DATE_FORMAT de Oracle.|  
|TimeStamp|xsd:cadena|String|El valor debe expresarse en NLS_TIMESTAMP_FORMAT de Oracle.|  
  
> [!IMPORTANT]
>  Si escribe seguro está habilitado, los tipos de datos numéricos de Oracle dentro de los conjuntos de datos y débilmente tipada cursores REF cursor siempre se exponen como cadenas.  
  
 Tipos de datos de Oracle que no están en esta tabla aparecen en la misma forma si escribe segura está habilitada o deshabilitada.  
  
### <a name="validation"></a>Validación  
 El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] no realiza ninguna validación explícita en los valores que especifican los tipos de datos de Oracle. Sin embargo, dependiendo del tipo de datos de Oracle y si la escribiendo segura está habilitada o deshabilitada, se puede realizar validación implícita:  
  
-   Al deserializar entre el código XML pasado en un mensaje y los tipos de .NET que son utilizados internamente por el adaptador.  
  
-   Por ODP.NET para algunos tipos de datos.  
  
