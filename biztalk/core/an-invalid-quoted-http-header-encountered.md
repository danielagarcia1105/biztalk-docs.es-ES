---
title: "No es válida entre comillas encontrado un encabezado HTTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb530ee6-ec6a-4791-ae99-b9db426c0896
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e154e3bacf34025edd837516a15dca6f2caa174
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="an-invalid-quoted-http-header-encountered"></a>Se detectó un encabezado HTTP entre comillas no válido
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|-|  
|Texto del mensaje|Se detectó un encabezado HTTP entre comillas no válido.  Detalles son los siguientes: nombre de encabezado: valor de encabezado "{0}": "{{1}"|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción AS2 o que la canalización de envío AS2 no pudo procesar el mensaje AS2 porque el nombre del encabezado HTTP AS2-From o AS2-To del mensaje no se entrecomilló correctamente. El nombre del encabezado se entrecomilla con el fin de ajustar un espacio, una barra invertida o comillas dentro del nombre.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, entrecomille el nombre del encabezado en el mensaje AS2 según las reglas que se indican en la sección 6.2, "AS2 System Identifiers", en RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2").