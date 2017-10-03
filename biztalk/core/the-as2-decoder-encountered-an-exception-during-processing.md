---
title: "El descodificador AS2 detectó una excepción durante el procesamiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5f16d2e-e83c-4e2c-84be-41b5ed012dce
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2826a938a4f081b8c5895da809e9f16966e25834
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-as2-decoder-encountered-an-exception-during-processing"></a>El descodificador AS2 detectó una excepción durante el procesamiento
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|AS2DecoderExceptionEncounteredDuringProcessing|  
|Texto del mensaje|El descodificador AS2 detectó una excepción durante el procesamiento.  Detalles del mensaje y excepción son los siguientes: AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}" MessageType: "{3}" excepción: "\ {4\}"|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el mensaje AS2 entrante debido a un problema con el descodificador AS2.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, compruebe el código de error de AS2 para determinar la naturaleza de la condición de error. Para obtener más información sobre códigos de error de AS2, consulte el tema "Códigos de error de AS2" en el archivo de Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].