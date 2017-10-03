---
title: "Escriba reutilización y derivaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 240145ea-be41-40ce-8edd-3d4d00e2baec
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2982fdf5e46f813669ff74b513615637aa699bd4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="type-reuse-and-derivations"></a>Reutilización y derivaciones de tipos
Dentro del lenguaje de definición de esquemas XML (XSD), los tipos globales complejos proporcionan un mecanismo para definir un tipo de datos estructurado que se puede reutilizar y potencialmente redefinir en varias ubicaciones del esquema. Tal vez el ejemplo más clásico sea la estructura de una dirección, que incluye un nombre, la calle, la ciudad, el estado, etc. Asimismo, el propio nombre puede ser una estructura que incluya cadenas de nombre, segundo nombre y apellidos. Si esta estructura compleja está definida de forma global, se podrá utilizar en varias ubicaciones dentro del esquema, como una dirección de envío y una dirección de facturación.  
  
 XSD también proporciona mecanismos para derivar un tipo a partir de otro. Esto incluye tanto tipos de contenido simple como tipos de contenido complejo. Por ejemplo, se puede derivar un tipo nuevo a partir de un tipo de cadena simple (como xs:string) de modo que el tipo nuevo admita únicamente un número reducido de cadenas concretas como valores permitidos. Este tipo de derivación se conoce en XSD como derivación por restricción, ya que los valores permitidos por el tipo derivado son más restrictivos que los que admite el tipo base.  
  
 Un ejemplo de derivación con un tipo complejo puede ser el tipo de dirección que se ha indicado antes. Supongamos que el tipo de dirección se ha diseñado para las direcciones de un país y una región concretas, donde el propio valor de país o región se considera parte de la dirección. Para ampliar ese tipo de dirección de modo que abarque direcciones internacionales, puede derivar un tipo nuevo a partir del tipo de dirección original y, a continuación, incluir información adicional en el tipo derivado, como el país y la región. Este tipo de derivación se conoce en XSD como derivación por extensión, ya que el tipo derivado ha extendido el tipo base.  
  
 Esta sección describe la reutilización de tipos y las formas en las que se puede usar la derivación para redefinir tipos reutilizados.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Definición de tipo Global complejo y nomenclatura](../core/complex-global-type-definition-and-naming.md)  
  
-   [Formas de utilizar los tipos globales complejos](../core/ways-to-use-complex-global-types.md)  
  
-   [Derivación de tipo simple](../core/simple-type-derivation.md)