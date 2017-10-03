---
title: EDI encabezados y finalizadores | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf1dae3-9570-413d-a85d-94dcbb561906
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 655a7261da5dc66687fdf0cd623802854c0fa4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-headers-and-trailers"></a>Encabezados y finalizadores EDI
Las partes de un intercambio EDI se delimitan por encabezados y finalizadores que deben cumplir los estándares de X12 o EDIFACT. El encabezado y el finalizador de control de intercambio se utilizan sólo una vez; el grupo funcional y los finalizadores y encabezados del conjunto de transacciones se repiten si los conjuntos de transacciones y los grupos se procesan por lotes en el intercambio. Todos los encabezados y finalizadores se componen de una serie de elementos de datos que contienen información acerca del contenido del encabezado y del finalizador.  
  
 Los encabezados y finalizadores para X12 y EDIFACT son similares. La diferencia principal es el encabezado de la notificación del servicio UNA para EDIFACT, que define los separadores usados en el intercambio. En la codificación X12, los separadores se definen en el encabezado de control de intercambio ISA.  
  
 Los encabezados y finalizadores de control de intercambio y del grupo funcional se indican como segmentos de sobre. Si BizTalk Server divide un intercambio entrante en conjuntos de transacciones, guarda estos segmentos de sobre como propiedades de contexto. Las propiedades de sobre claves que son de ayuda para el enrutamiento se encuentran disponibles como propiedades individuales. Esto no se realiza si se conserva el intercambio, en cuyo caso los datos de sobre forman parte del mensaje.  
  
 En caso de que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genere un mensaje saliente, basará los encabezados y finalizadores en los acuerdos entre socios comerciales (o los acuerdos globales si no se ha determinado ninguna entidad).  
  
 Los campos de encabezado y finalizador, así como los caracteres separadores que se usan para separarlos en los intercambios, se definen en el acuerdo entre las dos entidades. Un carácter separador no se debe usar en la definición de ninguno de los campos de intercambio, grupo o finalizador o encabezado del conjunto de transacciones, según se defina para el acuerdo. Si se usan, el intercambio dará lugar a un error en el procesamiento del ensamblador EDI del servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de envío o del desensamblador de la entidad receptora. El intercambio no se llevará a cabo correctamente en el ensamblador EDI si existe un lote saliente, ya que el ensamblador validará el sobre con el esquema de control de encabezado (servicio). Si el intercambio no se ha procesado por lotes, el ensamblador EDI lo serializará, pero se producirá un error en el procesamiento del desensamblador en el acuerdo de recepción.  
  
## <a name="x12-headers-and-trailers"></a>Encabezados y finalizadores X12  
 Los encabezados y finalizadores de un mensaje codificado con X12 tienen el siguiente aspecto:  
  
```  
ISA Interchange Control Header  
  GS Functional Group Header  
    ST Transaction Set Header  
    SE Transaction Set Trailer  
  GE Functional Group Trailer  
IEA Interchange Control Trailer  
```  
  
 Si un encabezado ISA va seguido inmediatamente de un finalizador IEA, el intercambio está vacío. Si existe un conjunto de transacciones, deben estar presentes el encabezado GS y el finalizador GE; en caso contrario, serán condicionales.  
  
 Los campos de encabezado de control de intercambio ISA de un mensaje codificado con X12 son de longitud fija. En algunos de los campos, puede especificar un valor inferior a la longitud fija del campo. Si lo hace, el intercambio debe contener espacios finales (para un campo de cadena) o ceros iniciales (para un campo numérico) de modo que cada campo tenga la longitud requerida. Al crear un intercambio saliente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] especificará los espacios finales o ceros iniciales para crear un encabezado de control de intercambio de la longitud adecuada. Los campos de encabezado del grupo GS y los campos de encabezado del conjunto de transacciones ST no tienen una longitud fija.  
  
 En la codificación X12, el encabezado de seguridad funcional y de control funcional, el segmento del valor de seguridad funcional y los segmentos de finalizador de seguridad funcional exceden el ámbito de EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si se recibe un intercambio con estos segmentos, se suspenderá con un registro de error que indica que los segmentos están sin identificar.  
  
 El campo ST01 el código de Id. del conjunto de transacciones; el campo ST02 es el número de control del conjunto de transacciones. El campo ST03 es el identificador de la versión de esquema. El campo SE01 indica el número de segmentos incluido en el conjunto de transacciones; el del campo SE02 es el mismo que el del campo ST02 (número de control de conjuntos de transacciones). Al analizar un mensaje entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprobará que el número de segmentos del conjunto de transacciones corresponde al valor del campo SE01. Al generar un mensaje saliente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] definirá el campo SE01 en el número correcto de segmentos en el conjunto de transacciones.  
  
 Un conjunto de transacciones XML que se va a serializar en un intercambio EDI saliente debe tener un encabezado y finalizador del conjunto de transacciones. No obstante, el ensamblador EDI procesará el mensaje si no tiene un encabezado o finalizador del conjunto de transacciones. Los segmentos de encabezado y finalizador del conjunto de transacciones en esquemas X12 y EDIFACT son opcionales para los conjuntos de transacciones XML. Si una transacción no tiene un encabezado ni un finalizador, el ensamblador EDI en la canalización de envío EDISend o AS2EDISend agregará los valores de encabezado y finalizador del conjunto de transacciones a ella. Estos valores se basarán en las asignaciones o los cálculos. El ensamblador EDI lo hará para el intercambio XML (un lote conservado), conjunto de transacciones procesado por lotes XML y un conjunto de transacciones XML. Para obtener más información, consulte [X12 segmentos de finalizador y encabezado del conjunto de transacciones](../core/how-the-edi-assembler-works.md#BKMK_X12) o [encabezado del conjunto de transacciones de EDIFACT y segmentos de finalizador](../core/how-the-edi-assembler-works.md#BKMK_EDIFACT).  
  
## <a name="edifact-headers-and-trailers"></a>Encabezados y finalizadores de EDIFACT  
 Los encabezados y finalizadores de un mensaje codificado con EDIFACT tienen el siguiente aspecto:  
  
```  
UNA Service String Advice  
UNB Interchange Control Header  
  UNG Functional Group Header  
    UNH Message Header  
    UNT Message Trailer  
  UNE Functional Group Trailer  
UNZ Interchange Control Trailer  
```  
  
 No se requiere el encabezado UNA. Se requiere el encabezado UNB. Si el encabezado UNA está presente, contiene los delimitadores que se deben usar al procesar el mensaje entrante. En caso contrario, se usarán los separadores definidos para la propiedad de canalización EfactDelimiters.  
  
 Si un encabezado UNB va seguido inmediatamente de un finalizador UNZ, el intercambio está vacío. Si un encabezado UNG va seguido inmediatamente de un finalizador UNE, el grupo está vacío. La pareja del encabezado UNG y finalizador UNE es condicional y no tiene que estar presente en un mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Estructura de mensaje EDI](../core/edi-message-structure.md)