---
title: No válido ReceiverId | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feabf940-c49b-4f4a-8906-230dc8fb1b30
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d397c75efe1172f87def3dee92e20f4d0d7ef4d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257060"
---
# <a name="invalid-receiverid"></a>Id. de destinatario no válido.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12Ta1InvalidReceiverIdDescription|  
|Texto del mensaje|Id. de destinatario no válido.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque el identificador de receptor en el campo ISA08 o la identificación de destinatario en el campo UNB3.1 no se ajustaba al tipo de datos y al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el campo ISA08 sea del tipo de datos X12_AN y tenga una longitud de 15 caracteres (con o sin espacios finales) o de que el campo UNB3.1 sea del tipo de datos EDIFACT_AN y tenga entre 1 y 35 caracteres. Vuelva a enviar el intercambio.