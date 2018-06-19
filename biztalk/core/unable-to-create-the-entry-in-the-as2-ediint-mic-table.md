---
title: No se puede crear la entrada en la tabla AS2 EDIINT MIC | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1c75d70-e39e-4465-b32b-db646c059c9b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c51cac2861fabaf8fc50269623130c90f3d445b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286700"
---
# <a name="unable-to-create-the-entry-in-the-as2-ediint-mic-table"></a>No se puede crear la entrada en la tabla AS2 EDIINT MIC
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|AS2MicDataStoreCreateEntryError|  
|Texto del mensaje|No se puede crear la entrada en la tabla AS2 EDIINT MIC. La razón puede ser la escritura de combinaciones de AS2-From, AS2-To y MessageID duplicadas en la tabla.  Error: {0}|  
  
## <a name="explanation"></a>Explicación  
 Este error indica problemas de conexión de la base de datos o que las claves de la fila ya existen en la tabla de la base de datos. El mensaje de error completo debe proporcionar información sobre por qué no se ha podido realizar la operación de inserción. Las entradas de la tabla se quitan una vez que se haya recibido el MDN (sea con éxito o no), de modo que este error no debe volver a aparecer una vez recibido el MDN.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, compruebe el mensaje de error completo para obtener información acerca de por qué no se pudo realizar la operación de inserción. En SQL, en la tabla EDIINT_MIC, determine si existen combinaciones AS2-From y AS2-To MessageID duplicadas. Si es así, quítelas.