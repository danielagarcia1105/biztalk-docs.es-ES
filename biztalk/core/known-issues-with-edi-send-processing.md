---
title: Conoce problemas con EDI del procesamiento de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1325dcd9-5dbb-48bb-b5a3-1502d1424d4e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbebfa213aa125252a8c58e246df376e2a36527d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263316"
---
# <a name="known-issues-with-edi-send-processing"></a>Problemas conocidos del procesamiento de envío de EDI
En este tema se describen los problemas conocidos del procesamiento en la canalización de envío EDI.  
  
## <a name="x12-implied-decimal-point-causes-length-validation-to-fail"></a>El separador decimal implícito X12 provoca que se produzca un error en la validación de la longitud.  
 **Síntoma**  
  
 Cuando la canalización de envío EDI convierte un valor numérico de base 10 en el XML intermedio en un número en el formato Nn en el intercambio EDI saliente, el intercambio XML producirá un error en la validación de la longitud.  
  
 **Causa posible**  
  
 Cuando se serializa un intercambio EDI con codificación X12, las canalizaciones de envío EDI siempre convertirá un valor número de base 10 en un número en el formato Nn con un separador decimal implícito. Por ejemplo, si hay un valor en el archivo XML intermedio de 12.34, la canalización de envío EDI lo convertirá en el intercambio EDI a 1234 cuando se especifica como tipo numérico N2. La duración del valor numérico de base 10 será superior en uno a la longitud del número en el formato Nn. Si la longitud del número en el formato Nn es el máximo, el valor numérico de base 10 en el XML intermedio puede producir un error en la validación de la longitud del XML.  
  
 Este es solo un problema de los intercambios con codificación X12.  
  
 **Resolución**  
  
 Agregue el valor de 1 al valor de longitud máxima del número XML.  
  
## <a name="control-numbers-may-need-to-be-reset-archived-or-purged"></a>Puede ser necesario restablecer, archivar o purgar los números de control.  
 Si un número de control alcanza el límite de restricción de longitud para el campo, BizTalk Server generará un error y suspenderá el intercambio. Tendrá que restablecer el número de control especificado en el cuadro de diálogo de Propiedades de EDI o Propiedades globales de EDI.  
  
 Los números de control se guardan en la tabla dbo.EdiSequenceNumbers de la Base de datos de cuadro de mensajes de BizTalk. Debe administrar esta tabla de base de datos mediante la purga de los números de control de la tabla o el archivado de éstos, según corresponda.  
  
 También puede habilitar el restablecimiento automático de números de control seleccionando **restablecer al límite inferior cuando se encuentra fuera del límite** en el cuadro de diálogo de propiedades de EDI.  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>El nombre de elemento de datos de un nombre de propiedad de contexto contiene un carácter de subrayado, no un punto.  
 El nombre de un elemento de datos dentro del segmento EDI contiene un punto, por ejemplo, UNB2.1, que es el campo de identificación para el segmento del remitente UNB2. Sin embargo, cuando el nombre de elemento de datos se incluye como parte de una propiedad de contexto EDI (por ejemplo, en la expresión de filtro de un puerto de envío), el punto se sustituye por un carácter de subrayado. Por ejemplo, la propiedad de contexto para el elemento de datos de la identificación de remitente es EDI.UNB2_1, no EDI.UNB2.1. El motivo de esto es que el punto no es compatible en un nombre de propiedad de contexto.  
  
## <a name="context-property-values-from-data-elements-must-not-contain-leading-or-trailing-spaces-in-filter-expressions"></a>Los valores de propiedad de contexto de los elementos de datos no deben contener espacios iniciales o finales en las expresiones de filtro.  
 Si un elemento de datos en el sobre de un intercambio EDI contiene espacios iniciales o finales y una canalización de recepción promociona una propiedad de contexto con el valor de ese elemento de datos, la canalización de recepción quitará los espacios iniciales o finales de la propiedad de contexto. Como resultado, si crea una expresión de filtrado con esta propiedad de contexto, debe especificar un valor para la propiedad que no contenga espacios iniciales o finales. Si la expresión de filtro tenía espacios iniciales o finales, la expresión de filtro no se resolverá mediante una coincidencia con la propiedad de contexto, que no contendrá espacios iniciales ni finales.  
  
## <a name="default-party-as-interchange-receiver-properties-for-preserved-interchange-will-cause-the-send-pipeline-to-fail"></a>La entidad predeterminada como propiedades del receptor del intercambio para intercambio conservado provocará que se produzca un error en la canalización de envío.  
 Si BizTalk Server recibe un intercambio por lotes que debe conservarse (con el intercambio suspendido en caso de error), se producirá un error en la canalización de envío que se suscribe al intercambio si las propiedades de la entidad como receptor de intercambio se establecen con los valores predeterminados. Estas propiedades, como ISA5, Calificador de remitente, ISA6 e Identificador de remitente deben establecerse con valores válidos. BizTalk Server registrará un error que indica que el mensaje podría no serializarse debido a una configuración de entidad no válida. Este procesamiento no es correcto ya que un intercambio conservado tiene los parámetros de configuración necesarios como un Calificador de remitente o Identificador de remitente, en sus encabezados.  
  
## <a name="the-decimal-notation-in-a-message-will-be-changed-if-the-send-side-party-or-global-setting-specifies-a-different-decimal-notation"></a>Se cambiará la notación decimal en un mensaje si la entidad de envío o la configuración global especifica una notación decimal distinta.  
 Si la notación decimal utilizada en un intercambio es distinta de la notación decimal que especifica la propiedad de entidad de UNA3 para los mensajes de salida, BizTalk Server cambiará la notación decimal utilizada en el sobre del intercambio cuando lo serializa para enviarlo. Esto también sucederá si se utiliza la propiedad global de UNA3 en lugar de la propiedad de entidad de UNA3. Por ejemplo, si la notación decimal utilizada en un mensaje de entrada un punto y la propiedad de entidad de UNA3 o la propiedad global de UNA3 que determina la notación decimal de un mensaje saliente especifica una coma, BizTalk Server cambiará la notación decimal en el mensaje saliente a una coma.  
  
## <a name="edi-send-pipelines-cannot-be-executed-from-within-an-orchestration"></a>Las canalizaciones de envío EDI no pueden ejecutarse desde dentro de una orquestación.  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], normalmente puede ejecutar canalizaciones de envío dentro de una forma Expresión en una orquestación. Sin embargo, esto no funcionará con la canalización EDISend o la canalización AS2EdiSend. Estas canalizaciones deben ejecutarse dentro de un puerto de envío. Si intenta ejecutar la canalización EDISend o la canalización AS2EdiSend en una forma Expresión en una orquestación, la canalización no se enlazará con un puerto de envío y se suspenderá el mensaje.  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>La aplicación EDI de BizTalk no debe modificarse.  
 Los artefactos en la aplicación EDI de BizTalk no deben modificarse o eliminarse. Si se modifica esta aplicación, no será posible volver a la aplicación original quitando la configuración o volviendo a configurar las características EDI y AS2.  
  
## <a name="using-the-default-row-in-the-functional-group-header-grid-can-result-in-a-message-type-mismatch-between-the-interchange-header-and-the-group-header"></a>Mediante la fila predeterminada en la cuadrícula del encabezado de grupo funcional puede provocar una falta de coincidencia de tipo de mensaje entre el encabezado de intercambio y el encabezado de grupo.  
 Si el valor de UNH2.1 de un intercambio con codificación EDIFACT de salida no coincide con el valor de “Para tipo de mensaje UNH2.1” en la cuadrícula de la página Definición de segmentos UNG y UNH, es posible que el valor de UNG1 especificado en el mensaje puede no se corresponda con el valor de UNH2.1.  
  
 Esto puede ocurrir porque BizTalk rellenará el mensaje con los valores de UNG1 en la fila predeterminada de la cuadrícula, incluso si el mensaje no tiene coincidencia con el elemento UNH2.1 de esa fila predeterminada.  
  
 Si el valor de ST1 de un intercambio saliente con codificación X12 no coincide con el valor de “Para ST1” en la cuadrícula de la página Definición de segmentos GS y ST, el valor de GS1 especificado en el mensaje se determinará de forma dinámica, en función del valor de ST1.  
  
## <a name="invalid-character-in-data-element"></a>Carácter no válido en el elemento de datos  
 **Síntoma**  
  
 Al enviar un intercambio de EDI mediante la canalización de envío de EDI, es posible que reciba un error en el registro de eventos de aplicación en el que se indica que hay un "carácter no válido en el elemento de datos".  
  
 **Causa posible**  
  
 Este error puede ocurrir si un carácter incluido en los datos de carga también se usa como separador. Por ejemplo, si usas el ':' carácter como separador de componentes, pero los datos de carga también contiene el ':' caracteres.  
  
 Este es solo un problema de los intercambios con codificación X12.  
  
 **Resolución**  
  
 Use la **reemplazar separadores de carga con** en el **definición de segmento ISA** página de las propiedades de entidad EDI para especificar que los caracteres separadores existentes en los datos de carga debe ser reemplazada por el carácter de reemplazo especificado al enviar el intercambio.  
  
 Por ejemplo, al seleccionar **reemplazar separadores de carga con** y especificando el ' &#124;' carácter reemplazará cualquier aparición de un carácter separador en los datos de carga con el ' &#124;' cuando el intercambio es de caracteres envía mediante la canalización de envío EDI.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos del procesamiento de EDI](../core/known-issues-with-edi-processing.md)   
 [Cómo BizTalk Server envía mensajes EDI](../core/how-biztalk-server-sends-edi-messages.md)   
 [Tutorial (X12): Enviar intercambios EDI](../core/walkthrough-x12-sending-edi-interchanges.md)