---
title: Coincidencia del nivel jerárquico de nodos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Field nodes
- BizTalk Mapper, processing
- Record node
- BizTalk Mapper, compiler directives
- destination schemas, matching nodes
- source schemas, matching nodes
- maps, links
- Target Links property
- BizTalk Mapper, links
- compiler directives, matching schema nodes
- compiler directives, flattening source hierarchies
- maps, processing
ms.assetid: 5ba1ac77-0e70-4c58-9b8c-1b379dbbb3bd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b2d0c363abfefb9e3d0eb8abfb332c59539bb67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264764"
---
# <a name="node-hierarchy-level-matching"></a>Coincidencia del nivel jerárquico de nodos
El Asignador de BizTalk le permite configurar una propiedad de vínculo para controlar cómo el compilador hace coincidir las jerarquías de nodos entre los esquemas de origen y de destino. Cuando crea un vínculo desde un campo del esquema de origen hacia un campo del esquema de destino, el Asignador de BizTalk agrega automáticamente vínculos de compilador. Estos vínculos de compilador dependen de la coincidencia que seleccione.  
  
 Cuando se selecciona un vínculo en la página de cuadrícula mostrada, una de las propiedades se muestra en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades es el **vínculos de destino** propiedad. Puede elegir entre alguno de los siguientes valores posibles para cada vínculo de la asignación:  
  
-   **Vínculos sin formato.** Utilice este valor para quitar el formato de todas las jerarquías de origen del registro primario del nodo de esquema de destino.  
  
-   **Coincidir vínculos de arriba hacia abajo.** Utilice este valor para hacer coincidir los niveles de nodos de la parte alta a la parte baja de los esquemas.  
  
-   **Coincidir vínculos de abajo arriba.** Utilice este valor para hacer coincidir los niveles de nodos de la parte baja a la parte alta de los esquemas.  
  
## <a name="flatten-links"></a>Vínculos sin formato  
 En este modo, se quita el formato de todas las jerarquías de origen del registro primario del nodo de destino. En el primer caso, el esquema de origen es más complejo que el esquema de destino. En el segundo caso, el esquema de destino es más complejo.  
  
 ![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")  
Vínculos sin formato  
  
 ![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")  
Vínculos sin formato, segundo caso  
  
## <a name="match-links-top-down"></a>Coincidir vínculos de arriba abajo  
 Este modo hace coincidir nivel a nivel en orden descendente. En el primer caso, el esquema de origen es más complejo que el esquema de destino. En el segundo caso, el esquema de destino es más complejo.  
  
 ![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")  
Coincidencia de arriba abajo  
  
 ![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")  
Coincidencia de arriba abajo, segundo caso  
  
## <a name="match-links-bottom-up"></a>Coincidir vínculos de abajo arriba  
 Este modo hace coincidir nivel a nivel en orden ascendente. En el primer caso, el esquema de origen es más complejo que el esquema de destino. En el segundo caso, el esquema de destino es más complejo.  
  
 ![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")  
Coincidencia de abajo arriba  
  
 ![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")  
Coincidencia de abajo arriba, segundo caso  
  
## <a name="how-biztalk-mapper-processes-link-types"></a>Cómo procesa los tipos de vínculos el Asignador de BizTalk  
 Dado que puede establecer el **vínculos de destino** propiedad a valores distintos para vínculos diferentes, el asignador de BizTalk necesita una manera de resolver las diversas configuraciones cuando puedan entrar en conflicto.  
  
 Por ejemplo, si usa una directiva de compilador sin formato, una directiva de compilador de arriba a abajo y una directiva de compilador de abajo arriba para vínculos de **campo** nodos **campo** nodos en el esquema de destino y estos nodos comparten la misma actividad primaria **registro** nodo, el asignador de BizTalk omite las directivas de compilador de arriba a abajo y de abajo arriba en conflicto y trata todos los vínculos como si estuvieran establecidos para la directiva de compilador sin formato.  
  
 En la tabla siguiente se muestra cómo el asignador de BizTalk trata los vínculos a **campo** nodos en el mismo **registro** nodo del esquema de destino, en función de la configuración de la **vínculos de destino** propiedad para los vínculos dentro de la misma **registro** nodo.  
  
|Sin formato|De arriba abajo|De abajo arriba|Resultado|  
|-------------|---------------|----------------|------------|  
|0 o más|1 o más|1 o más|El Asignador de BizTalk trata todos los vínculos como si estuvieran establecidos para la directiva de compilador sin formato.|  
|1 o más|1 o más|0|El Asignador de BizTalk trata todos los vínculos como si estuvieran establecidos para una directiva de compilador de arriba abajo.|  
|1 o más|0|1 o más|El Asignador de BizTalk trata todos los vínculos como si estuvieran establecidos para una directiva de compilador de abajo arriba.|  
  
 Las directivas de compilador de arriba abajo y de abajo arriba tienen prioridad sobre la directiva de compilador sin formato, pero se cancelan entre sí cuando ambas están presentes.  
  
## <a name="see-also"></a>Vea también  
 [Functoid de copia masiva](../core/mass-copy-functoid.md)   
 [Cómo establecer el valor de compilador de vínculos de origen](../core/how-to-set-the-source-links-compiler-value.md)   
 [Compilar asignaciones](../core/compiling-maps.md)