---
title: No se puede obtener el esquema del enlace para validar la dirección | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b002084a-63ae-4685-8ce3-88cc6489e19e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c952e967a391011bbd887513d58e426d90d325a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230964"
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a>No se puede obtener el esquema del enlace para validar la dirección
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se puede obtener el esquema del enlace para validar la dirección.|  
  
## <a name="explanation"></a>Explicación  
 El elemento de enlace de transporte que se ha especificado no tiene esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Asegúrese de que el elemento de enlace de transporte tiene un esquema válido, o que esté seleccionado un elemento de enlace de transporte válido. Si usa un enlace personalizado, asegúrese de que se especifique un elemento de enlace de transporte válido.  
  
 Para obtener más información, consulte los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:  
  
-   [Configurar el adaptador de WCF-Custom](../core/configuring-the-wcf-custom-adapter.md)