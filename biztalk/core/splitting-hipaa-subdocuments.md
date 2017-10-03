---
title: Dividir subdocumentos HIPAA | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66d9badd-00c6-43a3-807e-0ad313983adc
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 799cb5813b3c13339a0c477bf142a467a91b2c94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="splitting-hipaa-subdocuments"></a>Dividir subdocumentos HIPAA
Los intercambios EDI para HIPAA suelen tener varios documentos secundarios/subdocumentos en un único conjunto de transacciones, limitado por los encabezados ST/SE. La canalización de recepción EDI admite la creación de subdocumentos HIPAA individuales en dicho conjunto de transacciones. Es distinta de los intercambios EDI que no son para HIPAA, en los que se procesa un solo conjunto de transacciones como mensaje único.  
  
## <a name="subdocument-splitting-schemas"></a>Esquemas de división de subdocumentos  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite la división de los siguientes tipos de documento HIPAA a través de esquemas nativos:  
  
-   Documentos HIPAA versión 4010: inscripción 834, pago de reclamaciones 835 y tres variantes de la reclamación 837  
  
-   Documentos HIPAA versión 5010: estado de la reclamación 276/277 – solicitud y respuesta, inscripción 834 y tres variantes de la reclamación 837  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona dos versiones de esquemas para cada uno de estos tres tipos de documentos. Para cada tipo de documento, el esquema que admite la división se identifica por la etiqueta ‘Multiple’ en el nombre de archivo. El otro esquema no admite la división de subdocumentos.  
  
 En algunos escenarios, es posible que se requieran los esquemas de división y no división. Esto se admitirá mediante el uso de un espacio de nombres de destino personalizado para una variante del esquema.  
  
## <a name="how-subdocument-splitting-is-enabled"></a>Cómo se habilita la división de subdocumentos  
 La división de subdocumentos HIPAA se habilita mediante tres entradas de anotación en el esquema HIPAA. Las dos primeras son entradas para el esquema de la anotación appinfo, que debe establecerse en **Sí**:  
  
```  
subdocument_break = "yes" Split_Without_Sibling_Data = "Yes"  
```  
  
 La tercera entrada de anotación se ubica en los niveles de registro correspondientes del esquema HIPAA. Esta propiedad también debe establecerse en **Sí**.  
  
```  
subdocument_creation_break = "yes"  
```  
  
 Un intercambio HIPAA se dividirá en subdocumentos solo si la anotación de interrupción de creación de subdocumentos en el esquema HIPAA se establece como "yes" y la propiedad de entidad de opción de procesamiento por lotes entrantes se establece como "Dividir intercambio en conjuntos de transacciones". Si la propiedad de entidad de opción de procesamiento por lotes entrantes se establece para conservar el intercambio, el desensamblador EDI no dividirá el intercambio en subdocumentos. En este caso, el desensamblador EDI omitirá la anotación. No aparecerá ninguna advertencia en el visor de eventos si esto ocurre.  
  
> [!NOTE]
>  No se pueden anidar las anotaciones de interrupción de creación de subdocumentos. Si un esquema incluye un bucle que tiene una anotación de subdocumento aplicada a él, dicho bucle no puede contener otro bucle que tenga una anotación de subdocumento aplicada a él.  
  
## <a name="how-subdocuments-are-processed"></a>Cómo se procesan los subdocumentos  
 El desensamblador EDI de la canalización de recepción EDI divide los subdocumentos. Una vez que la canalización de recepción valida el intercambio entrante y genera las confirmaciones correspondientes, enruta cada subdocumento individual en el cuadro de mensajes. Todos los subdocumentos son válidos desde el punto de vista estructural y sintáctico. No obstante, se espera que los resúmenes de nivel empresarial, totales del conjunto de transacciones y números de control del conjunto de transacciones se encuentren fuera de la sincronización. La canalización de envío sobrescribirá el valor del número de segmento existente en SE01 de cada uno de los subdocumentos (que provenía del conjunto de transacciones original) con el número de segmentos incluidos en el subdocumento. Además, la canalización de recepción restablecerá los números de control del conjunto de transacciones en cada uno de los subdocumentos para que el subdocumento no tenga números de control duplicados. Esto garantiza que el procesamiento de envío se lleva a cabo sin ningún error.  
  
 Si un conjunto de transacciones genera un error en EDI o en la validación extendida durante la división de subdocumentos, se suspende el conjunto de transacciones individual con errores.  
  
 Un puerto de envío que se suscribe a los subdocumentos recogerá los subdocumentos del cuadro de mensajes, serializará los subdocumentos XML, los procesará por lotes (si está habilitada esta opción), los validará y los enviará. La canalización de envío actualiza el número de elementos de datos en segmentos (SE01).  
  
## <a name="how-subdocuments-are-split"></a>Cómo se dividen los subdocumentos  
 Una anotación de interrupción de creación de subdocumentos se suele aplicar a un bucle que incluye uno o varios elementos en un esquema HIPAA. Otros elementos antes y después del bucle de interrupción del esquema se replican en todos los subdocumentos.  
  
 En la siguiente tabla se muestra un ejemplo de división de subdocumentos. En este ejemplo, la anotación de interrupción de creación de subdocumentos se establece como "yes" para el bucle del elemento CC. Como resultado, los elementos CC del conjunto de transacciones se separan en subdocumentos individuales, mientras que los elementos AA, BB y DD del conjunto de transacciones se incluyen en los subdocumentos individuales.  
  
|Esquema (número mínimo y máximo de coincidencias)|Instancia original|Subdocumento #1|Subdocumento #2|Subdocumento n.º 3|  
|---------------------------------------|-----------------------|---------------------|---------------------|---------------------|  
|ST (1,0)|ST|ST|ST|ST|  
|AA (1,1)|AA|AA|AA|AA|  
|Bucle BB (1,n)<br /><br /> BB1 (1,n)<br /><br /> Bucle CC (1,n) - subdocument_break = "yes"<br /><br /> CC1 (1,n)<br /><br /> CC2 (0,n)<br /><br /> BB2 (0,n)|BB1*1<br /><br /> CC1\*1<br /><br /> CC2\*1<br /><br /> BB2\*1<br /><br /> BB1\*2<br /><br /> CC1\*2<br /><br /> CC2\*2<br /><br /> BB1\*3<br /><br /> CC1\*3<br /><br /> CC2\*3|BB1*1<br /><br /> CC1\*1<br /><br /> CC2\*1<br /><br /> BB2\*1|BB1*2<br /><br /> CC1\*2<br /><br /> CC2\*2|BB1*3<br /><br /> CC1\*3<br /><br /> CC2\*3|  
|DD (0,n)|DD|DD|DD|DD|  
|SE|SE|SE|SE|SE|