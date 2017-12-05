---
title: Problemas conocidos con herramientas XML utilizadas con soluciones EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d9b361-be98-494c-b32d-03892672fef1
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23b8222369503f616f2d994f9292091f8e6c1f0d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-xml-tools-used-with-edi-solutions"></a>Problemas conocidos con herramientas XML utilizadas con soluciones EDI
En este tema se describe problemas conocidos con herramientas XML en BizTalk Server.  
  
## <a name="validation-of-test-map-input-and-output-file-still-occurs-when-the-validate-property-is-set-to-false"></a>La validación del archivo de entrada y de salida de asignación de comprobación se produce cuando se establece la propiedad de validación como False.  
 Si prueba una asignación con la propiedad de entrada de comprobar asignación establecida en **nativo** y establecen las propiedades validar entrada de comprobar asignación y validar salida de comprobar asignación en **False**, todavía se realizará la validación. Esto ocurre porque el archivo de entrada con formato nativo se convertirá a formato XML y BizTalk Server validará el XML con respecto al esquema. Si hay problemas de validación en el archivo de entrada, este mecanismo de validación registrará errores, incluso si se establecen las propiedades validar entrada de comprobar asignación y validar salida de comprobar asignación en **False**.  
  
## <a name="length-validation-is-not-performed-on-a-data-element-in-a-generated-instance-that-is-pulled-from-an-enum-list-in-the-schema"></a>La validación de duración no se realiza en un elemento de datos en una instancia generada que se extrae de una lista de enumeraciones en el esquema.  
 Cuando una instancia se genera a partir de un esquema y los valores de enumeración para un elemento de datos en el esquema no satisfacen el requisito de longitud, la instancia puede generarse con un elemento de datos que provocará un error de validación XSD debido al requisito de longitud. La validación del esquema no comprobará si un valor en la instancia generada que se extrae de la lista de enumeraciones en el esquema satisface el requisito de duración mínimo y máximo.  
  
## <a name="validate-schema-may-not-detect-an-invalid-transaction-set-id-code"></a>Validar esquema puede no detectar un código de Id. de conjunto de transacciones no válidas.  
 Cuando se valida un esquema con el comando Validar esquema en la ventana Explorador de soluciones de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], la comprobación del nodo raíz no puede detectar código de Id. de conjunto de una transacción no válida en la última parte del nodo raíz de referencia (con el formato X12_\< Es\>_TSID). Si el TSID en el nodo raíz de referencia del esquema no es válido pero es el mismo que el TSID en el nodo de enumeración del elemento ST'01 en el esquema, la operación Validar esquema no detectará que el TSID no es válido.  
  
## <a name="visual-studio-must-be-restarted-to-make-an-enum-change-in-a-schema-effective-for-instance-validation"></a>Visual Studio debe reiniciarse para realizar un cambio de enumeración en un esquema efectivo para la validación de instancia.  
 Si cambia una lista de enumeración en un esquema, lo guardo y, a continuación, ejecuta la validación de instancia, BizTalk Server realizará la validación que se basa en la versión anterior del esquema, no en la última versión. BizTalk Server no utilizará la última versión del esquema hasta que reinicie Visual Studio.  
  
## <a name="the-edi-instance-properties-dialog-box-may-be-displayed-when-not-needed-in-the-testmap-operation"></a>El cuadro de diálogo de las propiedades de instancia de EDI debe mostrarse cuando no sea necesario en la operación de comprobación de la asignación.  
 BizTalk Server mostrará un cuadro de diálogo Propiedades de la instancia de EDI dos veces durante el proceso de comprobar asignación: una vez para que pueda especificar los delimitadores necesarios para la interpretación de la instancia de mensaje de entrada y otra para especificar los delimitadores para generar el mensaje de salida instancia. BizTalk Server debe mostrar el cuadro de diálogo de propiedades de instancia de EDI sólo dos veces y únicamente para los esquemas EDI. Sin embargo, BizTalk Server puede mostrar el cuadro de diálogo para esquemas que no sean EDI y más de dos veces. Si es así, cierre el cuadro de diálogo.  
  
## <a name="validation-of-an-xml-preserved-interchange-is-not-supported"></a>La validación de un intercambio conservado XML no es compatible.  
 Al validar un intercambio conservado, si selecciona XML para el **valide el tipo de entrada de instancia** propiedad, se producirá un error en la operación y se devolverá nada. Sin embargo, si selecciona **nativo** para el **valide el tipo de entrada de instancia** al validar un intercambio conservado, la operación se realizará correctamente.  
  
## <a name="an-instance-generated-for-a-hipaa-278-schema-will-contain-both-request-and-response-sections"></a>Una instancia generada para un esquema HIPAA 278 constará de las secciones Solicitud y Respuesta.  
 El esquema HIPAA 278 se utiliza para los mensajes de solicitud 278 y las respuesta 278. Si utiliza el comando Generar instancia en un esquema 278, la instancia generada tendrá las secciones de solicitud y respuesta, que nunca se deben enviar. Para crear un mensaje factible de solicitud 278 o de respuesta 278, abra la instancia que las herramientas XML han generado en un editor de texto y borre una de las secciones, es decir, borre la sección de respuesta para un mensaje de solicitud.  
  
 Si ejecuta el comando Validar instancia en un mensaje 278 con secciones de solicitud y respuesta, el mensaje se validará satisfactoriamente en el esquema 278.  
  
## <a name="an-xml-instance-generated-from-a-278-hipaa-schema-will-fail-validation"></a>Una instancia XML generada a partir de un esquema 278 HIPAA producirá un error en la validación.  
 Si utiliza el comando de generación de instancias para generar una instancia XML en un esquema 278 HIPAA y, a continuación, utiliza el comando de validación de instancias para validar esa instancia, BizTalk Server registrará un error.  
  
## <a name="a-native-instance-generated-from-a-837-schema-incorrectly-sets-gs08"></a>Una instancia nativa que se generó a partir de un esquema 837 establece GS08 de manera incorrecta  
 Al generar una instancia nativa mediante un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución que contiene el X12_BatchSchema, así como un esquema de 837I, 837d o 837p, el valor de GS08 contendrá 00401. Antes de procesar esta instancia, debe cambiar el valor de GS08 en el valor correcto para la instancia del esquema.  En la tabla siguiente se incluye el valor de GS08 correcto para cada esquema 837:  
  
|Esquema HIPAA|Valor de GS08|  
|------------------|----------------|  
|837I|004010X096A1|  
|837D|004010X097A1|  
|837P|004010X098A1|  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos del procesamiento de EDI](../core/known-issues-with-edi-processing.md)   
 [Uso de las extensiones de herramientas XML](../core/using-the-xml-tool-extensions.md)   
 [Uso de herramientas XML en tiempo de diseño](../core/using-design-time-xml-tools.md)