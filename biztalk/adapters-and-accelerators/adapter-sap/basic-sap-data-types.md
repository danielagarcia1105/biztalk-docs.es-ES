---
title: "Tipos de datos básicos de SAP en el adaptador de mySAP en BizTalk | Documentos de Microsoft"
description: "Tipos de datos admitidos de ABAP y base de datos para el adaptador de mySAP en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 296b4813-f175-4a02-8fd3-227ae301bc3d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f40e7dc6f98e1de2ff0388a8e7e52fdabafc7681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="basic-sap-data-types"></a>Tipos de datos SAP básica
Los tipos de parámetros que el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite se rige por el:  
  
-   Tipos de datos ABAP que admite SAP  
  
-   Tipos de datos de la base de datos que admite SAP  
  
 Esta sección presenta una asignación entre los tipos de datos ABAP y base de datos y sus correspondientes tipos de esquema XML y. NET.  
  
> [!NOTE]
>  La información de esta sección se aplica a las solicitudes de cambio, tRFCs y BAPI. Tipos de datos SAP siempre se representan como cadenas (XSD: String) en IDOC. Esto es compatible con el analizador de archivos sin formato de BizTalk Server.  
  
## <a name="supported-abap-data-types"></a>Tipos de datos ABAP admitidos  
 El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es compatible con tipos seguros para algunos tipos de datos ABAP. Cuando escriba seguro está habilitado, estos tipos de datos se representan como cadenas. Configurar escribiendo seguro estableciendo la **EnableSafeTyping** propiedad de enlace. Escriba seguro está deshabilitado de forma predeterminada. Para obtener más información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] propiedades de enlace, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
 En la tabla siguiente se muestra cómo aparecen los tipos de datos ABAP cuando escriba seguro no está habilitada. (**EnableSafeTyping** es false). Tipos de datos que se exponen de forma diferente al escribir seguro está habilitado se marcan con un asterisco (*).  
  
|Tipo de datos ABAP|Tipo RFC|Tipo XSD|Tipo de .NET|Cadena de formato|  
|--------------------|--------------|--------------|---------------|-------------------|  
|I (entero)|RFC_INT|xsd:int|Int32|-|  
|Interno (RFC_INT1)|RFC_INT1|xsd:unsignedByte|Byte|-|  
|Interno (RFC_INT2)|RFC_INT2|xsd:short|Int16|-|  
|F (Float)|RFC_FLOAT|xsd:double|Doble|-|  
|P (número de BCD)|RFC_BCD|xsd: decimal si longitud < = 28<br />xsd: String si longitud > 28|Decimal<br />String|Número decimal. 0 posiciones decimales.<br />Número decimal. con > 0 decimales|  
|C (carácter)|RFC_CHAR|xsd:cadena|String|-|  
|D. (fecha: AAAAMMDD) *|RFC_DATE|xsd:dateTime|DateTime|Internamente, el adaptador deserializa el valor en un **DateTime** objeto. A continuación, se invoca el **DateTime.ToUniversalTime** método para convertir el valor de este objeto en una hora UTC. Por último, el componente de fecha (**DateTime.Date**) se utiliza para crear el valor que se envía al sistema SAP. El sistema SAP trata este valor de fecha como hora local.<br /><br /> Debe especificar valores de fecha como UTC para evitar la conversión.<br /><br /> -Para XSD: DateTime, se recomienda el patrón siguiente: "(\d\d\d\d-\d\d-\d\d)T(00:00:00) (.\*) Z".<br />-Para **DateTime** objetos conjunto **DateTime.Kind** a **DateTimeKind.Utc**.|  
|T (hora: HHMMSS) *|RFC_TIME|xsd:dateTime|DateTime|Internamente, el adaptador deserializa el valor en un **DateTime** objeto. A continuación, se invoca el **DateTime.ToUniversalTime** método para convertir el valor de este objeto en una hora UTC. Por último, el componente de tiempo (**DateTime.Time**) se utiliza para crear el valor que se envía al sistema SAP. El sistema SAP trata este valor de tiempo como hora local.<br /><br /> Debe especificar los valores de tiempo como hora UTC para evitar la conversión.<br /><br /> -Para XSD: DateTime, se recomienda el patrón siguiente: "(0001-01-01)T(\d\d:\d\d:\d\d) (.\*)".<br />-Para **DateTime** objetos conjunto **DateTime.Kind** a **DateTimeKind.Utc**.<br /><br /> Por ejemplo, si la hora local es 9:15 a.m., expresarlo como "(001-01-01) T (09: 15:00) Z"|  
|N (cadena numérica) *|RFC_NUM|xsd: int si lenrth < = 9<br />xsd: Long si longitud > 9 y < = 19<br />xsd: String si longitud > 19|Int32<br />long<br />String|-|  
|X (bytes)|RFC_BYTE|xsd:base64Binary|Byte[]|-|  
|CADENA|RFC_STRING|xsd:cadena|String|-|  
|XSTRING|RFC_BYTE|xsd:base64Binary|Byte[]|-|  
  
 * Indica que el tipo de datos aparece en forma diferente cuando escriba segura está habilitada.  
  
### <a name="safe-typing-enabled"></a>Escriba seguro habilitado  
 La siguiente tabla muestra los tipos de datos ABAP que se exponen de forma diferente al escribir seguro está habilitado (el **EnableSafeTyping** enlaza la propiedad es true).  
  
|Tipo de datos ABAP|Tipo RFC|Tipo XSD|Tipo de .NET|Cadena de formato|  
|--------------------|--------------|--------------|---------------|-------------------|  
|D. (fecha: AAAAMMDD)|RFC_DATE|xsd:cadena|String|Formato de fecha SAP: AAAAMMDD.<br /><br /> Se permiten caracteres para los dígitos de fecha, por lo que el valor es básicamente una cadena de ocho caracteres|  
|T (hora: HHMMSS)|RFC_TIME|xsd:cadena|String|Formato de hora SAP: HHMMSS.<br /><br /> Se permiten caracteres para los dígitos de tiempo, por lo que el valor es básicamente una cadena de seis caracteres|  
|N (cadena numérica)|RFC_NUM|xsd:cadena|String|Una cadena de caracteres n; donde n = longitud del campo numc.|  
  
 Tipos de datos ABAP que no están en esta tabla se exponen en la misma forma que al escribir seguro no está habilitado.  
  
### <a name="support-for-date-and-time-fields"></a>Compatibilidad para campos de hora y fecha  
 Cuando escriba seguro no está habilitada, los tipos de fecha ABAP (D) y el tiempo (T) aparecen como XSD: DateTime; Sin embargo, la faceta de patrón aparecen para los tipos de fecha y hora es diferente.  
  
-   La faceta de patrón de fecha es:`(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)`  
  
     Por ejemplo, 7 de julio de 2007 (2007-07-07) se representa como:  
  
     `(2007-07-07)T(00:00:00)`.  
  
-   La faceta de patrón de hora es:`(0001-01-01)T(\d\d:\d\d:\d\d)(.*)`  
  
     Por ejemplo, 18:30:30 (6:30 p.m. y 30 segundos) se representa como:  
  
     `(0001-01-01)T(18:30:30)`.  
  
#### <a name="how-does-the-adapter-represent-minimum-and-maximum-time-values-on-inbound-messages-from-sap"></a>¿Cómo el adaptador representan valores mínimo y máximo tiempo en los mensajes entrantes (desde SAP)?  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza las siguientes directrices cuando recibe los valores de tiempo desde el sistema SAP:  
  
-   El adaptador trata 000000 (hhmmss) y 240000 (hhmmss) como 0 horas, 0 minutos y 0 segundos.  
  
## <a name="supported-database-data-types"></a>Tipos de datos de la base de datos compatibles  
 La manera en que el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] tipos de datos de base de datos de superficies también depende de si escribe seguro está habilitado. En la tabla siguiente se muestra cómo las superficies de adaptador base de datos de tipos de datos al escribir seguro no está habilitada (la **EnableSafeTyping** enlaza la propiedad es false). Tipos de datos que se exponen de forma diferente al escribir seguro está habilitado se marcan con un asterisco (*).  
  
|Tipo de datos de la base de datos|Tipo RFC|XSD|Tipo .NET|  
|------------------------|--------------|---------|---------------|  
|ACCP (período de contabilización) *|RFC_NUM|xsd:int|Int32|  
|CHAR|RFC_CHAR|xsd:cadena|String|  
|CLNT (cliente)|RFC_CHAR|xsd:cadena|String|  
|DIV (campo de moneda)|RFC_BCD|xsd: decimal **Nota:** el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] redondea los valores decimales en función de la definición del parámetro DECIMAL. Por ejemplo, si un parámetro DECIMAL puede aceptar hasta cinco dígitos después del separador decimal, se redondea un valor como 4,000028 a 4.00003.|Decimal|  
|CUKY (clave de moneda)|RFC_CHAR|xsd:cadena|String|  
|DAT (campo de fecha) *|RFC_DATE|xsd:dateTime<br /><br /> Internamente, el adaptador deserializa el valor en un **DateTime** objeto. A continuación, se invoca el **DateTime.ToUniversalTime** método para convertir el valor de este objeto en una hora UTC. Por último, el componente de fecha (**DateTime.Date**) se utiliza para crear el valor que se envía al sistema SAP. El sistema SAP trata este valor de fecha como hora local.<br /><br /> Debe especificar valores de fecha como UTC para evitar la conversión. Se recomienda el patrón siguiente: "(\d\d\d\d-\d\d-\d\d) T (00: 00:00)(.*) Z".|DateTime<br /><br /> Debe especificar valores de fecha como hora UTC (DateTime.Kind = DateTimeKind.Utc) para evitar la conversión.|  
|DEC (cantidad)|RFC_BCD|xsd: decimal **Nota:** el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] redondea los valores decimales en función de la definición del parámetro DECIMAL. Por ejemplo, si un parámetro DECIMAL puede aceptar hasta cinco dígitos después del separador decimal, se redondea un valor como 4,000028 a 4.00003.|Decimal|  
|FLTP (punto flotante)|RFC_FLOAT|xsd:double|Doble|  
|INT1|RFC_INT1|xsd:unsignedByte|Byte|  
|INT2|RFC_INT2|xsd:short|Int16|  
|INT4|RFC_INT|xsd:int|Int32|  
|LANG (clave de lenguaje)|RFC_CHAR|xsd:cadena|String|  
|LCHR|RFC_STRING|xsd:cadena|String|  
|LRAW (seq bytes largo)|RFC_BYTE|xsd: base64Binary|Byte[]|  
|NUMC *|RFC_NUM|xsd:int<br />xsd:long<br />xsd:cadena|Int32 si longitud < = 9<br />Int64 si longitud > 9 y < = 19<br />La cadena si longitud > 19|  
|PREC (precisión)|RFC_INT2|xsd:short|Int16|  
|QUAN (Quantity)|RFC_BCD|xsd: decimal **Nota:** el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] redondea los valores decimales en función de la definición del parámetro DECIMAL. Por ejemplo, si un parámetro DECIMAL puede aceptar hasta cinco dígitos después del separador decimal, se redondea un valor como 4,000028 a 4.00003.|Decimal|  
|RAW (secuencia de bytes)|RFC_BYTE|xsd: base64Binary|Byte[]|  
|RAWSTRING (longitud variable)|RFC_BYTE|xsd: base64Binary|Byte[]|  
|STRING (longitud variable)|RFC_STRING|xsd:cadena|String|  
|TIM (campo de hora) *|RFC_TIME|xsd:datetime<br /><br /> Internamente, el adaptador deserializa el valor en un **DateTime** objeto. A continuación, se invoca el **DateTime.ToUniversalTime** método para convertir el valor de este objeto en una hora UTC. Por último, el componente de tiempo (**DateTime.Time**) se utiliza para crear el valor que se envía al sistema SAP. El sistema SAP trata este valor de tiempo como hora local.<br /><br /> Debe especificar los valores de tiempo como hora UTC para evitar la conversión. Se recomienda el patrón siguiente: "(0001-01-01) T (\d\d:\d\d:\d\d)(.*) Z".<br /><br /> Por ejemplo, si la hora local es 9:15 a.m., expresarlo como "(001-01-01) T (09: 15:00) Z"|DateTime<br /><br /> Debe especificar los valores de tiempo como hora UTC (DateTime.Kind = DateTimeKind.Utc) para evitar la conversión.|  
|UNIDAD (unidad para Qty)|RFC_CHAR|xsd:cadena|String|  
|[No compatible]|--|--|String|  
  
 * Indica que el adaptador presenta el tipo de datos diferente cuando escriba segura está habilitada.  
  
### <a name="safe-typing-enabled"></a>Escriba seguro habilitado  
 La siguiente tabla muestra los tipos de datos que se exponen de forma diferente al escribir segura está habilitada de la base de datos (el **EnableSafeTyping** enlaza la propiedad es true).  
  
|Tipo de datos de la base de datos|Tipo RFC|XSD|Tipo de .NET|Formato de valor de cadena|  
|------------------------|--------------|---------|---------------|-------------------------|  
|ACCP (período de registro)|RFC_NUM|xsd:cadena|String|Cadena de caracteres|  
|NUMC|RFC_NUM|xsd:cadena|String|Cadena de caracteres|  
|DAT (campo de fecha)|RFC_DATE|xsd:cadena|String|YYYYMMDD|  
|TIM (campo de hora)|RFC_TIME|xsd:cadena|String|HHMMSS|  
  
 Tipos de datos que no están en esta tabla se exponen en la misma forma que al escribir seguro no está habilitado.  
  
## <a name="supported-xsd-facets"></a>Facetas XSD compatibles  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con los siguientes aspectos de XSD.  
  
|Tipo RFC|Faceta de XSD (**EnableSafeTyping** = false)|Faceta de XSD (**EnableSafeTyping** = true)|  
|--------------|-------------------------------------------------|------------------------------------------------|  
|RFC_BCD|**Faceta de patrón XSD**<br /><br /> **Cero decimales:**`"([\\-]{0,1})(([0-9]{1,"`  `+ digitsBeforeDecimal +`  `"}))"`<br /><br /> **Uno o más posiciones decimales:**`"([\\-]{0,1})(([0-9]{0,"` + `digitsBeforeDecimal +``"}\\.[0-9]{0,"``+ digitsAfterDecimal +``"})&#124;([0-9]{1,"``+ digitsBeforeDecimal +``"}))"`|Mismo|  
|RFC_NUM|**Faceta XSD totalDigits** si longitud < = 19<br /><br /> **Faceta de patrón XSD** si longitud > 19|**Faceta XSD maxLength (depende de la longitud del valor en SAP)**|  
|RFC_DATE|**Faceta de patrón XSD**<br /><br /> `"(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)"`<br /><br /> Patrón contiene la hora 00:00:00 para que sea compatible con`xsd:datetime`|**Faceta XSD maxLength = 8**|  
|RFC_TIME|**Faceta de patrón XSD**<br /><br /> `"(0001-01-01)T(\d\d:\d\d:\d\d)(.*)"`<br /><br /> Patrón contiene la fecha de 0001-01-01 para ser compatible con`xsd:datetime`|**Faceta XSD maxLength = 6**|  
|RFC_CHAR|**Faceta XSD maxLength**|Mismo|  
  
## <a name="unsupported-data-types"></a>Tipos de datos no compatibles  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no admite el tipo de datos siguientes:  
  
-   Tipos de tabla (jerárquicos) ITAB II  
  
