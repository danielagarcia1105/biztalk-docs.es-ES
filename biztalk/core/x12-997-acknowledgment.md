---
title: X12 confirmación 997 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62a352fb-635c-4f0e-9844-4b250159333d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1868c6c644940c49f854282980efc09c631b2cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290892"
---
# <a name="x12-997-acknowledgment"></a>Confirmación 997 de X12
La confirmación funcional X12 997 informa del estado de un intercambio recibido. Informa de cada error encontrado al procesar el documento recibido. La canalización de recepción de BizTalk EDI siempre genera un 997 conforme con 4010; no obstante, la canalización de recepción de EDI y las canalizaciones de envío de EDI también pueden validar un 997 conforme con 5010.  
  
 Al igual que todos los conjuntos de transacciones de X12, la confirmación 997 se envía dentro de un sobre GS/GE. Los conjuntos ST y SE no son distintos a otros conjuntos de transacciones.  
  
 Los segmentos del conjunto de transacciones de una confirmación 997 se muestran en la siguiente tabla.  
  
|Posición|Segment<br />ID|Nombre|Req.<br />DES.|Máximo de Utilice|Bucle<br />Repita|  
|--------------|-----------------|----------|----------------|--------------|------------------|  
|010|ST|Encabezado del conjunto de transacciones (para la confirmación)|M|1|-|  
|020|AK1|Encabezado de respuesta de grupo funcional|M|1|-|  
|030|AK2|Encabezado de respuesta de conjunto de transacciones|O|1|999999 <br />(Id. de bucle = AK2)|  
|040|AK3|Nota del segmento de datos|O|1|999999 <br />(Id. de bucle = AK2/AK3)|  
|050|AK4|Nota del elemento de datos|O|99|-|  
|060|AK5|Finalizador de respuesta de conjunto de transacciones|M|1|-|  
|070|AK9|Finalizador de respuesta de grupo funcional|M|1|-|  
|080|SE|Finalizador del conjunto de transacciones (para la confirmación)|M|1|-|  
  
-   Req. DES. = Designación de requisito  
  
-   M = Obligatorio  
  
-   O = Opcional  
  
 A continuación se describen los segmentos AK. Los segmentos del bucle AK2 a AK5 proporcionan información acerca de un error con un conjunto de transacciones.  
  
## <a name="ak1"></a>AK1  
 El segmento AK1 obligatorio identifica el grupo funcional que se va a confirmar con dos elementos de datos siguientes:  
  
-   AK101 es el Id. de grupo funcional (GS01) del grupo funcional que se va a confirmar.  
  
-   AK102 es el número de control de grupo (GS06 y GE02) del grupo funcional que se va a confirmar.  
  
-   AK103 es opcional y es la versión de implementación de EDI enviada en el GS08 de la transacción original. AK103 admite 997 conforme con 5010 de entrada.  
  
## <a name="ak2"></a>AK2  
 El segmento AK2 opcional contiene una confirmación para un conjunto de transacciones en el grupo funcional recibido. Si hay varios segmentos AK2, se enviarán como una serie de bucles. Los bucles AK2 identifican un conjunto de transacciones en el orden en que se han recibido. El segmento AK2 identifica el conjunto de transacciones con dos elementos de datos:  
  
-   AK201 es el Id. del conjunto de transacciones (ST01) del conjunto de transacciones que se va a confirmar.  
  
-   AK202 es el número de control de conjunto de transacciones (ST02 y SE02) del conjunto de transacciones que se va a confirmar.  
  
-   AK203 es opcional y es la versión de implementación de EDI enviada en el ST03 de la transacción original. AK203 admite 997 conforme con 5010 de entrada.  
  
 Un bucle AK2 contendrá segmentos AK3, AK4 y AK5 si un conjunto de transacciones se encuentra en error. Para obtener más información, consulte las descripciones para estos segmentos a continuación.  
  
 Puede especificar que los segmentos AK2 se generan para todos los conjuntos de transacciones, si se ha aceptado o rechazado, o sólo para conjuntos de transacciones rechazados. BizTalk Server generará segmentos AK2 para conjuntos de transacciones aceptadas (donde AK501 == A) si selecciona el **incluir bucle AK2 para conjuntos de transacciones aceptadas** casilla de verificación en la **confirmaciones** página de la Cuadro de diálogo de propiedades de acuerdo para un acuerdo entre dos perfiles de negocio (o la **confirmaciones** página de la X12 ficha de configuración para un perfil de negocio). En caso contrario, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará bucles AK2 solo para conjuntos de transacciones rechazados. Si no se resuelve un acuerdo para el intercambio al que se está respondiendo, la configuración de la generación de 997 toma de forma predeterminada el valor de la configuración del acuerdo de reserva y los segmentos AK2 no se generan para los conjuntos de transacciones aceptados.  
  
## <a name="ak3"></a>AK3  
 El segmento AK3 opcional genera informes de errores en un segmento de datos e identifica la ubicación del segmento de datos. Se crea un segmento AK3 para cada segmento de un conjunto de transacciones que tenga uno o varios errores. Si hay varios segmentos AK3, se enviarán como una serie de bucles (un segmento por bucle). El segmento AK3 contiene cuatro elementos de datos que especifican la ubicación de los segmentos que contienen errores y genera informes del tipo de error sintáctico encontrado en dicha ubicación:  
  
-   AK301 identifica el segmento que contiene el error con su Id. de segmento X12, por ejemplo, NM1.  
  
-   AK302 es el número de segmento del segmento que contiene el error. El segmento ST es "1" y cada uno de los segmentos aumenta el número de segmentos en uno.  
  
-   AK303 identifica un bucle enlazado: un bucle rodeado por un segmento LS y un segmento LE. AK303 contiene los valores de los segmentos LS y LE que enlazan el segmento que contiene el error.  
  
-   AK304 es el código de error del segmento de datos. AK304 es opcional, pero se requiere si existe un error en el segmento identificado. Para obtener una lista de los códigos de error de AK304, vea [X12 códigos de Error de confirmación 997](../core/x12-997-acknowledgment-error-codes.md).  
  
## <a name="ak4"></a>AK4  
 El segmento AK4 opcional informa de errores en un elemento de datos o en la estructura de datos compuesta e identifica la ubicación del elemento de datos. Se envía cuando el elemento de datos AK304 es "8", "El segmento contiene errores de elementos de datos". Se puede repetir hasta 99 veces en todos los segmentos AK3. El segmento AK4 tiene contiene cuatro elementos de datos que especifican la ubicación de los elementos de datos o la estructura de datos compuesta que contiene errores e informa del tipo de error sintáctico encontrado en dicha ubicación.  
  
-   AK401 es un elemento de datos compuesto con los campos AK41.1, AK41.2 y AK41.3. AK401-1 identifica el elemento de datos o la estructura de datos compuesta que contienen un error con su recuento numérico. Por ejemplo, si el segundo elemento de datos del segmento tiene un error, AK401 es igual a "2". AK401-2 identifica el recuento numérico del elemento de datos del componente de una estructura de datos compuesta que tiene un error. Si AK401 informa de un error en una estructura de datos que no es compuesta, no se ha especificado valor para AK401-2.  
  
     AK41.3 es opcional y es la posición del elemento de datos de repetición. AK41.3 admite 997 conforme con 5010 de entrada.  
  
-   AK402 es opcional e identifica el número simple del elemento de datos X12 del elemento que contiene el error. Por ejemplo, NM101 es el número 98 simple del elemento de datos X12.  
  
-   AK403 es obligatorio e informa del error del elemento identificado. Para obtener una lista de los códigos de error de AK403, vea [X12 códigos de Error de confirmación 997](../core/x12-997-acknowledgment-error-codes.md).  
  
-   AK404 es opcional y contiene una copia de elemento de datos identificado que contiene el error. AK404 no se utiliza si el error indica un carácter no válido.  
  
## <a name="ak5"></a>AK5  
 El segmento AK5 indica si el conjunto de transacciones identificado en el segmento AK2 se identifica o se rechaza y el motivo. El segmento AK5 es obligatorio si se incluye en la confirmación el bucle AK2 opcional. El segmento AK4 tiene un elemento de datos obligatorio que especifica el estado del conjunto de transacciones y de uno a cinco elementos de datos opcionales que proporcionan códigos de error basados en la sintaxis que edita el conjunto de transacciones.  
  
-   AK501 especifica si se acepta o rechaza el conjunto de transacciones identificado. Para obtener una lista de los códigos de error de AK501, vea [X12 códigos de Error de confirmación 997](../core/x12-997-acknowledgment-error-codes.md).  
  
-   Los códigos de error de AK502 a AK506 indican la naturaleza del error. Para obtener una lista de los códigos de error de AK501, vea [X12 códigos de Error de confirmación 997](../core/x12-997-acknowledgment-error-codes.md).  
  
## <a name="ak9"></a>AK9  
 El segmento AK9 obligatorio indica si el grupo funcional identificado en el segmento AK1 se acepta o se rechaza y el motivo. El segmento AK9 contiene cuatro elementos de datos obligatorios que especifican el estado del conjunto de transacciones y la naturaleza del error, así como de uno a cinco elementos opcionales que especifican los errores indicados.  
  
-   AK901 es obligatorio y especifica si se acepta o se rechaza el grupo funcional identificado en AK1. Para obtener una lista de los códigos de error de AK901, vea [X12 códigos de Error de confirmación 997](../core/x12-997-acknowledgment-error-codes.md).  
  
-   AK902 especifica el número de conjuntos de transacciones incluido en el finalizador del grupo funcional identificado (GE01).  
  
-   AK903 especifica el número de conjuntos de transacciones recibido.  
  
-   AK904 especifica el número de conjuntos de transacciones aceptado en el grupo funcional identificado.  
  
-   Los códigos de error de AK905 a AK909 pueden indicar de uno a cinco errores indicados en el grupo funcional identificado. Para obtener una lista de AK905 a AK909 códigos de error, consulte [X12 códigos de Error de confirmación 997](../core/x12-997-acknowledgment-error-codes.md).  
  
## <a name="see-also"></a>Vea también  
 [X12 códigos de Error de confirmación 997](../core/x12-997-acknowledgment-error-codes.md)