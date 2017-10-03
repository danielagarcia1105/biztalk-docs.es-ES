---
title: "X12 códigos de Error de confirmación 997 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f73ca2c-cfff-444b-ae80-fb724f067fcc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89627cc793000fa6bb9c11c5e15dc78423fcb0ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="x12-997-acknowledgment-error-codes"></a>Códigos de error de confirmación 997 de X12
En este tema se enumeran los códigos de error usados dentro de los segmentos de una confirmación 997 de X12. Para obtener más información acerca de estos segmentos, vea [X12 confirmación 997](../core/x12-997-acknowledgment.md).  
  
 En cada tabla se describe qué códigos de error indicados por la especificación X12 se admiten en EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y cuáles no.  
  
 **AK304 Códigos de Error**  
  
 La tabla siguiente muestra los códigos de error que se utilizan en el elemento de datos AK304 del segmento AK3 (nota del segmento de datos).  
  
|Código de error|Condición|¿Admitido?|  
|----------------|---------------|----------------|  
|1|Id. de segmento no reconocido.|Sí|  
|2|Segmento inesperado.|Sí|  
|3|Falta segmento obligatorio|Sí|  
|4|Se produce un bucle superior al máximo permitido|Sí|  
|5|El segmento excede la descripción de uso máximo|Sí|  
|6|Segmento no definido en el conjunto de transacciones|Sí|  
|7|El segmento no tiene el orden adecuado|Sí|  
|8|El segmento contiene errores de elementos de datos|Sí|  
|511|Se han encontrado separadores finales (código personalizado)|Sí|  
  
 **AK403 Códigos de Error**  
  
 La tabla siguiente muestra los códigos de error que se utilizan en el elemento de datos AK403 del segmento AK4 (nota del elemento de datos).  
  
|Código de error|Condición|¿Admitido?|  
|----------------|---------------|----------------|  
|1|Falta elemento de datos obligatorio.|Sí|  
|2|Falta un elemento de datos requerido condicional.|Sí|  
|3|Demasiados elementos de datos.|Sí|  
|4|El elemento de datos es demasiado corto.|Sí|  
|5|El elemento de datos es demasiado largo.|Sí|  
|6|Carácter no válido en el elemento de datos.|Sí|  
|7|Valor de código no válido|Sí|  
|8|Fecha no válida|Sí|  
|9|Hora no válida|Sí|  
|10|Infringido de condición de exclusión|Sí|  
  
 **AK501 Códigos de Error**  
  
 La tabla siguiente muestra los códigos de error que se utilizan en el elemento de datos AK501 del segmento AK5 (finalizador de respuesta del conjunto de transacciones).  
  
|Código de error|Condición|¿Admitido?|  
|----------------|---------------|----------------|  
|Un|Aceptado|Sí|  
|E|Se acepta, pero se registraron los errores.|Sí<br /><br /> Nota: Ninguno de los códigos de error conduce a un estado de "E".|  
|M|Rechazado. Error del código de autenticación del mensaje (MAC).|No|  
|P|Parcialmente aceptado, pero al menos un conjunto de transacciones se rechazó.|Sí|  
|L|Rechazado|Sí|  
|W|Rechazado. La seguridad no superó las pruebas de validez.|No|  
|X|Rechazado. No se pudo analizar el contenido tras el descifrado.|No|  
  
 **AK502 a AK506 códigos de Error**  
  
 La tabla siguiente muestra los códigos de error que se utilizan en los elementos de datos de AK502 a AK506 del segmento AK5 (finalizador de respuesta del conjunto de transacciones).  
  
|Código de error|Condición|Admite? /<br />¿Correlaciona con AK501?|  
|----------------|---------------|------------------------------------------|  
|1|Conjunto de transacciones no admitido|Sí/R|  
|2|Falta el finalizador de conjunto de transacciones.|Sí/R|  
|3|El número de control de conjunto de transacciones del encabezado y del finalizador no coincide.|Sí/R|  
|4|El número de segmentos incluidos no coincide con el recuento real.|Sí/R|  
|5|Error en uno o más segmentos.|Sí/R|  
|6|El identificador del conjunto de transacciones falta o no es válido.|Sí/R|  
|7|El número de control del conjunto de transacciones falta o no es válido (puede haberse producido la duplicación de un número de transacción).|Sí/R|  
|8 a 27|-|No|  
  
 **AK901 Códigos de Error**  
  
 La tabla siguiente muestra los códigos de error que se utilizan en los elementos de datos AK901 del segmento AK9 (finalizador de respuesta del grupo funcional).  
  
|Código de error|Condición|Admite? /<br />¿Correlaciona con AK501?|  
|----------------|---------------|------------------------------------------|  
|Un|Aceptado|Sí|  
|E|Aceptado, pero se han registrado los errores|Sí|  
|M|Rechazado. Error del código de autenticación del mensaje (MAC).|No|  
|P|Parcialmente aceptado, pero al menos un conjunto de transacciones se rechazó.|Sí|  
|L|Rechazado|Sí|  
|W|Rechazado. La seguridad no superó las pruebas de validez.|No|  
|X|Rechazado. No se pudo analizar el contenido tras el descifrado.|No|  
  
 **AK905 a AK909 códigos de Error**  
  
 La tabla siguiente muestra los códigos de error que se utilizan en los elementos de datos de AK905 a AK909 del segmento AK9 (finalizador de respuesta del grupo funcional).  
  
|Código de error|Condición|Admite? /<br />¿Correlaciona con AK501?|  
|----------------|---------------|------------------------------------------|  
|1|Grupo funcional no compatible|No|  
|2|Versión de grupo funcional no compatible|No|  
|3|Falta el finalizador del grupo funcional.|Sí|  
|4|El número de control de grupo del encabezado y el finalizador del grupo funcional no coinciden.|Sí|  
|5|El número de conjuntos de transacciones incluidos no coincide con el recuento real.|Sí|  
|6|El número de control de grupo infringe la sintaxis (puede haberse producido la duplicación de un número de control de grupo).|Sí|  
|7 a 26|-|No|  
  
## <a name="see-also"></a>Vea también  
 [X12 confirmación 997](../core/x12-997-acknowledgment.md)