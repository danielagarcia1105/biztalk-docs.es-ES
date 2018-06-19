---
title: Cómo se almacenan los datos para los mensajes EDI entrantes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8cbcb96-c0af-4f41-b844-f0e684a4af7c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9a395e691835f3e21622ebf5f29c2845361fb36
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971562"
---
# <a name="how-data-is-stored-for-inbound-edi-messages"></a>Cómo se almacenan los datos correspondientes a mensajes EDI de entrada
Para generar una entrada del informe de estado correspondiente a un intercambio de entrada y a la confirmación enviada como respuesta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lleva a cabo lo siguiente:  
  
1.  Cuando la canalización de recepción EDI envía el XML del mensaje de entrada al cuadro de mensajes, esta canalización crea las siguientes entradas en el almacén de datos de informes de estado con los valores siguientes:  
  
    -   Una entrada de informe de estado por cada intercambio recibido, cuyo estado se establece como Aceptado/Parcialmente aceptado/Rechazado  
  
    -   Una entrada de informe de estado por cada confirmación técnica (intercambio), una por intercambio, cuyo estado se establece como Generado  
  
    -   Una entrada de informe de estado por cada confirmación funcional, una por grupo en X12 y una para todos los grupos en EDIFACT, cuyo estado se establece como Generado.  
  
2.  Una vez que la canalización de envío haya enviado las confirmaciones al socio comercial, la canalización de envío EDI actualiza las entradas de estado de confirmación de intercambio y de estado de confirmación funcional a Enviado, según corresponda. No se realizan cambios en la entrada de estado del intercambio.  
  
## <a name="data-stored-by-the-receive-pipeline-for-inbound-interchanges"></a>Datos almacenados por la canalización de recepción correspondientes a los intercambios de entrada  
 La canalización de recepción crea un registro en el almacén de datos de informes de estado para cada intercambio que recibe. Los datos almacenados incluyen:  
  
-   Tipo de registro = Estado de intercambio  
  
-   Dirección de intercambio = Recepción  
  
-   Receptor del intercambio = Datos actualizados  
  
-   Remitente del intercambio = Datos actualizados  
  
-   Fecha del intercambio = Datos actualizados  
  
-   Hora del intercambio = Datos actualizados  
  
-   Id. de control de intercambio = Datos actualizados  
  
-   Estado del intercambio = Datos actualizados  
  
-   Número de grupos en el intercambio = Datos actualizados (En EDIFACT los grupos son opcionales; si no se encuentran, el valor es "No aplicable”)  
  
-   Id. del puerto de recepción del intercambio = Datos actualizados  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-generated-in-response-to-an-inbound-interchange"></a>Datos almacenados por la canalización de recepción correspondientes a cada confirmación técnica generada en respuesta a un intercambio de entrada  
 La canalización de envío crea un registro en el almacén de datos de informes de estado para cada confirmación técnica que envía. La confirmación técnica es TA1 para X12 y el mensaje CONTRL con solo el segmento UCI para EDIFACT. La mayoría de los datos necesarios para la entrada están disponibles a partir de los segmentos de encabezado y finalizador del intercambio (ISA/IEA o UNB/UNZ). Otros datos están disponibles a partir de las propiedades del puerto de envío. Los datos almacenados incluyen:  
  
-   Tipo de registro = Estado de confirmación del intercambio  
  
-   Dirección de confirmación del intercambio = Recepción  
  
-   Receptor del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Remitente del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Fecha del intercambio = Datos actualizados  
  
-   Id. de control del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Estado de confirmación del intercambio = \< esperado o no aplicable\>. Si la confirmación técnica está configurada o tiene un valor asignado en el intercambio de entrada, el estado es Esperado. En caso contrario, el estado es No aplicable.  
  
-   Id. de Control de confirmación del intercambio = \<sin valor\>  
  
-   Fecha de confirmación del intercambio = \<sin valor\>  
  
-   Hora de confirmación del intercambio = \<sin valor\>  
  
-   Código de confirmación/acción = \<sin valor\>  
  
-   Código de nota de confirmación = \<sin valor\>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-technical-acknowledgment-generated-in-response-to-inbound-interchanges"></a>Datos actualizados por la canalización de envío correspondientes a cada confirmación técnica generada en respuesta a intercambios de entrada  
 Para cada confirmación técnica que envía la canalización de envío, se actualiza la entrada del informe de estado correspondiente al intercambio recibido correlacionado. Los sobres de intercambio que la canalización de envío crea serán el origen de los datos.  
  
 El ensamblador EDI localiza los registros en el almacén de datos mediante los datos que figuran en los segmentos UCI y TA1 de la confirmación entrante, como se muestra a continuación:  
  
|Campos en la confirmación|Campos en el almacén de datos|Comentario|  
|-------------------|--------------------------|-------------|  
|Id. del remitente del intercambio|Receptor del intercambio|-|  
|Id. del receptor del intercambio|Remitente del intercambio|-|  
|-|Fecha de intercambio|-|  
|Número de Control de intercambio|Id. de control de intercambio|-|  
|-|Dirección de intercambio = Recepción|Necesario en el escenario de intercambio conservado para la unicidad|  
|Tipo de registro|Estado de confirmación del intercambio|-|  
  
 Los datos almacenados incluyen:  
  
-   Tipo de registro = Estado de confirmación del intercambio  
  
-   Dirección de confirmación del intercambio = Envío – Datos existentes  
  
-   Estado de confirmación del intercambio = Procesado o Enviado – Datos actualizados  
  
-   Receptor del intercambio = Datos existentes  
  
-   Remitente del intercambio = Datos existentes  
  
-   Fecha del intercambio = Datos existentes  
  
-   Id. de control de intercambio = Datos existentes  
  
-   Id. de control de confirmación del intercambio = Datos actualizados  
  
-   Fecha de confirmación del intercambio = Datos actualizados  
  
-   Hora de confirmación del intercambio = Datos actualizados  
  
-   Código de acción o confirmación = Datos existentes  
  
-   Código de nota de confirmación = Datos existentes  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-generated-in-response-to-an-inbound-interchange"></a>Datos almacenados por la canalización de recepción correspondientes a cada confirmación funcional generada en respuesta a un intercambio de entrada  
 La canalización de envío crea un registro en el almacén de datos de informes de estado para cada confirmación funcional que envía. La canalización de envío crea un registro de cada confirmación funcional enviada (como respuesta a un intercambio recibido) en el almacén de datos de informes de estado. Si no se encuentra ningún grupo en EDIFACT, se creará aún así una confirmación funcional. La entrada del informe de estado de confirmación funcional se rellenará a partir del encabezado o el finalizador del grupo funcional (GS/GE o UNG/UNE). La confirmación técnica es 997 para X12 y el mensaje CONTRL completo para EDIFACT. Los datos almacenados incluyen:  
  
-   Tipo de registro = Estado de la confirmación funcional  
  
-   Dirección de confirmación funcional = Recepción  
  
-   Estado de confirmación funcional = \< esperado o no aplicable\>. Si la ficha de confirmación funcional en PAM está seleccionada, el estado se establecerá como Esperado. En caso contrario, el estado se establecerá como No aplicable.  
  
-   Receptor del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Remitente del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Fecha del intercambio = Datos actualizados  
  
-   Id. de control del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Número de control de grupo = Datos actualizados (necesarios para la correlación. En EDIFACT si no se encuentran segmentos de grupo, el valor de este campo se asigna mediante UNH.1)  
  
-   Código de Id. funcional = Datos actualizados (sin valor en EDIFACT cuando no se encuentra un grupo)  
  
-   Número de conjuntos de transacciones = Datos (en EDIFACT esto se asigna a UNE.1 cuando se encuentran UNG/UNE o a UNZ.1 en caso de que no se encuentren segmentos de grupo)  
  
-   Identificador de Control de intercambio de confirmación funcional = \<sin valor\>  
  
-   Fecha de intercambio de confirmación funcional = \<sin valor\>  
  
-   Hora de intercambio de confirmación funcional = \<sin valor\>  
  
-   Número de conjuntos de transacciones entregados = \<sin valor\>  
  
-   Número de conjuntos de transacciones aceptados = \<sin valor\>  
  
-   Código de confirmación/acción = \<sin valor\>  
  
-   Código de Error de sintaxis/error = \<sin valor\>  
  
-   Adicionales X12 código de Error de confirmación 2 = \<sin valor\>  
  
-   X12 adicionales 3 de código de Error de confirmación = \<sin valor\>  
  
-   X12 adicionales 4 de código de Error de confirmación = \<sin valor\>  
  
-   X12 adicional 5 de código de Error de confirmación = \<sin valor\>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-functional-acknowledgment-generated-in-response-to-inbound-interchanges"></a>Datos actualizados por la canalización de envío correspondientes a cada confirmación funcional generada en respuesta a intercambios de entrada  
 Para cada confirmación funcional que envía la canalización de envío, se actualiza la entrada del informe de estado correspondiente al intercambio recibido correlacionado. Los sobres de intercambio que la canalización de envío crea serán el origen de los datos.  
  
 El ensamblador EDI localiza los registros en el almacén de datos mediante los datos que figuran en los segmentos de intercambio y de encabezado de grupo de la confirmación entrante, como se muestra a continuación:  
  
|Campos en la confirmación|Campos en el almacén de datos|Comentario|  
|-------------------|--------------------------|-------------|  
|Id. del remitente del intercambio|Receptor del intercambio|-|  
|Id. del receptor del intercambio|Remitente del intercambio|-|  
|Fecha de intercambio|Fecha de intercambio|-|  
|Número de Control de intercambio|Id. de control de intercambio|-|  
|Número de control de grupo|Número de control de grupo|Opcional en EDIFACT|  
|-|Dirección de intercambio = Recepción|Necesario en el escenario de intercambio conservado para la unicidad|  
|Tipo de registro|Estado de confirmación funcional|-|  
  
 Los datos almacenados incluyen:  
  
-   Tipo de registro = Estado de la confirmación funcional  
  
-   Dirección de confirmación funcional = Envío – Datos existentes  
  
-   Estado de la confirmación funcional = Enviado/Procesado – Datos actualizados  
  
-   Receptor del intercambio = datos existentes  
  
-   Remitente del intercambio = Datos existentes  
  
-   Fecha del intercambio = Datos existentes  
  
-   Id. de control de intercambio = Datos existentes  
  
-   Número de control de grupo = Datos existentes  
  
-   Código de Id. funcional = Datos existentes  
  
-   Número de conjuntos de transacciones = Datos existentes  
  
-   Id. de control de intercambio de reconocimiento funcional = Datos actualizados  
  
-   Fecha de intercambio de reconocimiento funcional = Datos actualizados  
  
-   Hora de intercambio de confirmación funcional = Datos actualizados  
  
-   Número de conjuntos de transacciones recibidos = Datos existentes  
  
-   Número de conjuntos de transacciones aceptados = Datos existentes  
  
-   Código de acción o confirmación = Datos existentes  
  
-   Código de error de sintaxis/Error = Datos existentes  
  
-   Adicionales X12 código de Error de confirmación 2 = datos existentes  
  
-   Adicionales X12 código de Error 3 de confirmación = datos existentes  
  
-   X12 adicionales 4 de código de Error de confirmación = datos existentes  
  
-   Código de error 5 de confirmación X12 adicional = Datos existentes  
  
## <a name="see-also"></a>Vea también  
 [Cómo se almacenan los datos para informes de estado de AS2 y EDI](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)   
 [Cómo se almacenan los datos correspondientes a mensajes EDI de salida](../core/how-data-is-stored-for-outbound-edi-messages.md)