---
title: Problemas conocidos con validación de EDI, esquemas y mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 417c3e18-9a97-4d59-bc2b-e96a8c33d388
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a508834ff81814b17bc12f1d698984d65748092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264564"
---
# <a name="known-issues-with-edi-validation-schemas-and-messages"></a>Problemas conocidos de los mensajes, esquemas y validaciones EDI
En este tema se describen problemas conocidos de la validación.  
  
## <a name="message-is-suspended-with-edi-validation-turned-off"></a>El mensaje se suspende con la validación EDI desactivada.  
 **Síntoma**  
  
 Se ha infringido una regla emparejada y la validación está desactivada, pero el mensaje se suspende (el resultado esperado es que el mensaje se serialice).  
  
 **Causa posible**  
  
 Se realiza la validación de campos cruzados o segmentos, incluso si **tipo EDI** propiedad no esté seleccionada en el **validación y configuración de la generación de confirmación** nodo de la **propiedades de EDI** cuadro de diálogo. La validación se produce porque se activa en la anotación de esquema.  
  
 **Resolución**  
  
 Desactive la validación en la anotación de esquema.  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-a-schema-has-been-edited-and-redeployed"></a>El servicio de BizTalk debe reiniciarse después de que el esquema se haya editado e implementado por segunda vez.  
 **Síntoma**  
  
 BizTalk Server no procesa correctamente un mensaje válido después de que el esquema se haya editado e implementado por segunda vez.  
  
 **Causa posible**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacena en caché esquemas con tiempos de espera ilimitados.  
  
 **Resolución**  
  
 Tras editar y volver a implementar un esquema, reinicie el Servicio de servidor BizTalk Server. También debe reiniciar la instancia de host que aloja la canalización que usa el esquema que se ha vuelto a implementar.  
  
## <a name="processing-has-been-aborted-for-messages-of-a-single-encoding-type-for-a-single-party"></a>Se ha anulado el procesamiento de los mensajes de un tipo de codificación única para una única entidad.  
 **Síntoma**  
  
 Se ha anulado el procesamiento de todos los mensajes de un tipo de codificación única (por ejemplo, X12 o EDIFACT) para una única entidad. El procesamiento de mensajes de otro tipo de codificación para la misma entidad, o de los mensajes de otra entidad, no se ha visto afectado.  
  
 **Causa posible**  
  
 El número de control del conjunto de transacciones, intercambio o grupo ha sobrepasado la longitud máxima permitida.  
  
 Para los mensajes X12, la longitud máxima de un número de control es de nueve dígitos. Para los mensajes EDIFACT, la longitud máxima de un número de control es 14 dígitos en tres campos.  
  
 **Resolución**  
  
 En la página de propiedades correspondiente, restablezca el número de control del cuadro de diálogo Propiedades de EDI para la entidad afectada. Puede editar los números de control en las siguientes páginas de propiedades:  
  
-   Número de control de intercambio X12: página Definición de segmento ISA (en el nodo Entidad como receptor del intercambio) para Propiedades de X12  
  
-   Número de control de conjunto de transacciones o grupo de X12: página Definición de segmentos GS y ST (en el nodo Entidad como receptor del intercambio para Propiedades de X12)  
  
-   Número de control de intercambio EDIFACT: página Definición de segmento UNB (en el nodo Entidad como receptor del intercambio para Propiedades de EDIFACT)  
  
-   Número de control de conjunto de transacciones o grupo de EDIFACT: página Definición de segmentos UNG y UNH (en el nodo Entidad como receptor del intercambio para Propiedades de UNH)  
  
## <a name="biztalk-server-validates-with-schemas-that-have-unh-segments-with-seven-data-elements"></a>BizTalk Server se valida con esquemas que tengan segmentos UNH con siete elementos de datos.  
 En versiones anteriores de EDIFACT, los segmentos UNH tienen cuatro elementos en lugar de los siete (de los que tres son opcionales) que tiene el segmento UNH en versiones posteriores. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa la versión posterior con siete elementos para la validación.  
  
## <a name="error-messages-generated-for-multiple-cross-field-validation-rules-will-not-be-specific-to-the-rule"></a>Los mensajes de error generados para reglas de validación de campos cruzados no serán específicos para la regla.  
 Si un esquema contiene varias reglas de validación de campos cruzados para un elemento de datos en un mensaje y se produce un error con el elemento de datos, se generará un error independiente para cada regla de validación. No obstante, cada uno de esos errores tendrá el mismo código de error y descripción; los errores no serán específicos para la regla de validación.  
  
## <a name="if-edi-type-validation-is-disabled-on-receive-and-enabled-on-send-the-send-pipeline-will-not-be-able-to-serialize-the-message"></a>Si la validación de tipo EDI está deshabilitada en la recepción y está habilitada en el envío, la canalización de envío no podrá serializar el mensaje.  
 Si desactiva la validación de tipo EDI en la recepción, la canalización de recepción EDI generará un mensaje XML desde un mensaje EDI recibido, tanto si el mensaje es válido como si no lo es. Si la validación de tipo EDI está habilitada en el envío, la canalización de envío EDI no podrá volver a procesar el XML en un archivo EDI válido si el archivo XML contiene errores y, como resultado, se producirá un error.  
  
## <a name="edi-promoted-properties-are-only-available-if-your-application-has-a-reference-to-the-biztalk-edi-application"></a>Las propiedades promocionadas de EDI solo están disponibles si su aplicación tiene una referencia a la aplicación EDI de BizTalk.  
 **Síntoma**  
  
 Las propiedades promocionadas bajo el espacio de nombres de EDI no aparecen en la lista de propiedades promocionadas que está intentando usar, por ejemplo, en una orquestación o en las condiciones de filtro para un puerto de envío.  
  
 **Causa posible**  
  
 La aplicación de BizTalk que está usando no tiene una referencia a la aplicación EDI de BizTalk. Los esquemas de propiedades para las propiedades promocionadas de EDI están en Microsoft.BizTalk.Edi.BaseArtifacts.dll, que está incluido en la carpeta Resources de la aplicación EDI de BizTalk.  
  
 **Resolución**  
  
 En la aplicación de BizTalk en la que está trabajando, agregue una referencia a la aplicación EDI de BizTalk.  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>El nombre de elemento de datos de un nombre de propiedad de contexto contiene un carácter de subrayado, no un punto.  
 El nombre de un elemento de datos dentro del segmento EDI contiene un punto, por ejemplo, UNB2.1, que es el campo de identificación para el segmento del remitente UNB2. Sin embargo, cuando el nombre de elemento de datos se incluye como parte de una propiedad de contexto EDI, el punto se sustituye por un carácter de subrayado. Por ejemplo, la propiedad de contexto para el elemento de datos de la identificación de remitente es EDI.UNB2_1, no EDI.UNB2.1. El motivo de esto es que el punto no es compatible en un nombre de propiedad de contexto.  
  
## <a name="irrelevant-string-is-appended-to-instance-validation-error-message"></a>Se anexa una cadena irrelevante al mensaje de error de validación de instancia.  
 Cuando reciba un error durante la validación de instancia, la cadena "BEC 2004" se anexará al mensaje de error. Puede ignorar esta cadena.  
  
## <a name="edifact-schema-names-are-case-sensitive"></a>Los nombres de esquema de EDIFACT distinguen entre mayúsculas y minúsculas.  
 El nombre de un esquema EDIFACT, tal y como se muestra en el elemento de datos root_reference del esquema, distingue entre mayúsculas y minúsculas. Por ejemplo, EFACT_D98B_ORDERS y EFACT_d98B_Orders serían dos esquemas diferentes.  
  
## <a name="invalid-edi-messages-can-be-suspended-even-if-edi-type-validation-is-disabled"></a>Los mensajes EDI no válidos pueden suspenderse incluso si la validación de tipo EDI está deshabilitada.  
 Validación estructural de EDI se lleva a cabo aunque la validación de tipo EDI está deshabilitada. Un intercambio que genera un error en las validaciones estructurales básicas se suspenderá incluso en el caso de que se haya deshabilitado la validación de tipo EDI.  
  
## <a name="the-edi-assembler-will-serialize-an-unbatched-interchange-even-if-a-separator-character-is-used-in-an-envelope-header"></a>El ensamblador EDI serializará un intercambio sin procesar por lotes aunque se use un carácter separador en un encabezado de sobre.  
 Los caracteres separadores usados para separar campos de encabezado y finalizador no se deben usar en la definición de ninguno de los campos de intercambio, grupo, finalizador o encabezado del conjunto de transacciones, cuando se defina como receptor de intercambio para la entidad. Si se utilizan, el intercambio dará lugar a un error en el procesamiento del ensamblador EDI del servidor BizTalk Server de envío o del desensamblador de la entidad receptora. El intercambio no se llevará a cabo correctamente en el ensamblador EDI si existe un lote saliente, ya que el ensamblador validará el sobre con el esquema de control de encabezado (servicio). Si el intercambio no se ha procesado por lotes, el ensamblador EDI lo serializará, pero se producirá un error en el procesamiento del desensamblador en la entidad de recepción.  
  
## <a name="mismatched-character-sets-can-result-in-suspended-interchanges"></a>Los conjuntos de caracteres que no coincidan pueden dar como resultado intercambios suspendidos.  
 El juego de caracteres usado para un intercambio saliente debe ser el mismo que el juego de caracteres usado para crear los conjuntos de transacciones insertados en el intercambio. En caso contrario, el intercambio se puede suspender con un mensaje de error que indique que había caracteres no válidos.  
  
 Por ejemplo, si crea un lote EDIFACT que use un juego de caracteres UNOA, pero un conjunto de transacciones agregado al lote tiene caracteres en minúsculas, la orquestación de procesamiento por lotes suspenderá el mensaje, ya que UNOA no permite caracteres en minúsculas.  
  
 Como otro ejemplo, si configura la canalización de envío EDI para intercambios X12 con el juego de caracteres "Básico", pero un intercambio por lotes X12 tiene caracteres en minúsculas debido a que el juego de caracteres de X12 seleccionado en la página Generación de sobres de intercambio X12 para la entidad como un receptor de intercambio configurado está establecido como "Ampliado" o como "UTF8/Unicode", el mensaje por lotes se suspenderá cuando se aplique la configuración del sobre.  
  
## <a name="using-unh25-for-schema-resolution-requires-an-update-to-the-schema"></a>El uso de UNH2.5 para la resolución de esquemas requiere que se actualice el esquema.  
 Si usa UNH2.5 (el código asignado a la asociación) para la resolución de esquemas de un intercambio EDIFACT entrante, tendrá que actualizar el esquema de documento correspondiente en la carpeta \Archivos de programa\Microsoft BizTalk Server 20xx\Schema. Deberá anexar el valor de UNH2.5 a los valores existentes para xs:element name, root_reference y display_reference. Por ejemplo, si UNH2.5 es "EAN008" y está usando el esquema EFACT_D96A_INVOIC, deberá establecer root_reference, display_reference y xs:element name como "EFACT_D96A_INVOIC_EAN008".  
  
## <a name="the-compressed-file-of-schemas-will-be-replaced-when-an-upgrade-is-performed"></a>El archivo comprimido de esquemas se sustituirá al realizar la actualización.  
 Si se actualiza Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a una compilación posterior, el archivo MicrosoftEdiXSDTemplates.exe de la instalación se sustituirá por el archivo MicrosoftEdiXSDTemplates.exe asociado a la actualización. Si prevé continuar usando los esquemas del archivo comprimido antiguo, ya no tendrá acceso al archivo comprimido después de la actualización a menos que realice una copia de seguridad del archivo comprimido antiguo.  
  
## <a name="if-a-group-contains-multiple-x12-transaction-sets-all-must-be-of-the-same-type"></a>Si un grupo contiene varios conjuntos de transacciones X12, todos deben ser del mismo tipo  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no es compatible con la combinación de diferentes conjuntos de transacciones dentro del mismo grupo. Si un grupo contiene varias transacciones, el valor ST01 debe ser el mismo para todas las transacciones.  
  
## <a name="receiving-x12-interchanges-that-contain-non-ascii-delimiters-may-result-in-the-message-becoming-suspended"></a>Recibir intercambios X12 que contienen delimitadores que no sean ASCII puede hacer que se suspenda el mensaje  
 **Síntoma**  
  
 Al recibir un intercambio X12 que use valores de delimitador que no sean ASCII, el mensaje puede suspenderse y escribirse un error en el registro de eventos de la aplicación.  
  
 **Causa posible**  
  
 Este problema puede producirse si el intercambio no se codifica en UTF-8.  
  
 **Resolución**  
  
 Asegúrese de que los intercambios X12 de entrada que contengan delimitadores que no sean ASCII se codifiquen en UTF-8.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos del procesamiento de EDI](../core/known-issues-with-edi-processing.md)   
 [Mensajería EDI](../core/edi-messaging.md)   
 [Validación del mensaje EDI](../core/edi-message-validation.md)   
 [Esquemas EDI](../core/edi-schemas.md)   
 [Desarrollo de esquemas EDI](../core/developing-edi-schemas.md)