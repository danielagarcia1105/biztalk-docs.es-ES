---
title: 'Se produjo un error en el procesamiento de X12 mensajes en el puerto de envío: no existen acuerdos de pares de calificador de identificador de destinatario y remitente | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72ae7926-f5c1-42f4-8c29-11f34c138dd4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 637cd174b2c9723f4391417392700e3a4f079b79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240860"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a>Se produjo un error en el procesamiento de X12 mensajes en el puerto de envío: no existen acuerdos de pares de calificador de identificador de destinatario y remitente
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|Error al procesar el mensaje X12 en el puerto de envío {0}. No existen acuerdos de pares de calificador o identificador de destinatario y remitente de {1}, {2}, {3}, \{4\.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server no pudo resolver la entidad para el intercambio EDIFACT porque no pudo hacer coincidir las propiedades del calificador e identificador del servidor promocionado y las propiedades del calificador e identificador del receptor promocionado con los valores correspondientes para una entidad.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el calificador e identificador del remitente (ISA5 e ISA6) y el calificador e identificador del receptor (ISA7 e ISA8) definidos en la página Definición de segmento ISA del cuadro de diálogo Propiedades de EDI coinciden con las propiedades promocionadas correspondientes en el contexto del intercambio.