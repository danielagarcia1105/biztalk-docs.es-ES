---
title: "Mensaje de CONTRL de EDIFACT como confirmación funcional | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d3c2be0-0993-4b2d-b6c3-286020117078
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e95e61fa4152cdd7485175240b6481f3d28cfc7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="edifact-contrl-message-as-functional-acknowledgment"></a>Mensaje CONTRL de EDIFACT como confirmación funcional
Si ha seleccionado generar una confirmación funcional en la configuración de perfil de negocio o acuerdo entre socios comerciales (o acuerdo de reserva si no se ha definido ningún acuerdo entre los dos perfiles de negocio), o bien si el campo UNB9 del mensaje se configura en "1", se generará un mensaje CONTRL como confirmación funcional. Esta confirmación informa sobre los resultados de las comprobaciones de sintaxis del intercambio.  
  
 La confirmación funcional CONTRL incluye los siguientes segmentos:  
  
-   Encabezado de mensaje UNH (obligatorio)  
  
-   Un segmento UCI que identifica el intercambio de asuntos e indica la recepción del intercambio de estado y contiene referencias a los segmentos UNA, UNB y UNZA del intercambio recibido (obligatorio). El segmento UCI presenta una repetición máxima de 1. Como resultado, informa sobre el primer error que se detecta en uno de los segmentos de control.  
  
-   Un segmento UCF que identifica un segmento de grupo (encapsulado por el encabezado UNG y el finalizador UNE) e indica la naturaleza de los errores (obligatorio si existe el segmento UNG)  
  
-   Un segmento UCF que identifica un segmento de mensajes (encapsulado por el encabezado UNH y el finalizador UNT) e indica la naturaleza de los errores (obligatorio)  
  
-   Un segmento UCS que identifica un conjunto de transacciones e indica la naturaleza de los errores (obligatorio)  
  
-   Un segmento UCD que identifica un elemento de datos de componentes o compuestos erróneo e indica la naturaleza de los errores (condicional)  
  
-   Finalizador de mensaje UNT (obligatorio).  
  
 Si una confirmación funcional CONTRL recibida sólo contiene segmentos UNH, UCI y UNT, la canalización EDIReceive procesará la confirmación como una confirmación de recepción CONTRL (técnica).  
  
 La instancia de un segmento en un nivel de informe (por ejemplo, los segmentos UCI, UCF, UCM, UCS y UCD) sólo puede informar de un error.  
  
> [!NOTE]
>  El mensaje CONTRL contiene varios elementos de datos obligatorios que se copiarán del intercambio recibido. Si falta el elemento de datos del intercambio o no es válido sintácticamente, no se generará un mensaje CONTRL que sea válido sintácticamente. Como consecuencia, debe informarse del error por otros medios distintos a un mensaje CONTRL.  
  
> [!NOTE]
>  En BizTalk Server, se envía un mensaje CONTRL (confirmación de recepción, aceptación o rechazo) como respuesta a un intercambio recibido que contiene solo uno o más mensajes CONTRL. En [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)], no se envía ningún mensaje CONTRL (confirmación de recepción, aceptación o rechazo) como respuesta al intercambio recibido que solo contiene uno o más mensajes CONTRL. Debe informarse de los errores en mensajes CONTRL recibidos por otros medios distintos a un mensaje CONTRL. Si uno o más mensajes CONTRL se incluyen en un intercambio que contiene mensajes de datos, se generará el mensaje CONTRL generado como respuesta a ese intercambio, como si no hubiera mensajes en el intercambio recibido.  
  
 **Bucles SG**  
  
 La confirmación funcional CONTRL se estructurará de forma diferente dependiendo de si el intercambio recibido incluye uno o más grupos. Si el intercambio incluye un grupo, la confirmación contendrá un segmento UCF por grupo. Cada segmento UCF contendrá un segmento UCM por mensaje y cada uno de estos segmentos incluirá una serie de segmentos UCS y UCD conjuntamente.  
  
 El formulario XML del mensaje de confirmación incluirá un elemento SG3Loop que encapsula cada segmento UCF, un elemento SG4Loop que encapsula cada elemento UCM y un elemento SG5 que encapsula cada par de elementos UCS y UCD. Las etiquetas de bucles SG no están presentes en el formato EDI nativo del mensaje.  
  
 Si el intercambio no incluye un grupo, la confirmación no contendrá ningún segmento UCF. En su lugar, incluirá un segmento UCM por mensaje y cada uno de estos segmentos incluirá una serie de segmentos UCS y UCD conjuntamente.  
  
 El formulario XML del mensaje de confirmación incluirá un elemento SG1Loop que encapsula cada elemento UCM y un elemento SG2Loop que encapsula cada par de elementos UCS y UCD. Igual que ocurre con los intercambios que incluyen grupos, las etiquetas SG no están presentes en el formato nativo de la confirmación.  
  
> [!NOTE]
>  Debido a un uso predeterminado de fábrica, no se espera que haya bucles SG1/SG4 en los conjuntos de transacciones aceptados. Sin embargo, para ser compatible con los estándares, puede forzar la generación de SG1/SG4 seleccionando la **bucles SG1/SG4 generar conjuntos de transacciones aceptadas** casilla de verificación en la **confirmaciones** página de la Cuadro de diálogo de propiedades de acuerdo para un acuerdo entre dos perfiles de negocio (o la **confirmaciones** página de la ficha Configuración de EDI para un perfil de negocio). Si se activa esta casilla, la canalización de recepción generará bucles SG1/SG4, se acepte o no el conjunto de transacciones. Si se encuentra desactivada, estos bucles sólo se generarán para conjuntos de transacciones erróneos (en los que UCM5 != 7).  
  
 **Elementos de datos**  
  
 La confirmación funcional CONTRL incluye los siguientes elementos de datos:  
  
|Elementos Data|Nombre|Uso|  
|------------------|----------|-----------|  
|UNH1|Número de referencia de mensaje|-|  
|UNH2|Subcomponentes del identificador de mensaje|Los subcomponentes son:<br /><br /> -1 = CONTRL<br /><br /> - 2 = 4<br /><br /> - 3 = 1<br /><br /> -4 = QUITAR|  
|UCI1|Número de control de intercambio.|Asignado desde el campo UNB5 del mensaje recibido.|  
|UCI2|Remitente de intercambio|Asignado desde el campo UNB2 del mensaje recibido. El primer subcomponente (identificación) es obligatorio. El segundo subcomponente (calificador de código) y el tercero (dirección de enrutamiento inverso) son opcionales.|  
|UCI3|Destinatario de intercambio|Asignado desde el campo UNB3 del mensaje recibido. El primer subcomponente (identificación) es obligatorio. El segundo subcomponente (calificador de código) es opcional.|  
|UCI4|Código de acción|Los códigos de acción son:<br /><br /> -8 si se acepta el intercambio<br /><br /> -se rechazan 7 si se acepta el intercambio, pero algunos conjuntos de transacciones<br /><br /> -4 si se rechaza el intercambio debido a un error en el segmento UNA o UNB<br /><br /> Es un elemento de datos obligatorio.|  
|UCI5|Código de error de sintaxis|Identifica la condición de error al recibir el intercambio (si lo hay). Para obtener más información, consulte [códigos de Error de confirmación de CONTRL de EDIFACT](../core/edifact-contrl-acknowledgment-error-codes.md).<br /><br /> Este elemento de datos presenta una opcionalidad condicional.|  
|UCI6|Etiqueta de segmento de servicio|Identifica el segmento que presenta la condición de error identificada en el elemento de datos UCI.5.<br /><br /> Este elemento de datos presenta una opcionalidad condicional.|  
|UCI7|Identificación de elementos de datos|Identifica los elementos de datos que presentan la condición de error identificada en el elemento de datos UCI.5. Los subcomponentes de UCI7 son:<br /><br /> -Posición del elemento de datos erróneo en segmento (obligatorio)<br /><br /> -Posición del elemento de datos de componentes erróneo en segmento (opcionalidad condicional)<br /><br /> -Aparición del elemento de datos erróneo en segmento (opcionalidad condicional)|  
|UCI8|-|-|  
|UCF1|Número de referencia de grupo|Asignado desde el campo UNG5 del mensaje recibido.<br /><br /> Es un elemento de datos obligatorio.|  
|UCF2|Identificación del remitente de la aplicación|Asignado desde el campo UNG2 del mensaje recibido junto con subcomponentes.<br /><br /> Es un elemento de datos condicional.|  
|UCF3|Identificación del destinatario de la aplicación|Asignado desde el campo UNG3 del mensaje recibido junto con subcomponentes.<br /><br /> Es un elemento de datos condicional.|  
|UCF4|Acción codificada|Los códigos de acción son:<br /><br /> -7 si se acepta el intercambio<br /><br /> -4 si se rechaza el intercambio debido a un error en el segmento UNA o UNB<br /><br /> El código se aplica a este nivel y a otros niveles inferiores.<br /><br /> Es un elemento de datos obligatorio.|  
|UCF5|Error de sintaxis, codificado|Identifica la condición de error en el grupo (si lo hay). Para obtener más información, consulte [códigos de Error de confirmación de CONTRL de EDIFACT](../core/edifact-contrl-acknowledgment-error-codes.md).<br /><br /> Este elemento de datos presenta una opcionalidad condicional.|  
|UCF6|Etiqueta de segmento de servicio|Identifica el segmento erróneo del grupo.<br /><br /> Este elemento de datos presenta una opcionalidad condicional.|  
|UCF7|Identificación de elementos de datos|Identifica los elementos de datos que presentan la condición de error identificada en el elemento de datos UCF5. Los subcomponentes de UCF7 son:<br /><br /> -Posición del elemento de datos erróneo en segmento (obligatorio)<br /><br /> -Posición del elemento de datos de componentes erróneo en segmento (opcionalidad condicional)<br /><br /> -Aparición del elemento de datos erróneo en segmento (obligatorio)|  
|UCM1|Número de referencia de mensaje|Asignado desde el campo UNH1 del mensaje recibido.<br /><br /> Es un elemento de datos obligatorio.|  
|UCM2|Identificador de mensaje|Asignado desde el campo UNH2 del mensaje recibido junto con subcomponentes.<br /><br /> Es un elemento de datos condicional.|  
|UCM3|Acción codificada|Los códigos de acción son:<br /><br /> -7 si se acepta el intercambio<br /><br /> -4 si se rechaza el intercambio debido a un error en el segmento UNA o UNB<br /><br /> El código se aplica a este nivel y a otros niveles inferiores.<br /><br /> Es un elemento de datos obligatorio.|  
|UCM4|Error de sintaxis, codificado|Identifica la condición de error en el grupo (si lo hay). Para obtener más información, consulte [códigos de Error de confirmación de CONTRL de EDIFACT](../core/edifact-contrl-acknowledgment-error-codes.md).<br /><br /> Este elemento de datos presenta una opcionalidad condicional.|  
|UCM5|Etiqueta de segmento de servicio|Identifica el segmento UNH o UNT con errores.<br /><br /> Este elemento de datos presenta una opcionalidad condicional.|  
|UCM7|Identificación de elementos de datos|Identifica los elementos de datos que presentan la condición de error identificada en el elemento de datos UCM5. Los subcomponentes de UCM7 son:<br /><br /> -Posición del elemento de datos erróneo en segmento (obligatorio)<br /><br /> -Posición del elemento de datos de componentes erróneo en segmento (opcionalidad condicional)<br /><br /> -Aparición del elemento de datos erróneo en segmento (obligatorio)|  
|UCS1|Posición del segmento en el cuerpo del mensaje|Recuento de la posición del segmento erróneo que empieza con UNH como 1. Para informar de que existe un segmento, esta es la posición de recuento numérico del último segmento que se procesó antes de la posición donde se esperaba el segmento que falta como. Se indica que falta un grupo de segmentos mediante la identificación de que falta el primer segmento del grupo.<br /><br /> Es un elemento de datos obligatorio.|  
|UCS2|Error de sintaxis codificado|Identifica la condición de error en el grupo (si lo hay). Para obtener más información, consulte [códigos de Error de confirmación de CONTRL de EDIFACT](../core/edifact-contrl-acknowledgment-error-codes.md).<br /><br /> Este elemento de datos presenta una opcionalidad condicional.|  
|UCD1|Error de sintaxis codificado|Identifica la condición de error en el grupo (si lo hay). Para obtener más información, consulte [códigos de Error de confirmación de CONTRL de EDIFACT](../core/edifact-contrl-acknowledgment-error-codes.md).<br /><br /> Este elemento de datos presenta una opcionalidad condicional.<br /><br /> **Nota:** si se produce un error de validación de XSD, el elemento de datos UCD1 informará de un valor de código de 12, valor no válido.|  
|UCD2|Identificación de elementos de datos|Identifica los elementos de datos que presentan la condición de error identificada en el elemento de datos UCD1. Los subcomponentes de UCD2 son:<br /><br /> -Posición del elemento de datos erróneo en segmento (obligatorio)<br /><br /> -Posición del elemento de datos de componentes erróneo en segmento (opcionalidad condicional)<br /><br /> -Aparición del elemento de datos erróneo en segmento (obligatorio)|  
|UNT1|Número de segmentos|-|  
|UNT2|Número de referencia de mensaje|-|