---
title: Tipos de datos básicos de Oracle en el adaptador de Oracle EBS en BizTalk | Documentos de Microsoft
description: Datos XSD tipos, escriba prueba de errores y la validación en Oracle e-Business Suite en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 008bf621-8b4e-450d-b354-ee26b91592f2
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9012e2ef6adaf94f55b87bbccfc24b7fb889fbf3
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="basic-oracle-data-types"></a>Tipos de datos de Oracle básica
Este tema se describe cómo la [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone los tipos de datos básicos de Oracle.  
  
## <a name="supported-oracle-data-types"></a>Tipos de datos de Oracle admitidos  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con tipos seguros para algunos tipos de datos de Oracle. Cuando escriba seguro está habilitado, estos tipos de datos se representan como cadenas. Configurar escribiendo seguro habilitando la **EnableSafeTyping** enlaza la propiedad (deshabilitada de forma predeterminada). Para obtener más información sobre la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] propiedades de enlace, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
> [!NOTE]
>  Escriba seguro no se admite si son tipos de datos dentro de tipos definidos por el usuario (UDT).  
  
 En la tabla siguiente se muestra cómo aparecen los tipos de datos de Oracle con escribir seguro deshabilitado (**EnableSafeTyping** es **false**). Tipos de datos de Oracle que se ven afectados por la **EnableSafeTyping** propiedad de enlace se marcan con un asterisco (*).  
  
|Tipo de datos de Oracle|Tipo XSD|Tipo de .NET|Comentarios|  
|----------------------|--------------|---------------|--------------|  
|BFile|entrada: xsd: String<br /><br /> salida: xsd: base64Binary|String<br /><br /> Byte[]|No se admite el tipo de datos BFile dentro de los tipos complejos (por ejemplo, el tipo de registro, TableType, UDT y VArray).|  
|BLOB|xsd:base64Binary|Byte[]|-|  
|Char|xsd:cadena|String|-|  
|CLOB|xsd:cadena|String|-|  
|Fecha *<br /><br /> (No escriba seguro si dentro de un UDT)|xsd:dateTime|DateTime|Los valores de fecha no pueden contener información de zona horaria (hora UTC o UTC offsets):<br /><br /> -no deben contener valores de XSD: DateTime UTC o UTC desplazamientos<br />-   **DateTime.Kind** debe ser **DateTimeKind.Unspecified**<br /><br /> Si se especifica la información de zona horaria, el adaptador lanza una **XmlReaderParsingException** excepción con un mensaje que indica el campo. **Nota:** la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone el tipo de datos Date de Oracle como XSD: DateTime en lugar de XSD: Date porque: <ul><li>Tipo de datos Date de Oracle también puede contener el valor de hora.</li><li>No hay ningún .NET equivalente para XSD: Date.</li></ul>|  
|Float **|float si prec < = 7<br /><br /> xsd: Double si prec > 7 y < = 15<br /><br /> xsd: String si prec > 15|Float<br /><br /> Doble<br /><br /> String|Debe especificar el valor coherente con el formato especificado para el carácter decimal y el separador de grupo en el **NumericCharacters** enlaza la propiedad en el **MlsSettings** propiedad de enlace. Si se especifica ningún valor para el **NumericCharacters** propiedad de enlace, el adaptador utiliza la configuración de MLS para el cliente ODP.NET en el mismo equipo donde está instalado el adaptador.|  
|IntervalDS|xsd:cadena<br /><br /> xsd:Duration si dentro de un UDT|String<br /><br /> Intervalo de tiempo si dentro de un UDT|El adaptador devuelve los datos IntervalDS como una cadena con el método OracleIntervalDS.ToString.<br /><br /> El valor debe expresarse en formato nativo de Oracle: HH:MI:SSxFF de día (por ejemplo, "5 15:30:12.99").|  
|IntervalYM|xsd:cadena<br /><br /> xsd: Long si dentro de un UDT|String<br /><br /> Si están largo dentro de un UDT|El adaptador devuelve los datos IntervalYM como una cadena con el método OracleIntervalYM.ToString.<br /><br /> El valor debe expresarse en formato nativo de Oracle: mes del año; Por ejemplo, "1-2" (1 y 2 meses del año).|  
|Long|xsd:cadena|String|A partir de la versión 9i de base de datos de Oracle, el tipo de datos LONG está en desuso. Oracle recomienda utilizar los tipos de datos de objetos grandes (LOB) en su lugar. Por lo tanto, al realizar operaciones en el Oracle base de datos utilizando el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], se recomienda usar los artefactos de base de datos de Oracle que funcionan en tipos de datos LOB y no los datos grandes de tipo.|  
|LongRaw|xsd:base64Binary|Byte[]|-|  
|NChar|xsd:cadena|String|-|  
|NClob|xsd:cadena|String||  
|Número **|xsd: decimal si prec < = 28<br /><br /> xsd: String si prec > 28|Decimal<br />String|-|  
|NVarchar2|xsd:cadena|String|-|  
|Sin formato|xsd:base64Binary|Byte[]||  
|RowID|xsd:cadena|String|-|  
|TimeStamp*<br /><br /> (No escriba seguro si dentro de un UDT)|xsd: DateTime si prec < = 7<br /><br /> xsd: String si prec > 7|DateTime<br /><br /> String|Cuando se expone como cadena (prec > 7), el valor debe expresarse en NLS_TIMESTAMP_FORMAT de Oracle. Puede especificar el formato de cadena para tipos de datos de marca de tiempo en el **TimeStampFormat** enlaza la propiedad en el **MlsSettings** propiedad de enlace. Si se especifica ningún valor para el **TimeStampFormat** propiedad de enlace, el adaptador utiliza la configuración de MLS para el cliente ODP.NET en el mismo equipo donde está instalado el adaptador.<br /><br /> Valores de marca de tiempo no pueden contener información de zona horaria (hora UTC o UTC offsets):<br /><br /> -no deben contener valores de XSD: DateTime UTC o UTC desplazamientos<br />-   **DateTime.Kind** debe ser **DateTimeKind.Unspecified**<br /><br /> Si se especifica la información de zona horaria, el adaptador lanza una **XmlReaderParsingException** excepción con un mensaje que indica el campo.|  
|TimeStampLTZ|xsd:cadena|String|No se admite TimeStampLTZ dentro de los UDT.<br /><br /> **Fuera de un UDT**: el valor se debe expresar en NLS_TIMESTAMP_TZ_FORMAT de Oracle. Puede especificar el formato de cadena para tipos de datos de TimeStampLTZ en el **TimeStampTZFormat** enlaza la propiedad en el **MlsSettings** propiedad de enlace. Si se especifica ningún valor para el **TimeStampTZFormat** propiedad de enlace, el adaptador utiliza la configuración de MLS para el cliente ODP.NET en el mismo equipo donde está instalado el adaptador.|  
|TimeStampTZ|xsd:cadena<br /><br /> xsd: DateTime si dentro de un UDT|String<br /><br /> Fecha y hora si dentro de un UDT|**Fuera de un UDT**: el valor se debe expresar en NLS_TIMESTAMP_TZ_FORMAT de Oracle. Puede especificar el formato de cadena para tipos de datos de TimeStampTZ en el **TimeStampTZFormat** enlaza la propiedad en el **MlsSettings** propiedad de enlace. Si se especifica ningún valor para el **TimeStampTZFormat** propiedad de enlace, el adaptador utiliza la configuración de MLS para el cliente ODP.NET en el mismo equipo donde está instalado el adaptador.|  
|Decimal**|xsd: decimal si prec < = 28<br /><br /> xsd: String si prec > 28|Decimal<br /><br /> String|-|  
|Varchar2|xsd:cadena|String|-|  
|Binario Float **|float si prec < = 7<br /><br /> xsd: String si prec > 7|Float<br /><br /> String|Debe especificar el valor coherente con el formato especificado para el carácter decimal y el separador de grupo en el **NumericCharacters** enlaza la propiedad en el **MlsSettings** propiedad de enlace. Si se especifica ningún valor para el **NumericCharacters** propiedad de enlace, el adaptador utiliza la configuración de MLS para el cliente ODP.NET en el mismo equipo donde está instalado el adaptador.|  
|Binario doble **|xsd: Double si prec < = 15<br /><br /> xsd: String si prec > 15|Doble<br /><br /> String|-|  
|Entero binario **|xsd:integer|Int32||  
|Boolean|xsd:boolean|Valor booleano que acepta valores null||  
|XMLTYPE|xsd:cadena|String|Se admite para parámetros de procedimiento de nivel superior.<br /><br /> Los caracteres XML como reservados '**\<**','**\>**' debe sustituirse por su representación de entidad **(&lt;, &gt;)**al desarrollar aplicaciones de BizTalk y al modelo del canal con WCF. Esto no es necesario en el caso del modelo de servicio de WCF.|  
  
 \*La manera en que se producen estos tipos de datos de Oracle se ve afectada por la **EnableSafeTyping** propiedad de enlace.  
  
 \*\*La manera en que estos aparecen los tipos de datos numéricos dentro de los conjuntos de datos y débilmente tipada cursores REF cursor de Oracle se ve afectado por la **EnableSafeTyping** propiedad de enlace.  
  
> [!IMPORTANT]
>  -   La longitud máxima del valor de un tipo de datos de Oracle en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] está limitado por la longitud máxima del valor compatible con ODP.NET para el tipo de datos de Oracle.  
> -   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] internamente trata los tipos de datos numéricos de Oracle dentro de los UDT como Decimal. NET. Sin embargo, en general (es decir, fuera UDT), el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] internamente trata los tipos de datos numéricos de Oracle como OracleDecimal.  
  
## <a name="safe-typing-enabled"></a>Escriba seguro habilitado  
 En la tabla siguiente se muestra cómo se cambian los tipos de datos de Oracle que se ven afectados escribiendo seguro cuando la **EnableSafeTyping** propiedad de enlace es **true**.  
  
> [!NOTE]
>  Tipos de datos de Oracle que no están en esta tabla aparecen en la misma forma si escribe segura está habilitada o deshabilitada.  
  
|Tipo de datos de Oracle|Tipo XSD|Tipo de .NET|Comentario|  
|----------------------|--------------|---------------|-------------|  
|Date|xsd:cadena|String|El valor debe expresarse en NLS_DATE_FORMAT de Oracle. Puede especificar el formato para los tipos de datos de fecha en la **DateFormat** enlaza la propiedad en el **MlsSettings** propiedad de enlace. Si se especifica ningún valor para el **DateFormat** propiedad de enlace, el adaptador utiliza la configuración de MLS para el cliente ODP.NET en el mismo equipo donde está instalado el adaptador.|  
|TimeStamp|xsd:cadena|String|El valor debe expresarse en NLS_TIMESTAMP_FORMAT de Oracle. Puede especificar el formato de cadena para tipos de datos de marca de tiempo en el **TimeStampFormat** enlaza la propiedad en el **MlsSettings** propiedad de enlace. Si se especifica ningún valor para el **TimeStampFormat** propiedad de enlace, el adaptador utiliza la configuración de MLS para el cliente ODP.NET en el mismo equipo donde está instalado el adaptador.|  
  
> [!IMPORTANT]
>  Si escribe seguro está habilitado, los tipos de datos numéricos de Oracle dentro de los conjuntos de datos y débilmente tipada cursores REF cursor siempre se exponen como cadenas.  
  
## <a name="validation"></a>Validación  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no realiza ninguna validación explícita en los valores que especifican los tipos de datos de Oracle. Sin embargo, dependiendo del tipo de datos de Oracle y si la escribiendo segura está habilitada o deshabilitada, se puede realizar validación implícita:  
  
-   Al deserializar entre el código XML pasado en un mensaje y los tipos de .NET que son utilizados internamente por el adaptador.  
  
-   Por ODP.NET para algunos tipos de datos.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)