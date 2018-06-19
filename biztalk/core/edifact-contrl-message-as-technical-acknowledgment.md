---
title: Mensaje de CONTRL de EDIFACT como confirmación técnica | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f2a7564-dbd3-48d0-b0a6-a77a0560459f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8376e3249a102486c1bef4d92a7512c8aa29636c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242516"
---
# <a name="edifact-contrl-message-as-technical-acknowledgment"></a>Mensaje CONTRL de EDIFACT como confirmación técnica
Si ha seleccionado generar una confirmación técnica en la configuración de perfil de negocio o acuerdo entre socios comerciales (o acuerdo de reserva si no se ha definido ningún acuerdo entre los dos perfiles de negocio), o bien si el campo UNB9 del mensaje se configura en "2", se generará un mensaje CONTRL como confirmación técnica. Esta confirmación informa sobre los resultados de la recepción del intercambio.  
  
 La confirmación técnica CONTRL incluye los siguientes segmentos:  
  
-   Encabezado de mensaje UNH (obligatorio)  
  
-   Respuesta de intercambio UCI que identifica el intercambio del asunto e indica la naturaleza de la recepción del intercambio (obligatorio). El segmento UCI presenta una repetición máxima de 1. Como resultado, informa sobre el primer error que se detecta en uno de los segmentos de control.  
  
-   Finalizador de mensaje UNT (obligatorio).  
  
 Se informa de un error en el elemento de datos UCI5, "Código de error de sintaxis". En los intercambios con codificación EDIFACT no existe el estado "aceptado con errores", como ocurre en los intercambios codificados con X12.  
  
> [!NOTE]
>  Una recepción CONTRL (confirmación técnica de EDIFACT) informa de un estado “Rechazado” sólo cuando el mensaje EDIFACT entrante es un duplicado o hay errores en el sobre (por ejemplo, existe un problema con el juego de caracteres). EDIFACT no informa de un estado de intercambio “Aceptado con errores” en la confirmación técnica CONTRL, como hace X12 en el campo TA104 de una confirmación TA1. Si se acepta parte del mensaje EDIFACT, la confirmación técnica CONTRL informará de un estado “Aceptado”. En algunos escenarios, se rechazará parte del mensaje, pero la confirmación CONTRL seguirá informando de un estado “Aceptado”. En tales escenarios, el elemento UCI5 puede informar del error.  
  
 La confirmación técnica CONTRL incluye los siguientes elementos de datos:  
  
|Elementos Data|Nombre|Uso|  
|------------------|----------|-----------|  
|UNH1|Número de referencia de mensaje|-|  
|UNH2|Subcomponentes del identificador de mensaje|Los subcomponentes son:<br /><br /> -1 = CONTRL<br /><br /> - 2 = 4<br /><br /> - 3 = 1<br /><br /> -4 = QUITAR|  
|UCI1|Número de control de intercambio.|Asignado desde el campo UNB5 del mensaje recibido.|  
|UCI2|Remitente de intercambio|Asignado desde el campo UNB2 del mensaje recibido. El primer subcomponente (identificación) es obligatorio. El segundo subcomponente (calificador de código) y el tercero (dirección de enrutamiento inverso) son opcionales.|  
|UCI3|Destinatario de intercambio|Asignado desde el campo UNB3 del mensaje recibido. El primer subcomponente (identificación) es obligatorio. El segundo subcomponente (calificador de código) es opcional.|  
|UCI4|Código de acción|Los códigos de acción son:<br /><br /> -8 si se acepta el intercambio<br /><br /> -se rechazan 7 si se acepta el intercambio, pero algunos conjuntos de transacciones<br /><br /> -4 si se rechaza el intercambio debido a un error en el segmento UNA o UNB<br /><br /> Es un elemento de datos obligatorio.|  
|UCI5|Código de error de sintaxis|Identifica la condición de error (si la hay). Para obtener más información, consulte [códigos de Error de confirmación de CONTRL de EDIFACT](../core/edifact-contrl-acknowledgment-error-codes.md).<br /><br /> Este elemento de datos presenta una opcionalidad condicional.|  
|UCI6|Etiqueta de segmento de servicio|Identifica el segmento que presenta la condición de error identificada en el elemento de datos UCI.5.<br /><br /> Este elemento de datos presenta una opcionalidad condicional.|  
|UCI7|Identificación de elementos de datos|Identifica los elementos de datos que presentan la condición de error identificada en el elemento de datos UCI.5. Los subcomponentes de UCI7 son:<br /><br /> -Posición del elemento de datos erróneo en segmento (obligatorio)<br /><br /> -Posición del elemento de datos de componentes erróneo en segmento (opcionalidad condicional)<br /><br /> -Aparición del elemento de datos erróneo en segmento (opcionalidad condicional)|  
|UCI8|-|-|  
|UNT1|Número de segmentos|-|  
|UNT2|Número de referencia de mensaje|-|