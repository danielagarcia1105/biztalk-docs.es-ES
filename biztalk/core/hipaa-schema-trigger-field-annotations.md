---
title: Anotaciones de campo desencadenador HIPAA esquema | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1389284-a2ec-44e7-a2f1-8d26f83fd31d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d3bf6d53ec95ebfc57cff646ce5658fc6b1f4a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="hipaa-schema-trigger-field-annotations"></a>Anotaciones del campo desencadenador del esquema HIPAA
Los segmentos EDI contienen con frecuencia valores de calificador que modifican el significado del segmento. Por ejemplo, el segmento N1 puede contener un elemento calificador “BT” para indicar “bill-to name” o puede contener un elemento calificador “ST” para indicar “ship-to name”. Normalmente, se deja a la lógica de negocio determinar cómo interpretar estos campos y el desensamblador resuelve todas las instancias del segmento N1 en el mismo nombre de registro XML. Sin embargo, los esquemas HIPAA suministrados con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] contienen anotaciones que permiten que el desensamblador EDI cree registros XML únicos según la presencia de un elemento de calificación.  
  
 **Implementación del campo desencadenador**  
  
 Los campos desencadenadores se implementan como un par de atributos XML que describen el elemento de segmento y el valor de desencadenador que causa este registro que se cree. En la tabla siguiente se describen los atributos:  
  
|Attribute|Finalidad|  
|---------------|-------------|  
|trigger_field|El campo de segmento en el que se buscará el valor desencadenador.|  
|trigger_value|Los valores desencadenadores.<br /><br /> Puede contener un único valor o una lista de valores delimitados por espacios.|  
  
 En la tabla siguiente se muestra la anotación de desencadenador tal como aparecería en el esquema HIPAA, el segmento EDI que causará que se active el desencadenador y los datos XML resultantes después del procesamiento del segmento.  
  
|Anotación de desencadenador de esquema|Segmento de N1 coincidente|Datos XML resultantes|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|N1 * PR\*Contoso\*XV\*0000000 ~|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|N1 * PE\*Fabrikam\*FI\*9999999 ~|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 **Procesamiento de desensamblador EDI de campos de desencadenador**  
  
 Cuando se recibe un conjunto de transacciones HIPAA, si el desensamblador EDI encuentra un segmento que contiene un campo desencadenador, usa la información de desencadenador para generar un registro XML específico para la combinación de segmento y desencadenador. Por ejemplo, en los datos EDI siguientes, hay dos segmentos N1 que tienen diferentes valores para N101, PR y PE:  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 Cuando se procesa el Desensamblador EDI, las anotaciones de campo desencadenador presentes en el esquema producirá dos registros XML independientes basados en el valor de N101, < N1_PayerIdentification_TS835W1_1000A > y < N1_PayeeIdentification_TS835W1_1000B >, correspondientes a N1 * PR y N1\*PE.  
  
 Cuando se realiza el envío, el ensamblador EDI eliminará el sufijo después del carácter “_” para los campos que contengan una anotación de desencadenador. Por ejemplo, <N1_PayerIdentification_TS835W1_1000A> y <N1_PayeeIdentification_TS835W1_1000B> se convertirán en N1.  
  
 **Segmentos predeterminados y campos desencadenadores**  
  
 En la tabla siguiente se incluye contiene información sobre los segmentos predeterminados y los campos que se en los documentos HIPAA suministrados como parte de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]:  
  
> [!NOTE]
>  Los valores desencadenadores individuales que se usan con los campos desencadenadores pueden variar entre esquemas.  
  
|Segmento con desencadenador|Campo desencadenador|  
|--------------------------|-------------------|  
|AMT|AMT01|  
|CRC|CRC01|  
|DTM|DTM01|  
|DTP|DTP01|  
|ENT|ENT02|  
|HI|HI01:01|  
|N1|N101|  
|NM1|NM01|  
|NTE|NTE01|  
|REF|REF01|  
|RMR|RMR01|