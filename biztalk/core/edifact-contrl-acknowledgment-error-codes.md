---
title: Códigos de Error de confirmación de CONTRL de EDIFACT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c5ab75-d83d-4c3e-a054-8fe079219b61
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee3aeff19069de5a10d7303b8b38d32a3a4ed3b7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009221"
---
# <a name="edifact-contrl-acknowledgment-error-codes"></a>Códigos de error de confirmación CONTRL de EDIFACT
En este tema se enumeran los códigos de error usados dentro de los segmentos de una confirmación CONTRL de EDIFACT. Para obtener más información acerca de estos segmentos, vea [confirmación CONTRL de EDIFACT](../core/edifact-contrl-acknowledgment.md).  
  
 Estos errores se aplican en el nivel de datos, mensajes, grupos e intercambios. Al detectar un error admitido, se rechaza el conjunto de transacciones, el grupo o el intercambio completo. En los intercambios con codificación EDIFACT no existe el estado "aceptado con errores".  
  
 **Códigos de Error EDIFACT estándar**  
  
 La tabla siguiente muestra los códigos de error que se utilizan en el campo UCI5 de la confirmación CONTRL de EDIFACT. Esta tabla indica qué códigos de error especificados por la especificación EDIFACT se admiten en BizTalk Server EDI y AS2 y que no son compatibles.  
  
|Código de error|Condición|Causa|¿Admitido?|  
|----------------|---------------|-----------|----------------|  
|2|Nivel o versión de sintaxis no admitidos|Notificación de que el destinatario no admite el nivel o la versión de sintaxis.|No|  
|7|El destinatario del intercambio no es el destinatario real|Notificación de que el destinatario del intercambio (S003) difiere del destinatario real.|No|  
|12|Valor no válido|Notificación de que el valor de un elemento de datos independiente, de un elemento de datos compuesto o de un elemento de datos de componentes no cumple las especificaciones relevantes del valor.|Sí|  
|13|Missing|Notificación de que falta un segmento de usuario o servicio obligatorio (o necesario), un elemento de datos, un elemento de datos compuesto o un elemento de datos de componentes.|Sí|  
|14|Valor no admitido en esta posición|Notificación de que el destinatario no admite el empleo del valor específico de un elemento de datos independiente, de un elemento de datos compuesto o de un elemento de datos de componentes identificado en la posición en la que se utiliza. El valor puede ser válido según las especificaciones relevantes, y puede admitirse si se utiliza en otra posición.|No|  
|15|No admitido en esta posición|Notificación de que el destinatario no admite el empleo del tipo de segmento, del tipo de elemento de datos independiente, del tipo de elemento de datos compuesto o del tipo de elemento de datos de componentes en la posición identificada.|Sí|  
|16|Demasiados constituyentes|Notificación de que el segmento identificado contiene demasiados elementos de datos o de que el elemento de datos compuesto identificado contiene demasiados elementos de datos de componentes.|Sí|  
|17|No hay acuerdo|No existe acuerdo que permita la recepción de un intercambio, grupo, mensaje o paquete con el valor del elemento de datos independiente, del elemento de datos compuesto o del elemento de datos de componentes identificado.|No|  
|18|Error no especificado|Notificación de que se ha identificado un error, pero no se ha determinado su naturaleza.|No|  
|19|Notación decimal no válida|Notificación de que el carácter indicado como notación decimal en UNA no es válido, o la notación decimal utilizada en un elemento de datos no es coherente con la indicada en UNA.|No|  
|20|Carácter no válido como carácter de servicio|Notificación de que un carácter recomendado en UNA no es válido como carácter de servicio.|No|  
|21|Carácter(es) no válido(s)|Notificación de que uno o varios de los caracteres utilizados en el intercambio no son válidos, como se muestra en el identificador sintáctico indicado en el segmento UNB. El carácter no válido forma parte del nivel al que hace referencia o seguida inmediatamente después de la parte identificada del intercambio.|Sí|  
|22|Caracteres de servicio no válidos|Notificación de que los caracteres de servicio utilizados en el intercambio no son caracteres de servicio válidos, como se recomienda en el segmento UNA, o bien no se trata de uno de los caracteres de servicio predeterminados. Si el código se emplea en el segmento UCS o UCD, el carácter no válido aparece inmediatamente después de la parte identificada del intercambio.|No|  
|23|Remitente de intercambio desconocido|Notificación de que el remitente del intercambio (S002) es desconocido.|No|  
|24|Demasiado antiguo|Notificación de que el grupo o el intercambio recibidos son más antiguos que un límite especificado en IA o determinado por el destinatario.|No|  
|25|Indicador de prueba no admitido|Notificación de que el procesamiento de prueba no puede efectuarse para el intercambio, grupo, mensaje o paquete identificado.|No|  
|26|Duplicado detectado|Notificación de que se ha detectado un posible duplicado de un intercambio, grupo, mensaje o paquete recibido con anterioridad. Puede que se haya rechazado la transmisión anterior.|Sí|  
|27|Función de seguridad no admitida|Notificación de que no se admite una función de seguridad relacionada con el elemento de datos o el nivel al que se hace referencia.|No|  
|28|Las referencias no coinciden|Notificación de que la referencia de control del segmento UNB, UNG, UNH, UNO, USH o USD no coincide con la referencia de control del segmento UNZ, UNE, UNT, UNP, UST o USU, respectivamente.|No|  
|29|La cuenta de control no coincide con el número de instancias recibidas|Notificación de que el número de grupos, mensajes o segmentos no coincide con el número proporcionado en el segmento UNZ, UNE, UNT o UST; o bien la longitud de un objeto o de un conjunto de datos cifrado no sea igual a la incluida en el segmento UNO, UNP, USD o USU.|Sí|  
|30|Grupos y mensajes o paquetes mezclados|Notificación de que se han mezclado los grupos y los mensajes o paquetes exteriores a los grupos en el intercambio.|No|  
|31|Más de un tipo de mensaje en el grupo|Notificación de que existen distintos tipos de mensaje en un grupo funcional.|Sí|  
|32|Nivel inferior vacío|Notificación de que el intercambio no contiene mensajes, paquetes o grupos, o bien que un grupo no contiene mensajes o paquetes.|No|  
|33|Suceso no válido fuera del mensaje, paquete o grupo|Notificación de que el intercambio contiene un segmento o elemento de datos no válido entre mensajes, paquetes o grupos. El rechazo se comunica en el nivel superior.|Sí|  
|34|Indicador de anidamiento no admitido|Notificación de que se ha utilizado en un mensaje un anidamiento explícito que no debía de usarse.|No|  
|35|Demasiados elementos de datos o repeticiones de segmentos|Notificación de que un elemento de datos independiente, un elemento de datos compuesto o un segmento se repite en demasiadas ocasiones.|Sí|  
|36|Demasiadas repeticiones de grupos de segmentos|Notificación de que se ha repetido demasiado un grupo de segmentos.|Sí|  
|37|Tipo de carácter(es) no válido(s)|Notificación de que uno o varios caracteres numéricos se utilizan en un elemento de datos (de componentes) alfabético o uno o varios caracteres alfabéticos se utilizan en un elemento de datos (de componentes) numérico.|Sí|  
|38|Dígito ausente delante de signo decimal|Notificación de que un signo decimal no está precedido de uno o varios dígitos.|Sí|  
|39|Elemento de datos demasiado largo.|Notificación de que la longitud del elemento de datos recibido supera la longitud máxima especificada en la descripción de elementos de datos.|Sí|  
|40|Elemento de datos demasiado corto.|Notificación de que la longitud del elemento de datos recibido es inferior a la longitud mínima especificada en la descripción de elementos de datos.|Sí|  
|41|Error de red de comunicación permanente|Notificación de que la red de comunicación empleada para la transferencia del intercambio ha informado de la existencia de un error permanente. La retransmisión de un intercambio idéntico con los mismos parámetros no se efectuará correctamente en el nivel de red.|No|  
|42|Error de red de comunicación temporal|Notificación de que la red de comunicación empleada para la transferencia del intercambio ha informado de la existencia de un error temporal. Puede que las retransmisiones de un intercambio idéntico se efectúen correctamente.|No|  
|43|Destinatario de intercambio desconocido|Notificación de que el destinatario del intercambio no es conocido para un proveedor de red.|No|  
|45|Separador final|Notificación que advierte de uno de los siguientes escenarios:<br /><br /> -El último carácter antes de que el terminador de segmento es un separador de elementos de datos, un separador de elementos de datos de componente o un separador de elementos de datos extensible, o<br /><br /> -El último carácter antes de un separador de elementos de datos es un separador de elementos de datos de componente o un separador de elementos de datos repetidos.|Sí|  
|46|Juego de caracteres no admitido|Notificación de que uno o varios de los caracteres utilizados no se encuentran en el juego de caracteres definido en el identificador de sintaxis, o bien el destinatario no admite el juego de caracteres identificado por la secuencia de escape para la técnica de extensión de código.|Sí|  
|47|Funcionalidad de sobre no admitida|Notificación de que el destinatario no admite la estructura de sobre detectada.|Sí|  
|48|Infracción de condición de notas de dependencia|Notificación de que se ha producido una condición de error como resultado de una infracción de la condición de dependencia.|No|  
  
 **Códigos de Error EDIFACT específicos de servidor BizTalk Server**  
  
 En la tabla siguiente se enumeran los códigos de error que se usan en el campo UCI5 de la confirmación de CONTRL de EDIFACT y que no forman parte de la especificación EDIFACT. Se trata de códigos personalizados que son específicos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
|Código de error|Condición|Causa|  
|----------------|---------------|-----------|  
|70|Falta el identificador de conjunto de transacciones o éste no es válido|Notificación de que falta el identificador del conjunto de transacciones o que no es válido.|  
|71|Número de control de grupo o conjunto de transacciones no coincidente|Notificación de que falta coincidencia de los números de conjunto de transacciones o control de grupo.|  
|72|Id. de segmento no reconocido.|Notificación de que no se reconoce el identificador de segmento.|  
|73|XML no está en la posición correcta|Notificación de que se produjo un problema al serializar el elemento raíz XML.|  
|74|Repeticiones insuficientes de grupos de segmentos|Notificación de que un grupo de segmentos se repite menos de la cantidad necesaria.|  
|75|Repeticiones insuficientes de segmento|Notificación de que un segmento se repite menos de la cantidad necesaria.|  
|76|No se encontraron suficientes datos de elementos.|Notificación de que no se encontraron suficientes elementos de datos.|