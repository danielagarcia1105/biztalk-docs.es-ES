---
title: X12 códigos de Error de confirmación de TA1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47eb315f-ec99-4e1e-937b-22199255f14f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2ff9001d73f815b0d62a4e83cc64e1288715f90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290852"
---
# <a name="x12-ta1-acknowledgment-error-codes"></a>Códigos de error de confirmación TA1 de X12
En este tema se enumeran los códigos de error usados dentro de los segmentos de una confirmación TA1 de X12. Para obtener más información acerca de estos segmentos, vea [X12 confirmación TA1](../core/x12-ta1-acknowledgment.md).  
  
 En la tabla siguiente se describe qué códigos de error que indica la especificación X12 se admiten en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI y AS2 y cuáles no. Los valores para el comportamiento del motor (TA104) son los siguientes:  
  
-   A = Aceptar  
  
-   E = Intercambio aceptado con errores  
  
-   R = Intercambio rechazado/suspendido  
  
|Condición|Comportamiento del motor (valor de TA104)|Valor de TA105|¿Admitido?|  
|---------------|-------------------------------------|-----------------|----------------|  
|Success|Un|000|Sí|  
|Los números de control de intercambio del encabezado ISA 13 y del finalizador IEA02 no coinciden.|E|001|Sí|  
|El estándar en ISA11 (estándares de control) no es compatible.|E|002|Sí<br /><br /> (si hay identificadores que no coinciden)|  
|La versión de los controles no es compatible.|E|003|Ya no<sup>1</sup>|  
|Terminador de segmento es válido<sup>2</sup>|L|004|Sí|  
|Calificador de Id. de intercambio no válido para el remitente.|L|005|Sí<br /><br /> (si hay identificadores que no coinciden)|  
|Id. de intercambio no válido para el remitente.|E|006|Sí<sup>3</sup>|  
|Calificador de Id. de intercambio no válido para el receptor.|L|007|Sí<br /><br /> (si hay identificadores que no coinciden)|  
|Id. de receptor de intercambio no válido.|E|008|Ya no<sup>3</sup>|  
|Id. de receptor de intercambio desconocido.|E|009|Sí|  
|Valor de calificador de información de autorización no válido.|L|010|Sí<br /><br /> (si hay identificadores que no coinciden)|  
|Valor de información de autorización no válido.|L|011|Sí<br /><br /> (si una entidad está configurada o tiene un valor)|  
|Valor de calificador de información de seguridad no válido.|L|012|Sí<br /><br /> (si hay identificadores que no coinciden)|  
|Valor de información de seguridad no válido|L|013|Sí<br /><br /> (si una entidad está configurada o tiene un valor)|  
|Valor de fecha de intercambio no válido.|L|014|Sí|  
|Valor de hora de intercambio no válido.|L|015|Sí|  
|Valor de identificador de estándares de intercambio no válido.|L|016|Sí|  
|Valor de Id. de versión de intercambio no válido|L|017|Sí<sup>4</sup>|  
|Valor de número de control de intercambio no válido.|L|018|Sí|  
|Valor solicitado de confirmación no válido|E|019|Sí|  
|Valor no válido de indicador de prueba|E|020|Sí|  
|Valor de número de grupos incluidos no válido|E|021|Sí|  
|Estructura de control no válida.|L|022|Sí|  
|Fin de archivo (transmisión) incorrecto (prematuro)|L|023|Sí|  
|Contenido de intercambio no válido (por ejemplo, segmento GS no válido).|L|024|Sí|  
|Número de control de intercambio duplicado.|L<br /><br /> (basado en la configuración)|025|Sí|  
|Separador de elemento de datos no válido.|L|026|Sí|  
|Separador de elemento de componente no válido.|L|027|Sí|  
|Fecha de entrega no válida en solicitud de entrega aplazada.|No compatible|-|-|  
|Hora de entrega no válida en solicitud de entrega aplazada.|No compatible|-|-|  
|Código de hora de entrega no válido en solicitud de entrega aplazada.|No compatible|-|-|  
|Calificación de servicio no válida.|No compatible|-|-|  
  
 <sup>1</sup> código de error 017 se utiliza en su lugar.  
  
 <sup>2</sup> combinaciones válidas del terminador de segmento son: sólo el carácter del terminador de segmento y caracteres de terminador de segmento seguido por el sufijo 1 y el sufijo 2.  
  
 <sup>3</sup> compatible si se recibe un intercambio en un puerto de recepción que requiera autenticación. Las propiedades relacionadas del Id. de remitente se revisarán y, si no son coherentes, se rechazarán. Si la configuración de entidad no está disponible porque no está establecida, el intercambio se rechazará.  
  
 <sup>4</sup> indica que el valor de enumeración no es válido.