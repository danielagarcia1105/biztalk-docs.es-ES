---
title: Esquemas de sobres | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af296c30-95dc-4fef-9aa3-bea2f2cd8caf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c44f1a5d9797ec09cc164789148287c98b4399
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="envelope-schemas"></a>Esquemas de sobres

## <a name="overview"></a>Información general
Puede crear un esquema de sobre de las mismas maneras con las que crea un esquema XML de un documento empresarial. Puede crear un esquema a partir de un mensaje de instancia de sobre XML bien estructurado o a partir de representaciones DTD (definición de tipo de documento) o XDR (datos reducidos XML) del esquema de sobre. Asimismo, puede crear un nuevo esquema, bien junto con otros esquemas o bien de forma aislada. Como los esquemas de sobre son normalmente más pequeños y menos complicados que la mayoría de los esquemas de documentos empresariales, la creación de un esquema de sobre nuevo es normalmente una alternativa viable.  
  
 Para definir un esquema como esquema de sobres, debe establecer el **sobres** propiedad de la **esquema** nodo en el valor **Sí**. Cuando se define un esquema de sobre, debe señalar la envoltura **XPath de cuerpo** para el nodo primario que contiene únicamente el \<cualquier > elemento secundario. Para que el ensamblador XML pueda usar el sobre, el nodo primario no debe contener ningún otro elemento.  
  
 Al establecer **sobres** propiedad **Sí**, significa que el contenido real del mensaje del mensaje de instancia XML (denominado cuerpo del mensaje) está presente en algún lugar dentro de la raíz **registro**  nodo del esquema, según lo especificado por el **XPath de cuerpo** propiedad de ese nodo. Por tanto, también debe establecer propiedades adicionales según algunas circunstancias:  
  
-   Si un esquema de sobre tiene una única raíz, debe establecer el **XPath de cuerpo** propiedad para ese nodo raíz.  
  
-   Si un esquema de sobre tiene varias raíces y la **referencia raíz** no está establecida la propiedad, debe establecer el **XPath de cuerpo** propiedad para todas las raíces.  
  
-   Si un esquema de sobre tiene varias raíces y la **referencia raíz** propiedad está establecida, se debe establecer el **XPath de cuerpo** propiedad de la raíz correspondiente **registro** nodo. Opcionalmente, puede establecer la **XPath de cuerpo** propiedad para el resto de las raíces.  
  
-   Independientemente de si un esquema de sobre tiene una o varias raíces, establecer el **[referencia raíz** propiedad no es necesaria.  

Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
 [Diferentes tipos de esquemas de BizTalk](../core/different-types-of-biztalk-schemas.md)   
 [Cómo crear esquemas de sobres](../core/how-to-create-schemas-for-envelopes.md)