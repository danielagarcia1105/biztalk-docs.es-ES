---
title: Cómo crear esquemas para sobres | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae1c991c-447f-497e-803c-1cb8cad2846b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7308a093f9f95ce2342f268554deb67193aea053
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249596"
---
# <a name="create-schemas-for-envelopes"></a>Crear esquemas de sobres

## <a name="overview"></a>Información general
Después de crear un esquema de mensaje XML como se describe en [crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md), establezca el **sobres** propiedad de la **esquema** nodo **Sí**. En función de determinadas características del esquema de sobre, como si hay varios nodos raíz, deberá establecer otras propiedades específicas del sobre. Para obtener más información, consulte [esquemas de sobres](../core/envelope-schemas.md).  
  
 La propiedad XPath de cuerpo del sobre hace referencia al elemento que contiene los elementos de documento. El elemento real al que hace referencia el XPath no pertenece al documento.  
  
## <a name="see-also"></a>Vea también  
-  [Administrar esquemas en proyectos](../core/managing-schemas-within-projects.md)
-  **Envoltura** propiedad[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]