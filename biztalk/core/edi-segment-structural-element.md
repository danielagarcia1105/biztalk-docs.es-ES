---
title: Elemento estructural de segmento EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f474a3d-004a-4981-b155-b0a5775918ba
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b05d7a793fe515b8d0254d63b9b96994ddb35d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-segment-structural-element"></a>Elemento estructural de segmento EDI
El segmento consta de uno o más elementos de datos y es una unidad intermedia de información en el mensaje. Cada segmento comienza con un identificador de segmento de datos de tres caracteres y finaliza con un terminador de segmentos (de forma predeterminada el apostrofo (')). Los elementos de datos dentro del segmento se separan mediante separadores de elementos de datos. El separador de elementos de datos es, de forma predeterminada, el signo más (+). Un segmento se clasifica como Obligatorio u Opcional. Los separadores para intercambios salientes se pueden establecer en los acuerdos entre dos socios comerciales o como parte del acuerdo del socio comercial de reserva.  
  
## <a name="nesting"></a>Anidación  
 Segmentos pueden agruparse en una relación jerárquica denominada **anidamiento**. Hay dos tipos distintos de anidamiento: explícitas e implícitas. Dentro de cualquier intercambio, sólo puede utilizarse un tipo de anidamiento.  
  
-   El anidamiento explícito utiliza una indicación explícita de que se anida el bucle. Al utilizar el anidamiento explícito, el primer elemento de datos de componentes en la etiqueta de segmento será el código de segmento. Le seguirán los elementos de datos de componentes condicionales que indican los dos niveles y la incidencia de repetición del segmento. El número de elementos de datos de componentes utilizado para este propósito depende del nivel jerárquico en el que aparece el segmento en la estructura de mensaje. Si el segmento va a aparecer en el nivel uno, se utilizará el elemento de datos de componentes inmediatamente posterior al código de segmento. Si el segmento va a aparecer en el nivel dos, se utilizarán el elemento de datos de componentes inmediatamente posterior al código de segmento y el siguiente elemento de datos de componentes. Si el segmento va a aparecer en el nivel tres, se utilizarán los tres elementos de datos de componentes inmediatamente posteriores al código de segmento. Las canalizaciones no pueden realizar la comprobación de estructural de comparación de datos con la jerarquía.  
  
-   En la anidación implícita, se sigue el orden de los segmentos especificado en la estructura de mensaje de forma estricta. La relación de anidación entre los segmentos es evidente de forma implícita y no es necesaria ninguna otra indicación para el procesamiento.  
  
## <a name="loops"></a>Bucles  
 Pueden repetir una o más segmentos como un **bucle** dentro de una transacción establecido. Hay dos tipos distintos de bucles: enlazados y sin enlazar.  
  
### <a name="unbounded-loops"></a>Bucles sin enlazar  
 Un bucle sin enlazar no tiene un único segmento de identificación para marcar el principio y el final del bucle. Se repite un bucle sin enlazar de acuerdo con un recuento. Si el recuento no dispone de un valor, el bucle se repetirá dos veces. Los segmentos en el bucle sólo pueden producirse una vez en un orden establecido.  
  
 El inicio de un bucle sin enlazar se establece mediante un primer elemento de datos que es único. El primer elemento puede aparecer una vez y sólo una vez en cada repetición. Los bucles sin enlazar pueden anidarse dentro de los bucles. Si es así, el bucle interno sin enlazar no puede iniciarse en la misma posición ordinal que el bucle externo ni iniciarse con el mismo Id. de segmento que el bucle externo. El bucle anidado no puede contener un segmento que sea también el segmento del principio de cada bucle exterior en la misma estructura de anidación.  
  
### <a name="bounded-loops"></a>Bucles enlazados  
 Un bucle enlazado comienza con el segmento LS predefinido (Inicio de bucle) y finaliza con un segmento LE predefinido (Fin de bucle). La opcionalidad del segmento LS debe coincidir con la del primer segmento en el bucle. Un bucle enlazado puede contener otro bucle enlazado.  
  
> [!NOTE]
>  Un bucle enlazado en X12 y un bucle explícito en EDIFACT son equivalentes.  
  
 Se utiliza el enlace en un bucle con el fin de resolver la ambigüedad. El designador de requisitos en los segmentos LS/LE coincide con el designador de requisitos del primer segmento del bucle. Los enlaces reducen las restricciones estructurales impuestas acerca del uso de ciertos segmentos de repetición habituales. Los segmentos enlazados no tienen restricciones con respecto al comienzo del Id. de segmento. Esto activa el mismo segmento para iniciar el bucle enlazado y puede utilizarse fuera del bucle, como en el ejemplo siguiente:  
  
```  
AA  
LS  
BB  
CC  
LE  
BB  
```  
  
 Se permiten bucles subordinados (bucles dentro de bucles). Si los bucles subordinados se anidan dentro de bucles, el bucle interior no puede iniciarse en la misma posición ordinal que el bucle exterior. El bucle enlazado interior debe finalizar antes del bucle exterior inmediato.  
  
 Cada bucle enlazado dentro de un conjunto de transacciones debe tener un valor <loop_id> único definido de una a cuatro letras mayúsculas o dígitos numéricos. Se recomienda que los segmentos LS y LE correspondientes contengan el mismo valor único <loop_id>. El elemento de datos < loop_id > se procesará como un elemento de datos "normal" y se validan para el tipo de datos, longitud mín./máx., opcionalidad, etcetera. Validación de segmento cruzado (en LS y LE) no se llevará a cabo. BizTalk Server comprobará la resolución de ambigüedad sólo a través de la presencia del segmento LS y LE. En el caso de que se produzca una infracción de la regla de elemento de datos, el conjunto de transacciones se acepta con errores y BizTalk Server devuelve AK501=E y la valoración adecuada en AK2/AK3 en la confirmación.  
  
 También es necesario que se apliquen un par de segmentos LS/LE. En el caso de que se produzca una falta de coincidencia, se denegará el conjunto de transacciones debido a un problema relacionado con la resolución de ambigüedad y AK501 = E y AK502 = 5 se devuelven en el Visor de eventos y la confirmación 997. Si faltan los segmentos LS/LE pero el conjunto de transacciones no es ambiguo, éste se aceptará con errores y se devolverá AK501=E y AK502 = 5.  
  
 Un par LS/LE puede ser opcional u obligatorio. Sin embargo, a menos que el par se incluya en un bucle primario que sea repetible, éste nunca podrá ser de este tipo. En cualquier caso, tanto MaxOccurs para un par LS/LE puede ser 1, pero no inferior a 1. Esto es obligatorio en la validación de esquemas.  
  
 El desensamblador EDI y el ensamblador EDI controlan los segmentos LS y LE. Durante el análisis, el desensamblador crea nodos XML para los segmentos LS y LE, y valida los segmentos. Durante el proceso de serialización, el ensamblador crea los segmentos LS y LE a partir de nodos XML y los valida. Si un LS esperado o segmento LE es que falta, el conjunto de transacciones es rechaza o suspende con un AK501 = E y AK502 = 5. Si los segmentos LS/LE están presentes sin el correspondiente elemento de datos y la validación EDI está habilitada, el conjunto de transacciones se acepta con errores y AK501 = E y AK502 = 5 se muestran en el Visor de eventos y 997 confirmación.