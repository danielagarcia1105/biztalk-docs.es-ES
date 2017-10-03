---
title: No se puede determinar el esquema | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2cc6e50b-33f5-4a88-b35d-075fdf8d79b2
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82731b0712ac880936e074005c01eab7945b4add
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="cannot-determine-scheme"></a>No se puede determinar el esquema
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se puede determinar el esquema; especifique un enlace válido.|  
  
## <a name="explanation"></a>Explicación  
 El elemento de enlace de transporte que se ha especificado no tiene esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Seleccione un enlace válido y asegúrese de que el elemento de enlace de transporte tenga un esquema válido. Si usa un enlace personalizado, asegúrese de que se especifique un elemento de enlace de transporte válido.  
  
 Para obtener más información, consulte los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:  
  
-   [Configurar el adaptador de WCF-Custom](../core/configuring-the-wcf-custom-adapter.md)