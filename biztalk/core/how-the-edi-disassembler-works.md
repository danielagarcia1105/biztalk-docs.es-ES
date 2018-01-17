---
title: "Cómo funciona el Desensamblador EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8da91ba4-e1c9-4e6b-bbd1-fe71ea880118
caps.latest.revision: "43"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4edf1353a9f06103205e1e6e4296c2aa77e74dc6
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-the-edi-disassembler-works"></a>Cómo funciona el desensamblador EDI
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realiza la mayoría del procesamiento para los intercambios codificados en EDI recibidos en la canalización de recepción EDI (`Microsoft.BizTalk.DefaultPipelines.EDIReceivePipeline`). La canalización incluye el componente de canalización del componente de canalización de desensamblador EDI que realiza el siguiente procesamiento:  
  
-   Divide varios intercambios de un único mensaje en intercambios independientes (si la propiedad de canalización "DetectMID" de la ubicación de recepción está definida como True). El desensamblador EDI lo consigue buscando un encabezado de control de intercambio (ISA, UNA o UNB) incluso después de que se haya encontrado un finalizador de control de intercambio (IEA o UNZ) has been encountered.  
  
-   Valida el sobre.  
  
-   Desensambla el intercambio.  
  
-   Campos de desencadenador de procesos para intercambios HIPAA.  
  
-   Valida EDI y las propiedades específicas del socio comercial, según corresponda. Esto incluye la validación de esquemas EDI, validación de campos cruzados para mensajes con codificación X12 (si está configurado), validación estructural de EDI y validación de esquemas extendida (si el esquema se ha personalizado con un nodo que no sea de tipo EDI). Para obtener más información, consulte [validación de mensajes de EDI recibidos](../core/validation-of-received-edi-messages.md).  
  
-   Comprueba que los números de control de conjunto de intercambio, grupo y transacción no están duplicados, si están habilitadas las comprobaciones en la **validación** página (en **la configuración de intercambio**) de la bidireccional pestaña del acuerdo el **propiedades del acuerdo de** cuadro de diálogo. Comprueba el número de control del intercambio con los intercambios recibidos anteriormente. Comprueba el número de control de grupo con los otros números de control de grupo del intercambio. Comprueba el númeroo de control del conjunto de transacciones con los otros números de control del conjunto de transacciones de ese grupo. Si se detecta un duplicado, el informe de estado indicará que existe un registro duplicado.  
  
-   Genera un documento XML para cada conjunto de transacciones. En cada archivo XML, promociona la propiedad de contexto de BTS.MessageType y la define en el nombre de esquema con espacio de nombres.  
  
-   Convierte todo el intercambio a XML si la **opción de procesamiento por lotes de entrada** propiedad se establece en uno de los dos **conservar intercambio** valores. Esta propiedad se establece en el **configuración de Host Local** página en **configuración de intercambio** de la pestaña del acuerdo bidireccional del **propiedades del acuerdo de** cuadro de diálogo. La canalización de recepción promociona la propiedad ReuseEnvelope para identificar el intercambio como conservado.  
  
-   Genera una confirmación funcional y/o técnica (si está configurada). Ésta puede incluir el procesamiento por lotes de las confirmaciones (si está configurado). Promociona la propiedad de contexto de BTS. MessageType, si se establece igual que el esquema de control en el http://schemas.microsoft.com/EDI/\<X12 o EDIFACT\> espacio de nombres (por ejemplo, X12_997_Root para una confirmación 997). También promociona la propiedad de contexto EDI.DestinationPartyName, que garantiza que la confirmación se seleccionará para su envío. Para obtener más información, consulte [envía una confirmación EDI](../core/sending-an-edi-acknowledgment.md).  
  
-   Realiza la división de documentos HIPAA 276/277 (solo la versión 5010) 834, 835 (solo la versión 4010) y 837, si se aplica.  
  
-   Promociona o escribe propiedades en el contexto del mensaje (vea la siguiente sección).  
  
## <a name="promoting-or-writing-properties-to-the-context"></a>Promocionar o escribir propiedades en el contexto:  
 Cuando el Desensamblador EDI procesa un mensaje recibido, promociona o escribe las siguientes propiedades en el contexto del mensaje:  
  
-   Para un mensaje sin procesar por lotes con codificación X12, promociona las siguientes propiedades desde el sobre: ISA06, ISA08, ISA15; GS01, GS02, GS03, GS08; ST03 y ST01.  
  
    > [!NOTE]
    >  Para un intercambio HIPAA 837 entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite tres esquemas 837 de HIPAA: notificación-Dental_837D, notificación-Institutional_837I y Professional_837P de notificación. El valor ST01 de cada uno de ellos es "837". Estos tres esquemas tienen valores diferentes para GS08 en la versión 5010: "005010X223A1" para 837I, "005010X224A1" para 837d y "005010 X 222" para 837p. Los esquemas tienen valores diferentes para GS08 en la versión 4010: "004010X096A1" para 837I, "004010X097A1" para 837d y "004010X098A1" para 837p.  
  
-   Para un mensaje sin procesar por lotes con codificación EDIFACT, promociona las siguientes propiedades desde el sobre: UNB2.1, UNB2.3, UNB3.1, UNB11; UNG1, UNG2.1, UNG3.1; UNH2.1, UNH2.2, UNH2.3.  
  
-   Si se divide un intercambio procesado por lotes, escribe ISA_Segment y GS_Segment en el contexto de los mensajes con codificación X12, o bien escribe UNA_Segment, UNB_Segment y UNG_Segment en el contexto de los mensajes con codificación EDIFACT.  
  
    > [!NOTE]
    >  Los segmentos anteriores se escriben en el contexto. No se promocionan en el contexto. No obstante, puede anexar estos segmentos a un conjunto de transacciones mediante el ejemplo Message Enrichment. También puede tomar el código que anexa los ejemplos y agregarlo a un componente de canalización personalizado. Para obtener más información, consulte [ejemplo de enriquecimiento de mensajes (ejemplo de BizTalk Server)](../core/message-enrichment-sample-biztalk-server-sample.md).  
  
    > [!NOTE]
    >  La propiedad promocionada ISA_Segment contiene información de autorización o seguridad (ISA02, Información de autorización, e ISA04, Información de seguridad) que puede dar lugar a la divulgación de información. Puede usar el **propiedad información de autorización y seguridad de contraseña de la propiedad de contexto de máscara** (en **configuración de Host Local** página **configuración de intercambio** para propiedades de acuerdo bidireccional) que se va a sustituir cada carácter en los campos ISA02 e ISA04 con un carácter '#'. Se trata de un proceso unidireccional: los caracteres '#' no se puede convertir en caracteres reales.  
  
-   Para los mensajes con codificación X12 y EDIFACT, promociona ReuseEnvelope, que indica si un intercambio por lotes se divide o se conserva.  
  
-   Si un intercambio por lotes se conserva, promociona las siguientes propiedades:  
  
    -   InboundTransportatLocation  
  
    -   InboundTransportType  
  
    -   ISA05  
  
    -   ISA07  
  
    -   ISA06  
  
    -   ISA08  
  
    -   ISA15  
  
    -   LastInterchangeMessage = {True &#124; False}  
  
    -   MessageType  
  
    -   ReceivePortID  
  
    -   ReceivePortName  
  
    -   ReuseEnvelope  
  
## <a name="parsing-the-envelope"></a>Analizar el sobre  
 La canalización de recepción EDI utiliza el esquema de control de encabezado para analizar el sobre de un mensaje EDI recibido y el esquema de documento EDI para analizar los mensajes o conjuntos de transacciones del intercambio.  
  
 Si se recibe un mensaje con codificación EDIINT o AS2 a través del transporte HTTP o HTTPS, el desensamblador EDI inspeccionará la propiedad de contexto BTS.MessageDestination. Si esa propiedad se define como SuspendQueue, lo que indica que se ha producido un error en el procesamiento de AS2 y que el mensaje se va a suspender, el desensamblador EDI actuará como un componente de canalización de paso a través y suspenderá el mensaje en el cuadro de mensajes.  
  
 Durante el análisis de intercambios EDIFACT, la canalización de recepción EDI elimina el indicador de versión utilizado para los caracteres de escape. El indicador de versión no está incluido en la validación EDI. La canalización de recepción EDI no incluye el indicador de versión cuando computa restricciones de longitud.  
  
 **Juego de caracteres**  
  
 Para los intercambios X12, las propiedades del Componente de canalización determinan el juego de caracteres que el desensamblador EDI utilizará para procesar el intercambio. Puede ser Básico, Ampliado o UTF8/Unicode. El valor predeterminado es UTF8. Para intercambios EDIFACT, el campo UNB1.1 determina el juego de caracteres.  
  
 **Detección de separadores dinámicos**  
  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un intercambio EDI, ninguna propiedad de acuerdo indica cuáles deben ser los separadores del intercambio. En su lugar, el desensamblador EDI detecta cuáles son los delimitadores (para X12 o EDIFACT) en tiempo de ejecución.  
  
 Para los mensajes X12, el desensamblador EDI utiliza los siguientes caracteres desde el intercambio:  
  
|Separador|Carácter|  
|---------------|---------------|  
|Separador de elementos de datos|4.º carácter de ISA|  
|Separador de elementos de componente|ISA16|  
|Separador de segmentos|106.º carácter de ISA|  
|Sufijo terminador de segmento|Carácter entre el segmento ISA y el segmento GS<br /><br /> **Valores:** ninguno, CR, LF o CRLF **Nota:** el separador puede tomar solo los valores anteriores.|  
|Separador de repeticiones o identificador estándar.<br /><br /> (dependiendo de la propiedad de acuerdo "Uso de ISA11" en la **sobres** página de la ficha de acuerdo bidireccional)|ISA11|  
  
 Para los intercambios EDIFACT, el desensamblador EDI comprueba el segmento UNA que define los separadores del intercambio. Si el intercambio no dispone de un segmento UNA, que es opcional, el desensamblador utilizará los valores predeterminados definidos en las propiedades del componente de canalización.  
  
|Separador|Carácter de UNA|  
|---------------|----------------------|  
|Separador de elementos de componente|4.º|  
|Separador de elementos de datos|5.º|  
|Notación decimal|6.º|  
|Carácter de versión|7.º|  
|Carácter de repetición|8.º|  
|Separador de segmentos|9.º|  
|Sufijo separador de segmento|Carácter entre los segmentos UNA y UNB<br /><br /> **Valores:** ninguno, CR, LF o CRLF **Nota:** el separador puede tomar solo los valores anteriores.|  
  
 La cadena UNA es opcional. Si está presente, define todos los delimitadores del archivo. Si no lo está, el desensamblador EDI utilizará la propiedad del componente de canalización EfactDelimiters para determinar los delimitadores. Para obtener más información, consulte [configurar propiedades de canalización de EDI](../core/configuring-edi-pipeline-properties.md).  
  
 **Errores de registro**  
  
 Si el desensamblador EDI detecta un error de procesamiento EDI, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía los dos errores siguientes del Visor de eventos (si está habilitado ese envío):  
  
-   Un error registrado por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de origen a la vez que suspende el mensaje. Es un error necesario relativo al procesamiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Un error que notifica problemas en el conjunto de transacciones, según lo registrado por el EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de origen. Se trata de un error específico de EDI.  
  
## <a name="using-agreement-properties"></a>Uso de las propiedades de acuerdo  
 El Desensamblador EDI utilizará propiedades del acuerdo si puede identificar el acuerdo (consulte [resolución de acuerdos, detección de esquemas y autorización para los mensajes de EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)). Si no se puede encontrar un acuerdo coincidente y los valores correspondientes no están disponibles en el acuerdo de reserva, establecen las propiedades del desensamblador de EDI en el **propiedades** se usará la ventana de Visual Studio. Sin embargo, esta reserva no tendrá lugar si se requiere autenticación en las propiedades de puerto de recepción (si el valor **eliminar mensajes si hay errores de autenticación** o **conservar mensajes si hay errores de autenticación** están seleccionadas ). En este caso debe configurarse un acuerdo; si no, el intercambio se suspenderá.  
  
 Cuando el desensamblador EDI usa propiedades de acuerdo, necesita que se definan las siguientes propiedades de entidad:  
  
|Propiedad|Página de propiedades de acuerdo|  
|--------------|-------------------------------|  
|Separador de repeticiones|**Los sobres** página (en **configuración de intercambio**) en la ficha de acuerdo bidireccional|  
|Realizar la validación de tipo de datos EDI|**Validación** página en **establecer la configuración de transacción** en la ficha de acuerdo bidireccional (para acuerdos de X12 y EDIFACT)|  
|Validación ampliada|**Validación** página en **establecer la configuración de transacción** en la ficha de acuerdo bidireccional (para acuerdos de X12 y EDIFACT)|  
|Permitir espacios y ceros iniciales y finales|**Validación** página en **establecer la configuración de transacción** en la ficha de acuerdo bidireccional (para acuerdos de X12 y EDIFACT)|  
|Crear etiquetas XML vacías si se permiten separadores iniciales|**Configuración de Host local** página en **establecer la configuración de transacción** en la ficha de acuerdo bidireccional (para acuerdos de X12 y EDIFACT)|  
|Opción de procesamiento por lotes entrantes|**Configuración de Host local** página (en **configuración de intercambio**) en la ficha de acuerdo bidireccional (para acuerdos de X12 y EDIFACT)|  
|Separadores de EDIFACT predeterminados|-|  
|Enmascarar información de seguridad, de autorización y de contraseña|**Configuración de Host local** página (en **configuración de intercambio**) en la ficha de acuerdo bidireccional (para acuerdos de X12 y EDIFACT)|  
|Convertir formato decimal implícito Nn a valor numérico de base 10|**Configuración de Host local** página en **establecer la configuración de transacción** en la ficha de acuerdo bidireccional (para X12 acuerdos)|  
|Enrutar confirmaciones para enviar canalización en un puerto de recepción de solicitud-respuesta.|**Configuración de Host local** página (**configuración del receptor** sección) en **configuración de intercambio** en la ficha de acuerdo bidireccional (para acuerdos de X12 y EDIFACT)|  
|Juego de caracteres de X12|X12 generación de sobres de intercambio **Nota:** esta opción solo se usa para validar los valores especificados para las propiedades del acuerdo. El juego de caracteres X12 utilizado para el procesamiento en tiempo de ejecución se selecciona en las propiedades de canalización. Para obtener más información, consulte [juegos de caracteres de EDI](../core/edi-character-sets.md).|  
  
## <a name="using-hipaa-trigger-fields"></a>Uso de campos de desencadenador HIPAA  
 Los segmentos EDI contienen con frecuencia valores de calificador que modifican el significado del segmento. Por ejemplo, el segmento N1 puede contener un elemento calificador “BT” para indicar “bill-to name” o puede contener un elemento calificador “ST” para indicar “ship-to name”. Normalmente, se deja a la lógica de negocios para determinar cómo interpretar estos campos y el Desensamblador resuelve todas las instancias del segmento N1 en el mismo nombre de registro XML; Sin embargo, los esquemas HIPAA incluidos con BizTalk Server contienen anotaciones que permiten el Desensamblador EDI cree registros XML únicos basados en la presencia de un valor calificador (consulte [anotaciones de campo desencadenador HIPAA esquema](../core/hipaa-schema-trigger-field-annotations.md)).  
  
 Cuando recibe un conjunto de transacciones HIPAA, si el desensamblador EDI detecta un segmento que contiene un campo desencadenador, usa la información del desencadenador para generar un registro XML específico para la combinación de segmento y desencadenador.  
  
 La tabla siguiente muestra cómo un segmento N1 se traducirá en un registro XML basado en el valor de N101:  
  
|Segmento N1|Datos XML resultantes|  
|----------------|------------------------|  
|N1*PR\*Contoso\*XV\*0000000~|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|N1*PE\*Fabrikam\*FI\*9999999~|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
## <a name="see-also"></a>Vea también  
 [Cómo recibe BizTalk Server los mensajes EDI](../core/how-biztalk-server-receives-edi-messages.md)