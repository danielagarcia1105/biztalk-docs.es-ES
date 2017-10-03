---
title: "Cómo se almacenan los datos para los mensajes EDI salientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6e576fc-37fd-417d-ae68-607a0a8bcc0a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 278ab244ab48d2e11a84e99f0af2e02948ff961a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-data-is-stored-for-outbound-edi-messages"></a>Cómo se almacenan los datos correspondientes a mensajes EDI de salida
Para generar una entrada del informe de estado correspondiente a un intercambio de salida, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lleva a cabo lo siguiente:  
  
1.  Cuando el XML del mensaje de salida se envía a la canalización de envío EDI, ésta crea una entrada en el almacén de datos de informes de estado con los valores siguientes:  
  
    -   La entrada Estado de intercambio se establece como Procesado.  
  
    -   La entrada de estado Confirmación de intercambio (una por intercambio) se establece como Esperado.  
  
    -   Las entradas Estado de confirmación funcional (una por grupo en X12, una para todos los grupos en EDIFACT) se establecen como Esperado.  
  
2.  Una vez que el mensaje EDI se ha enviado al socio comercial y éste ha devuelto la confirmación, la canalización de recepción EDI que recibe la confirmación actualiza las entradas de estado del intercambio, estado de confirmación de intercambio y estado de confirmación funcional a los valores Aceptado/Parcialmente aceptado/Rechazado, según corresponda.  
  
## <a name="data-stored-by-the-send-pipeline-for-outbound-interchanges"></a>Datos almacenados por la canalización de envío correspondientes a los intercambios de salida  
 La canalización de envío crea un registro en el almacén de datos de informes de estado para cada intercambio que envía. La mayoría de los datos necesarios para la entrada están disponibles a partir de los segmentos de encabezado y finalizador del intercambio (ISA/IEA o UNB/UNZ). Otros datos están disponibles a partir de las propiedades del puerto de envío. Los datos almacenados incluyen:  
  
-   Tipo de registro = Estado de intercambio  
  
-   Dirección de intercambio = Datos actualizados = Envío  
  
-   Receptor del intercambio = Datos actualizados  
  
-   Remitente del intercambio = Datos actualizados  
  
-   Fecha del intercambio = Datos actualizados  
  
-   Hora del intercambio = Datos actualizados  
  
-   Id. de control de intercambio = Datos actualizados  
  
-   Estado de intercambio = Procesado/enviado. El estado Procesado indica que la canalización de envío ha procesado correctamente el intercambio y lo ha transferido al adaptador de envío para su entrega.  
  
-   Número de control de intercambio (grupos y mensajes en X12 respectivamente) = Datos  
  
-   Id. del puerto de intercambio = Datos  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a>Datos almacenados por la canalización de recepción correspondientes a cada confirmación técnica recibida en respuesta a un intercambio de salida  
 La canalización de recepción crea un registro en el almacén de datos de informes de estado para cada confirmación técnica que recibe. La canalización de recepción crea un registro de cada intercambio recibido en el almacén de datos de informe de estado. crea una entrada del informe de estado de confirmación técnica en el almacén de datos para cada confirmación técnica recibida como respuesta a un intercambio enviado a un socio comercial. La confirmación técnica es TA1 para X12 y el mensaje CONTRL con solo el segmento UCI para EDIFACT. Los datos almacenados incluyen:  
  
-   Tipo de registro = Estado de confirmación del intercambio  
  
-   Dirección de confirmación del intercambio = Envío – Datos actualizados  
  
-   Receptor del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Remitente del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Fecha del intercambio = Datos actualizados (necesarios para la correlación X12)  
  
-   Id. de control del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Estado de confirmación del intercambio = generado o no es aplicable \<consultar Nota 0 >-Actualizar datos  
  
-   Id. de control de confirmación del intercambio= Sin valor – se aplicará en el envío  
  
-   Fecha de confirmación del intercambio = Sin valor – se aplicará en el envío  
  
-   Hora de confirmación del intercambio = Sin valor – se aplicará en el envío  
  
-   Código de confirmación/acción = datos actualizados \<consultar Nota 1 > (de X12-TA104 o EDIFACT-UCI4) *  
  
-   Código de nota de confirmación = datos actualizados \<consultar Nota 2 > (de X12-TA105, no es aplicable a EDIFACT) *  
  
 Se utilizan los siguientes códigos de confirmación/acción:  
  
|Datos en código de confirmación/acción|Descripción del error para informes|Comentario (aplicabilidad)|  
|------------------------------|-------------------------------------|-------------------------------|  
|Un|Aceptado|X12|  
|E|Aceptado con errores registrados|X12|  
|P|Parcialmente aceptado|X12|  
|L|Rechazado|X12|  
|4|Rechazado|EDIFACT|  
|8|Aceptado/Parcialmente aceptado|EDIFACT|  
  
 Se utilizan los siguientes códigos de nota de confirmación:  
  
|Datos en código de nota de confirmación (en X12)|Description|  
|--------------------------------------|-----------------|  
|000|Success|  
|001|Falta de coincidencia del número de control de intercambio.|  
|002|Estándar no admitido.|  
|003|Versión de los controles incompatible.|  
|004|El terminador de segmento no es válido.|  
|005|Calificador de Id. de intercambio no válido para el remitente.|  
|006|Id. de intercambio no válido para el remitente.|  
|007|Calificador de Id. de intercambio no válido para el receptor.|  
|008|Id. de receptor de intercambio no válido.|  
|009|Id. de receptor de intercambio desconocido.|  
|010|Valor del calificador de información de autorización no válido|  
|011|Valor de la información de autorización no válido|  
|012|Valor del calificador de información de seguridad no válido.|  
|013|Valor de información de seguridad no válido.|  
|014|Valor de fecha de intercambio no válido|  
|015|Valor de hora de intercambio no válido|  
|016|Valor de identificador de estándares de intercambio no válido|  
|017|Valor de Id. de versión de intercambio no válido.|  
|018|Valor de número de Control de intercambio no válido|  
|019|Valor solicitado de confirmación no válido.|  
|020|Valor del indicador de prueba no válido.|  
|021|Valor de número de grupos incluidos no válido.|  
|022|Estructura de control no válida.|  
|023|Fin de archivo incorrecto.|  
|024|Contenido de intercambio no válido.|  
|025|Número de control de intercambio duplicado.|  
|026|Separador de elemento de datos no válido.|  
|027|Separador de elemento de componente no válido.|  
|028|Fecha de entrega no válida en solicitud de entrega aplazada.|  
|029|Hora de entrega no válida en solicitud de entrega aplazada.|  
|030|Código de tiempo de entrega no válido en la solicitud de entrega aplazada.|  
|031|Calificación de servicio no válida.|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-technical-acknowledgment-received-in-response-to-an-outbound-interchange"></a>Datos actualizados por la canalización de recepción correspondientes a cada confirmación técnica recibida en respuesta a un intercambio de salida  
 Para cada confirmación técnica que recibe la canalización de recepción, se actualiza la entrada del informe de estado correspondiente al intercambio enviado correlacionado.  
  
 El Desensamblador EDI localiza los registros en el almacén de datos mediante los datos que figuran en los segmentos UCI y TA1 de la confirmación entrante, como se muestra a continuación:  
  
|Campos en la confirmación|Campos en el almacén de datos|Comentario|  
|-------------------|--------------------------|-------------|  
|Id. del remitente del intercambio|Receptor del intercambio|-|  
|Id. del receptor del intercambio|Remitente del intercambio|-|  
|-|Fecha de intercambio|-|  
|Número de Control de intercambio|Id. de control de intercambio|-|  
|-|Dirección de intercambio = Envío|Necesario en el escenario de lote conservado para la unicidad|  
|Tipo de registro|Estado del intercambio y estado de la confirmación del intercambio|-|  
  
 Los datos almacenados incluyen:  
  
-   Dirección de confirmación del intercambio = Recepción – Datos existentes  
  
-   Estado de la confirmación y del intercambio = Recibido  
  
-   Receptor del intercambio = Datos existentes  
  
-   Remitente del intercambio = Datos existentes  
  
-   Fecha del intercambio = Datos existentes  
  
-   Id. de control de intercambio = Datos existentes  
  
-   Id. de control de confirmación del intercambio = Datos actualizados  
  
-   Fecha de confirmación del intercambio = Datos actualizados  
  
-   Hora de confirmación del intercambio = Datos actualizados  
  
-   Código de confirmación/acción = datos actualizados (de X12-TA104 o EDIFACT-UCI4) * \<consultar Nota 1 >  
  
-   Código de nota de confirmación 2 = datos actualizados (de X12-TA105 y sin valor para EDIFACT) * \<consultar Nota 2 >  
  
 Los datos de confirmación X12:TA1-104 o EDIFACT UCI4 se asignarán del modo siguiente:  
  
|Datos en código de confirmación/acción|Asignado para informes de estado|Comentario|  
|------------------------------|---------------------------------|-------------|  
|Un|Aceptado|X12|  
|P|Parcialmente aceptado|X12|  
|R, M, W, X|Rechazado|X12|  
|E|Aceptado con errores|X12|  
|4|Rechazado|EDIFACT|  
|7, 8|Aceptado/Parcialmente aceptado|EDIFACT|  
  
 Se utilizan los siguientes códigos de nota de confirmación:  
  
|Datos en código de nota de confirmación (en X12)|Asignado para informes de estado|  
|--------------------------------------|---------------------------------|  
|000|Success|  
|001|Falta de coincidencia del número de control de intercambio.|  
|002|Estándar no admitido.|  
|003|Versión de los controles incompatible.|  
|004|El terminador de segmento no es válido.|  
|005|Calificador de Id. de intercambio no válido para el remitente.|  
|006|Id. de intercambio no válido para el remitente.|  
|007|Calificador de Id. de intercambio no válido para el receptor.|  
|008|Id. de receptor de intercambio no válido.|  
|009|Id. de receptor de intercambio desconocido.|  
|010|Valor del calificador de información de autorización no válido|  
|011|Valor de la información de autorización no válido|  
|012|Valor del calificador de información de seguridad no válido.|  
|013|Valor de información de seguridad no válido.|  
|014|Valor de fecha de intercambio no válido|  
|015|Valor de hora de intercambio no válido|  
|016|Valor de identificador de estándares de intercambio no válido|  
|017|Valor de Id. de versión de intercambio no válido.|  
|018|Valor de número de Control de intercambio no válido|  
|019|Valor solicitado de confirmación no válido.|  
|020|Valor del indicador de prueba no válido.|  
|021|Valor de número de grupos incluidos no válido.|  
|022|Estructura de control no válida.|  
|023|Fin de archivo incorrecto.|  
|024|Contenido de intercambio no válido.|  
|025|Número de control de intercambio duplicado.|  
|026|Separador de elemento de datos no válido.|  
|027|Separador de elemento de componente no válido.|  
|028|Fecha de entrega no válida en solicitud de entrega aplazada.|  
|029|Hora de entrega no válida en solicitud de entrega aplazada.|  
|030|Código de tiempo de entrega no válido en la solicitud de entrega aplazada.|  
|031|Calificación de servicio no válida.|  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outbound-interchanges"></a>Datos almacenados por la canalización de recepción correspondientes a cada confirmación funcional recibida en respuesta a intercambios de salida  
 La canalización de recepción crea un registro en el almacén de datos de informes de estado para cada confirmación funcional que recibe.  La confirmación técnica es 997 para X12 y el mensaje CONTRL completo para EDIFACT. Se creará una entrada por grupo. Durante su creación, se usan los datos procedentes del intercambio y los encabezados de grupo. Los datos almacenados incluyen:  
  
-   Tipo de registro = Estado de la confirmación funcional  
  
-   Dirección de confirmación funcional = Envío  
  
-   Estado de confirmación funcional = \<generado o no está disponible, consulte la nota 1 >  
  
-   Receptor del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Remitente del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Fecha del intercambio = Datos actualizados (necesarios para la correlación X12)  
  
-   Id. de control del intercambio = Datos actualizados (necesarios para la correlación)  
  
-   Número de control de grupo = Datos actualizados ("opcional para EDIFACT" y necesario para la correlación X12)  
  
-   Código de Id. funcional = Datos actualizados (GS01/UNG01)  
  
-   Número de conjuntos de transacciones = Datos actualizados (UNE1/UNZ1)  
  
-   Id. de control de intercambio de reconocimiento funcional = Sin valor – se aplicará en el envío  
  
-   Fecha de intercambio de reconocimiento funcional = Sin valor – se aplicará en el envío  
  
-   Hora de intercambio de confirmación funcional = Sin valor – se aplicará en el envío  
  
-   Número de conjuntos de transacciones recibidos = Datos actualizados (X12-AK903 y calculado por el motor para la codificación EDIFACT)  
  
-   Número de conjuntos de transacciones aceptados = Datos actualizados (X12-AK904 y calculado por el motor para la codificación EDIFACT)  
  
-   Código de confirmación/acción = datos actualizados \<consultar Nota 2 > (de X12-AK901 o EDIFACT-UCI4) *  
  
-   Código de error y de error de sintaxis = Datos actualizados (X12-AK905, EDIFACT UCI5) Nota 3  
  
-   Código de error 2 de confirmación X12 adicional = Datos actualizados (X12-AK906)  
  
-   Código de error 3 de confirmación X12 adicional = Datos actualizados (X12-AK907)  
  
-   Código de error 4 de confirmación X12 adicional = Datos actualizados (X12-AK908)  
  
-   Código de error 5 de confirmación X12 adicional = Datos actualizados (X12-AK909)  
  
 Se utilizarán los siguientes códigos de confirmación/acción:  
  
|Datos en código de confirmación/acción|Descripción del error para informes|Comentario (aplicabilidad)|  
|------------------------------|-------------------------------------|-------------------------------|  
|Un|Aceptado|X12|  
|E|Aceptado con errores|X12|  
|P|Parcialmente aceptado|X12|  
|L|Rechazado|X12|  
|4|Rechazado|EDIFACT|  
|7|Aceptado/Parcialmente aceptado|EDIFACT|  
  
 Para EDIFACT, se usarán los siguientes códigos de error y de error de sintaxis:  
  
|Datos en el código de Error de sintaxis/Error<br /><br /> (aplicable a EDIFACT)|Descripción del error para el informe|  
|--------------------------------------------------------------------|-------------------------------------|  
|2|Nivel o versión de sintaxis no admitidos|  
|7|El destinatario del intercambio no es el destinatario real|  
|12|Valor no válido|  
|13|Missing|  
|14|Valor no admitido en esta posición|  
|15|No admitido en esta posición|  
|16|Demasiados constituyentes|  
|17|No hay acuerdo|  
|18|Error no especificado|  
|19|Notación decimal no válida|  
|20|Carácter no válido como carácter de servicio|  
|21|Carácter(es) no válido(s)|  
|22|Caracteres de servicio no válidos|  
|23|Remitente de intercambio desconocido|  
|24|Demasiado antiguo|  
|25|Indicador de prueba no admitido|  
|26|Duplicado detectado|  
|27|Función de seguridad no admitida|  
|28|Las referencias no coinciden|  
|29|La cuenta de control no coincide con el número de instancias recibidas|  
|30|Grupos y mensajes o paquetes mezclados|  
|31|Más de un tipo de mensaje en el grupo|  
|32|Nivel inferior vacío|  
|33|Suceso no válido fuera del mensaje, paquete o grupo|  
|34|Indicador de anidamiento no admitido|  
|35|Demasiados elementos de datos o repeticiones de segmentos|  
|36|Demasiadas repeticiones de grupos de segmentos|  
|37|Tipo de carácter(es) no válido(s)|  
|38|Dígito ausente delante de signo decimal|  
|39|Elemento de datos demasiado largo.|  
|40|Elemento de datos demasiado corto.|  
|41|Error de red de comunicación permanente|  
|42|Error de red de comunicación temporal|  
|43|Destinatario de intercambio desconocido|  
|45|Separador final|  
|46|Juego de caracteres no admitido|  
|47|Funcionalidad de sobre no admitida|  
|48|Infracción de condición de dependencia|  
|70|Conjunto de transacciones falta o identificador de conjunto de transacción no válido|  
|71|Número de control de grupo o conjunto de transacciones no coincidente|  
|72|Id. de segmento no reconocido.|  
|73|XML no está en la posición correcta|  
|74|Repeticiones insuficientes de grupos de segmentos|  
|75|Repeticiones insuficientes de segmento|  
|76|No se encontraron suficientes datos de elementos.|  
  
 Para X12, se usarán los siguientes códigos de error y de error de sintaxis:  
  
|Datos en el código de Error de sintaxis/Error<br /><br /> (aplicable a X12)|Descripción del error para el informe|  
|----------------------------------------------------------------|-------------------------------------|  
|1|Grupo funcional no compatible|  
|2|Versión de grupo funcional no compatible|  
|3|Falta el finalizador del grupo funcional.|  
|4|El número de control de grupo del encabezado y el finalizador del grupo funcional no coinciden.|  
|5|El número de conjuntos de transacciones incluidos no coincide con el recuento real.|  
|6-26|Otros errores de validación no admitidos|  
  
## <a name="data-updated-by-the-receive-pipeline-for-each-functional-acknowledgment-received-in-response-to-outgoing-interchanges"></a>Datos actualizados por la canalización de recepción correspondientes a cada confirmación funcional recibida en respuesta a intercambios de salida  
 Para cada confirmación funcional que recibe la canalización de recepción, se actualiza la entrada del informe de estado correspondiente al intercambio enviado correlacionado.  
  
 El Desensamblador EDI localiza los registros en el almacén de datos mediante los datos que figuran en los segmentos de intercambio y de encabezado de grupo de la confirmación entrante, como se muestra a continuación:  
  
|Campos en la confirmación|Campos en el almacén de datos|Comentario|  
|-------------------|--------------------------|-------------|  
|Id. del remitente del intercambio|Receptor del intercambio|Aplicable a X12 y EDIFACT|  
|Id. del receptor del intercambio|Remitente del intercambio|Aplicable a X12 y EDIFACT|  
|-|Fecha de intercambio|-|  
|Número de Control de intercambio|Id. de control de intercambio|Aplicable únicamente a EDIFACT|  
|Número de control de grupo|Número de control de grupo|Aplicable únicamente a X12|  
|-|Dirección de intercambio = Envío|Necesario en el escenario BIBO para la unicidad|  
|Tipo de registro|Estado de confirmación funcional|Aplicable a X12 y EDIFACT|  
  
 Los datos almacenados incluyen:  
  
-   Tipo de registro = Estado de la confirmación funcional  
  
-   Dirección de confirmación funcional = Recepción  
  
-   Estado de confirmación funcional = Datos actualizados como Recibidos  
  
-   Receptor del intercambio = Datos existentes  
  
-   Remitente del intercambio = Datos existentes  
  
-   Fecha del intercambio = Datos existentes  
  
-   Id. de control de intercambio = Datos existentes  
  
-   Número de control de grupo = Datos existentes  
  
-   Código de Id. funcional = Datos existentes  
  
-   Número de conjuntos de transacciones = Datos existentes  
  
-   Id. de control de intercambio de reconocimiento funcional = Datos actualizados  
  
-   Fecha de intercambio de reconocimiento funcional = Datos actualizados  
  
-   Hora de intercambio de confirmación funcional = Datos actualizados  
  
-   Número de conjuntos de transacciones entregados = Datos actualizados (X12-AK903 y no aplicable a EDIFACT)  
  
-   Número de conjuntos de transacciones aceptados = Datos actualizados (X12-AK904 y no aplicable a EDIFACT)  
  
-   Código de confirmación/acción = Datos actualizados (X12 AK901 y UCI4) Consultar nota 1  
  
-   Código de error y de error de sintaxis = (X12 AK905 y UCI5) Consultar nota 2  
  
-   Código de error 2 de confirmación X12 adicional = Datos actualizados (X12-AK906)  
  
-   Código de error 3 de confirmación X12 adicional = Datos actualizados (X12-AK907)  
  
-   Código de error 4 de confirmación X12 adicional = Datos actualizados (X12-AK908)  
  
-   Código de error 5 de confirmación X12 adicional = Datos actualizados (X12-AK909)  
  
 Se utilizarán los siguientes códigos de confirmación/acción:  
  
|Datos en código de confirmación/acción|Asignado para informes de estado|Comentario|  
|------------------------------|---------------------------------|-------------|  
|Un|Aceptado|X12|  
|P|Parcialmente aceptado|X12|  
|R, M, W, X|Rechazado|X12|  
|E|Aceptado con errores|X12|  
|4|Rechazado|EDIFACT|  
|7, 8|Aceptado/Parcialmente aceptado|EDIFACT|  
  
 Para EDIFACT, se usarán los siguientes códigos de error y de error de sintaxis:  
  
|Datos del código de error y de error de sintaxis<br /><br /> (aplicable a EDIFACT)|Descripción del error para el informe|  
|-------------------------------------------------------------------|-------------------------------------|  
|2|Nivel o versión de sintaxis no admitidos|  
|7|El destinatario del intercambio no es el destinatario real|  
|12|Valor no válido|  
|13|Missing|  
|14|Valor no admitido en esta posición|  
|15|No admitido en esta posición|  
|16|Demasiados constituyentes|  
|17|No hay acuerdo|  
|18|Error no especificado|  
|19|Notación decimal no válida|  
|20|Carácter no válido como carácter de servicio|  
|21|Carácter(es) no válido(s)|  
|22|Caracteres de servicio no válidos|  
|23|Remitente de intercambio desconocido|  
|24|Demasiado antiguo|  
|25|Indicador de prueba no admitido|  
|26|Duplicado detectado|  
|27|Función de seguridad no admitida|  
|28|Las referencias no coinciden|  
|29|La cuenta de control no coincide con el número de instancias recibidas|  
|30|Grupos y mensajes o paquetes mezclados|  
|31|Más de un tipo de mensaje en el grupo|  
|32|Nivel inferior vacío|  
|33|Suceso no válido fuera del mensaje, paquete o grupo|  
|34|Indicador de anidamiento no admitido|  
|35|Demasiados elementos de datos o repeticiones de segmentos|  
|36|Demasiadas repeticiones de grupos de segmentos|  
|37|Tipo de carácter(es) no válido(s)|  
|38|Dígito ausente delante de signo decimal|  
|39|Elemento de datos demasiado largo.|  
|40|Elemento de datos demasiado corto.|  
|41|Error de red de comunicación permanente|  
|42|Error de red de comunicación temporal|  
|43|Destinatario de intercambio desconocido|  
|45|Separador final|  
|46|Juego de caracteres no admitido|  
|47|Funcionalidad de sobre no admitida|  
|48|Infracción de condición de dependencia|  
|70|Conjunto de transacciones falta o identificador de conjunto de transacción no válido|  
|71|Número de control de grupo o conjunto de transacciones no coincidente|  
|72|Id. de segmento no reconocido.|  
|73|XML no está en la posición correcta|  
|74|Repeticiones insuficientes de grupos de segmentos|  
|75|Repeticiones insuficientes de segmento|  
|76|No se encontraron suficientes datos de elementos.|  
  
 Para X12, se usarán los siguientes códigos de error y de error de sintaxis:  
  
|Datos en el código de Error de sintaxis/Error<br /><br /> (aplicable a X12)|Descripción del error para el informe|  
|----------------------------------------------------------------|-------------------------------------|  
|1|Grupo funcional no compatible|  
|2|Versión de grupo funcional no compatible|  
|3|Falta el finalizador del grupo funcional.|  
|4|El número de control de grupo del encabezado y el finalizador del grupo funcional no coinciden.|  
|5|El número de conjuntos de transacciones incluidos no coincide con el recuento real.|  
|6-26|Otros errores de validación no admitidos|  
  
## <a name="see-also"></a>Vea también  
 [Cómo se almacenan los datos para informes de estado de AS2 y EDI](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)   
 [Cómo se almacenan los datos para los mensajes EDI entrantes](../core/how-data-is-stored-for-inbound-edi-messages.md)