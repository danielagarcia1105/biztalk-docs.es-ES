---
title: "Cálculo de la posición de campo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e315f09-f2c9-49cc-8d2f-0f4f2d48fd45
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55c58f532ea64300518667d677d2248f5c1c2b6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="field-position-calculation"></a>Cálculo de la posición de campo

## <a name="overview"></a>Información general
Cuando se usa el **longitud posicional** y **desplazamiento posicional** propiedades de la **elemento de campo** y **atributo de campo** nodos en el esquema para definir el diseño de los registros posicionales en el mensaje de archivo sin formato, el **posición iniciar** y **longitud** columnas de la **archivos planos** pestaña Editor de BizTalk muestra las posiciones iniciales calculadas y longitudes, respectivamente, de los campos correspondientes y los registros.  
  
> [!NOTE]
>  El **archivos planos** ficha aparece como una vista con pestañas alternativa con la vista XSD en el Editor de BizTalk cuando se ha configurado la extensión de archivo sin formato mediante la **extensiones de Editor de esquemas** propiedad de la **Esquema** nodo. Para obtener más información acerca de esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 En general, la posición inicial de un campo determinado *N* es la posición inicial del campo anterior más la longitud del campo anterior, más el desplazamiento (posicional) especificado para el campo *N*.  
  
 Todo el cálculo posición de campo en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es realiza automáticamente, sobre la marcha, sin necesidad de ejecutar un comando (como ocurría en versiones anteriores de BizTalk Server).  
  
## <a name="see-also"></a>Vea también  
-  [Consideraciones del registro posicional](../core/positional-record-considerations.md)   
-  **Longitud posicional (propiedad de nodo de esquemas de archivo sin formato)** y **desplazamiento posicional (propiedad de nodo de esquemas de archivo sin formato)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]