---
title: "Validación de tipo (elemento de datos) EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd53685f-a49c-41c8-813e-29700fc0b62b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a989c58f59581795f641601938fe76bb7b1671f6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="edi-type-data-element-validation"></a>Validación de tipo EDI (elemento de datos)
La canalización de recepción EDI y la canalización de envío EDI llevan a cabo una validación de EDI en los elementos de datos del conjunto de transacciones. Esta validación se configura para todos los mensajes desde o a un usuario específico, a través de propiedades del acuerdo de esa entidad en el **validación** página (bajo la **configuración del conjunto de transacciones** sección para cualquier X12 o acuerdos EDIFACT). Si el **validación de tipo EDI** propiedad no está seleccionada en el **validación** página, los datos no se realizarán las validaciones que se describe en este tema.  
  
 Validación de tipo EDI está habilitada para los mensajes entrantes como salientes seleccionando la **validación de tipo EDI** propiedad en el **validación** página de las fichas del acuerdo bidireccional del **Propiedades de acuerdo** cuadro de diálogo. Esta propiedad está seleccionada de forma predeterminada para los mensajes entrantes y para los salientes, de modo que la validación EDI está habilitada de forma predeterminada.  
  
## <a name="validation-checks"></a>Comprobaciones de la validación  
 Cuando la canalización de recepción EDI o la canalización de envío EDI llevan a cabo una validación, lo hacen de los siguientes elementos:  
  
-   Tipos de datos definidos por las propiedades de EDI del esquema  
  
-   Restricciones de longitud  
  
-   Separadores finales y elementos de datos vacíos  
  
    > [!NOTE]
    >  En esta validación no se comprueban los conjuntos de códigos (enumeraciones) ni el número máximo ni mínimo de instancias.  
  
 **Juegos de caracteres**  
  
 Para llevar a cabo validaciones de elementos de datos de EDI, las canalizaciones de envío y recepción EDI necesitan que se establezca un juego de caracteres:  
  
-   Para EDIFACT, el juego de caracteres se establece en el elemento de datos **UNB1** de la **juego de caracteres y separadores** página de la ficha de acuerdo unidireccional del **propiedades del acuerdo de** cuadro de diálogo o la **configuración de reserva de EDIFACT** cuadro de diálogo (si no se ha establecido ningún acuerdo).  
  
-   Para KEDIFACT, el carácter se establece en el elemento de datos **UNB1** de la **juego de caracteres y separadores** página de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo cuadro, igual que para EDIFACT. El valor de la **UNB1.1** elemento debe estar establecido en `KECA`.  
  
-   En X12, el juego de caracteres se establece para el mensaje en las propiedades de la canalización.  
  
    > [!NOTE]
    >  Cuando el tiempo de ejecución de BizTalk lleva a cabo una validación de EDI de un mensaje, ésta utilizará el juego de caracteres de X12 seleccionado en las propiedades de la canalización. Sin embargo, la validación de las propiedades especificadas en las páginas de la **propiedades del acuerdo de** cuadro de diálogo se realiza con el juego de caracteres seleccionado en el **juego de caracteres y separadores** página del cuadro de diálogo. Durante el tiempo de ejecución, la canalización omite el valor de la X12 propiedad de juego de caracteres **juego de caracteres y separadores** página de la **propiedades del acuerdo de** cuadro de diálogo. Si estos dos valores no son iguales (es decir, el X12 propiedad del juego de caracteres en el **propiedades del acuerdo de** cuadro de diálogo se establece en **extendido** mientras el X12 propiedad caracteres en las propiedades de canalización está establecida en **Básica**), podría producir un error de validación del mensaje.  
  
 **Validación de tipo de datos**  
  
 Para X12, los siguientes tipos de datos EDI se anotan en el esquema para la validación por parte de los componentes Desensamblador/Ensamblador de las canalizaciones de recepción o de envío: numérico, decimal, identificador, cadena, fecha, hora, binario y compuesto.  
  
 Para EDIFACT, los siguientes tipos de datos EDI se anotan en el esquema para la validación por parte de los componentes Desensamblador/Ensamblador de las canalizaciones de recepción o de envío: alfabético, numérico, identificador, cadena y compuesto.  
  
 **Restricciones de longitud**  
  
 Tanto en X12 como en EDIFACT, los elementos o subelementos deben validarse en cuanto a requisitos de longitud (máxima y mínima). La longitud está definida por el número de posiciones de caracteres utilizado. No obstante, en ella no se incluyen signos ni notaciones decimales.  
  
> [!NOTE]
>  En un tipo de datos de cadena X12_AN, se conservan los espacios iniciales y se permiten los finales en todos los segmentos para satisfacer el requisito de longitud mínimo.  
  
 En KECA, la longitud está determinada por el número de bytes. Por ejemplo, si la longitud se define como tres, el elemento o subelemento puede incluir tres caracteres de un byte o la combinación de un carácter de dos bytes y un carácter de un byte.  
  
 **Vacía de elementos de datos y validación de separadores finales**  
  
 En X12, los elementos de datos que están marcados como obligatorios no pueden estar vacíos en una instancia si el segmento está presente. Si el elemento de datos es compuesto, debe valorarse un elemento de datos del componente, como mínimo.  
  
 En EDIFACT, los elementos de datos condicionales y sin valor (así como los subcomponentes) pueden excluirse; no obstante, el separador se conserva.  
  
 Los separadores finales no son necesarios en X12 o EDIFACT, pero sí recomendables.  
  
## <a name="when-edi-type-validation-is-disabled"></a>Cuando se deshabilita la validación de tipo EDI  
 Cuando se desactiva la validación de tipo EDI, la canalización de recepción EDI o la canalización de recepción EDI procesarán los elementos de datos que contienen errores comprobados por la validación de tipo EDI sin suspender el mensaje que se está procesando.  
  
> [!NOTE]
>  La validación estructural de EDI se lleva a cabo aunque esté deshabilitada la validación de tipo EDI. Un intercambio que genera un error en las validaciones estructurales básicas se suspenderá incluso en el caso de que se haya deshabilitado la validación de tipo EDI.  
  
 Algunos de los errores que se procesarán sin que se suspenda el mensaje son los siguientes:  
  
-   Un conjunto de transacciones inesperado o no definido.  
  
-   Datos inesperados o no definidos en el nivel del elemento de datos y del bucle o segmento.  
  
-   Opcionalidad (número máximo y mínimo de instancias) en el nivel del elemento de datos y del bucle o segmento.  
  
-   Infracción de la longitud (máxima o mínima) en el nivel del elemento de datos (datos con una longitud que supera el nivel máximo o que queda por debajo del nivel mínimo).  
  
-   No coincidencia del tipo de datos en el nivel del elemento de datos (con excepción del tipo de datos de Id., que cuenta con su control propio).  
  
-   Lista de enumeración no válida en el nivel del elemento de datos.  
  
 Si la validación de tipo EDI está deshabilitada en la fase de recepción pero habilitada en la de envío, la canalización de envío EDI no podrá volver a procesar el archivo XML que ha producido la canalización de recepción en un archivo EDI válido si el archivo XML contiene errores. Como consecuencia, la canalización de envío generará un error.  
  
 Si la validación de tipo EDI está deshabilitada, la canalización de envío o recepción EDI controlará errores de la siguiente forma:  
  
|||  
|-|-|  
|Datos inesperados|Acción|  
|Conjunto de transacciones inesperado o no definido|La canalización de envío o recepción EDI aceptará un conjunto de transacciones aunque no se haya implementado un esquema para aquél.|  
|Segmento o registro inesperado|La canalización de recepción generará una etiqueta con el prefijo adecuado: \<UnexpectedSegment_ % SegmentID %\>.<br /><br /> La canalización de envío utilizará los tres primeros caracteres del nombre de la etiqueta XML como nombre del segmento.|  
|Elemento de datos simple inesperado|La canalización de recepción generará una etiqueta XML con un prefijo, un identificador de segmento y un índice que representará la posición del elemento de datos en el segmento: <UnexpectedDataElement_%FieldName%.|  
|Elemento de datos compuesto inesperado|La canalización de recepción generará una etiqueta XML con un prefijo, un identificador de segmento y un índice que representará la posición del elemento de datos en el segmento: <UnexpectedCompositeDataElement_%FieldName%.|  
|Datos necesarios que faltan|La canalización tratará los datos como opcionales.|  
|Infracción de la longitud del elemento de datos|La canalización tratará la longitud no válida del elemento de datos como válida (mínimo = 0 y máximo = sin enlazar).|  
|Valor de enumeración no válido en la instancia (aplicable al tipo de datos del Id.)|La canalización omitirá el error y continuará el procesamiento.|  
|Infracción de repleción "máxima" en la instancia|La canalización tratará los datos repetitivos como válidos (número mínimo de instancias = 0 y número máximo de instancias = sin enlazar).|  
  
 **Informes de errores**  
  
 Cuando la validación de tipo EDI está desactivada, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no informa de los errores en el visor de eventos, pero sí emite una advertencia. Además, la confirmación devuelve el mensaje "Aceptar" a la entidad de origen, y establece los valores AK501 y AK901 como “E” en 997 de X12 o UCI.4, y UCM.3 y UCF.4 como “7” en CONTRL de EDIFACT. Como resultado, se eliminará toda posibilidad de rectificación en transmisiones futuras. Sin embargo, los receptores del mensaje tendrán la oportunidad de recuperar el documento a través de una intervención manual, en lugar de que se rechace o se suspenda el mensaje. Asimismo, la propiedad de contexto `Edi.ErrorsInTransactionSet` se promocionará si la canalización de recepción EDI detecta alguno de estos errores. Esta propiedad se promocionará como "True" si se detectan errores de validación de EDI o errores de validación ampliada. Si no se detectan errores, la propiedad se promocionará como "False".  
  
 Si la canalización de envío o recepción detecta datos inesperados, informará del error en el nivel principal, y omitirá los errores de los niveles secundarios, como sigue:  
  
|||  
|-|-|  
|Datos inesperados|Acción|  
|Conjunto de transacciones inesperado|La confirmación informa de este error y omite los errores posteriores en el nivel del elemento de datos y del bucle o segmento.|  
|Bucle o segmento inesperado|La confirmación informa de este error y omite los errores posteriores en el nivel del elemento de datos.|  
|Elemento de datos inesperado|La confirmación informa de este error y omite los errores compuestos relativos a propiedades del tipo Id., restricción, número de instancias, etc., así como los errores relativos a los campos compuestos del elemento de datos (si procede).|  
  
## <a name="see-also"></a>Vea también  
 [Validación del mensaje EDI](../core/edi-message-validation.md)   
 [Validación extendida (BTS-XSD)](../core/extended-bts-xsd-validation.md)