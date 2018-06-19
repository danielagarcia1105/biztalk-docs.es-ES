---
title: Juegos de caracteres EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57fae748-d66e-4ecf-be00-70147078ef93
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38d7b19c751f2bd380dad29ffc31a2be5f79245e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971394"
---
# <a name="edi-character-sets"></a>Juegos de caracteres de EDI
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa un juego de caracteres para validar un intercambio EDI completo. Los juegos de caracteres usados para un mensaje codificado con X12 y un mensaje codificado con EDIFACT o KEDIFACT se determinan de distintos modos.  
  
## <a name="edifact-character-set"></a>Juego de caracteres EDIFACT  
 Un intercambio codificado con EDIFACT se autodescribe en términos del juego de caracteres. Se usa el elemento de datos UNB1. EDIFACT requiere que los nombres de etiquetas y separadores/delimitadores son tipos ASCII. Como resultado, es posible ubicar UNB1 para aplicar la página de código relevante para el intercambio restante.  
  
 Al procesar un mensaje EDIFACT entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina el juego de caracteres que se debe usar para dicho mensaje a partir del elemento de datos UNB1. No es necesario realizar ninguna configuración en el acuerdo entre socios comerciales.  
  
 Al procesar un mensaje EDIFACT saliente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el juego de caracteres del acuerdo entre socios comerciales o el acuerdo de reserva. Establezca el elemento de datos UNB1 en la **juego de caracteres y separadores** página en las fichas de acuerdo bidireccional (si se ha definido un acuerdo) o la **juego de caracteres y separadores** página en la pestaña del acuerdo el **Configuración de reserva de EDIFACT** cuadro de diálogo (si no se ha definido ningún acuerdo). UNB1.1 es un elemento de datos compuesto obligatorio denominado identificador de sintaxis. UNB1.2 es la versión del juego de caracteres EDIFACT. El elemento de datos UNB1 también se usa para validar los valores especificados para las propiedades en la interfaz de usuario del administrador de acuerdos entre socios comerciales al guardar el conjunto completo de propiedades (no cuando se salga de un campo o aparezca una página distinta).  
  
 Los juegos de caracteres disponibles son KECA, UNOA, UNOB, UNOC, UNOD, UNOE, UNOF, UNOG, UNOH, UNOI, UNOJ, UNOK, UNOX y UNOY. El valor predeterminado es UNOB. EL juego de caracteres completo para estos niveles se especifica en ISO 9735 Reglas sintácticas EDIFACT.  
  
> [!NOTE]
>  Si el juego de caracteres UNOC se encuentra en un intercambio entrante o saliente, el desensamblador EDI o el ensamblador EDI usará la página de código Latin-1, en lugar de la página de código UTF-8. Esto se requiere debido a que UTF-8 no es un supraconjunto de UNOC. Algunos caracteres que son aceptables en UNOC harán que el intercambio se suspenda al procesarlos como UTF-8.  
  
 Los caracteres de algunos juegos de caracteres EDIFACT pueden ser caracteres de doble byte, mientras que en otros juegos de caracteres EDIFACT pueden ser caracteres de un solo byte. Debido a ello, al establecer los criterios de versión para lotes basados en el número de caracteres del intercambio, el número de bytes del intercambio puede ser distinto en función del juego de caracteres utilizado.  
  
 El segmento UNA y el nombre del segmento UNB se limitan a los valores del juego de caracteres ASCII.  
  
## <a name="kedifact-character-set"></a>Juego de caracteres KEDIFACT  
 Al igual que EDIFACT, el juego de caracteres de un intercambio codificado con KEDIFACT se establece en el elemento de datos UNB1. Igual que para EDIFACT, el juego de caracteres que va a aplicar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] al procesar un intercambio KEDIFACT se establece en el elemento de datos **UNB1** de **juego de caracteres y separadores** página en el bidireccional pestañas de acuerdo (si se ha definido un acuerdo) o la **juego de caracteres y separadores** página en la pestaña del acuerdo el **configuración de reserva de EDIFACT** cuadro de diálogo (si no se ha definido ningún acuerdo). El valor de la **identificador (UNB1.1)** elemento debe establecerse en KECA.  
  
## <a name="x12-character-set"></a>Juego de caracteres X12  
 Si la canalización de recepción de BizTalk o la canalización de envío realiza la validación de EDI de un mensaje codificado con X12, usará el juego de caracteres de X12 seleccionado en la propiedad CharacterSet de la canalización. Para establecer esta propiedad, abra el cuadro de diálogo Propiedades de la ubicación de recepción o del puerto de envío, haga clic en el botón de puntos suspensivos que aparece junto a la canalización de recepción o de envío y, a continuación, establezca la propiedad CharacterSet para el desensamblador o ensamblador.  
  
 La propiedad CharacterSet de la canalización se usa para validar un intercambio X12 debido a que, a diferencia de EDIFACT o KEDIFACT, un intercambio con codificación X12 no se autodescribe en términos de su juego de caracteres. Leer el encabezado ISA con la codificación ISO o UTF puede dar lugar a valores distintos para la búsqueda de acuerdo. Como resultado, BizTalk debe conocer el juego de caracteres aplicable que se va a usar en el procesamiento del mensaje antes de la búsqueda de acuerdos (cuando se obtendría el juego de caracteres aplicable para el acuerdo).  
  
 Especifique el X12 carácter conjunto que se usará para la validación de acuerdo en la en la **juego de caracteres y separadores** página en las fichas de acuerdo bidireccional (si se ha definido un acuerdo) o el **juego de caracteres y separadores**página en la ficha de acuerdo de reserva de la **X12 configuración de reserva** cuadro de diálogo (si no se ha definido ningún acuerdo). No obstante, BizTalk sólo usa esta configuración para validar los valores especificados para las propiedades relacionadas al guardar el conjunto completo de propiedades (no cuando se salga de un campo o aparezca una página distinta). La canalización de recepción o de envío omitirá estas propiedades del juego de caracteres.  
  
> [!NOTE]
>  Si el juego de caracteres especificado en el acuerdo o en el acuerdo de reserva no coincide con el juego de caracteres seleccionado para la canalización de recepción o de envío, se podría producir un error en la validación del mensaje. Un ejemplo podría ser si la propiedad del juego de caracteres de X12 del acuerdo se establece en Ampliado, mientras que la propiedad de caracteres de X12 de las propiedades de la canalización se establece en Básico.  
  
 Los juegos de caracteres disponibles son Básico y Ampliado (como se documenta en las guías de especificaciones/implementación de X12) y UTF8/Unicode. El valor predeterminado es UTF8.  
  
> [!NOTE]
>  Los valores especificados para el separador de elemento de datos, separador de elemento de componentes y terminador de segmento en el acuerdo bidireccional o acuerdo de reserva se limitan a los valores del juego de caracteres ASCII. Estas propiedades no se validan con respecto al juego de caracteres de X12.  
  
 El juego de caracteres básico incluye las siguientes letras en mayúscula, dígitos, espacio y caracteres especiales: A-z, 0-9,! “ & ’ ( ) * + , - . / : ; ? = (espacio).  
  
 El juego de caracteres ampliado incluye los caracteres de los caracteres del idioma seleccionado conjunto y letras minúsculas, caracteres básico y otros caracteres especiales: a z, % @ [] _ {} \ &#124; \< \> ~ # $.  
  
## <a name="see-also"></a>Vea también  
 [Mensajería EDI](../core/edi-messaging.md)   
 [Esquemas EDI](../core/edi-schemas.md)