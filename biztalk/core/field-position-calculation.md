---
title: Cálculo de la posición de campo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e315f09-f2c9-49cc-8d2f-0f4f2d48fd45
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fb167c0bf704aee869e81798116377608fde0c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983029"
---
# <a name="field-position-calculation"></a>Cálculo de la posición de campo

## <a name="overview"></a>Información general
Cuando se usa el **longitud posicional** y **desplazamiento posicional** propiedades de la **elemento de campo** y **atributo de campo** nodos en el esquema para definir el diseño de los registros posicionales en un mensaje de archivo sin formato, el **posición iniciar** y **longitud** columnas de la **archivos sin formato** pestaña El Editor de BizTalk muestran las posiciones de iniciales calculadas y longitudes, respectivamente, de los campos correspondientes y los registros.  

> [!NOTE]
>  El **archivos planos** pestaña aparece como una vista con pestañas alternativa con la vista XSD en el Editor de BizTalk cuando se ha configurado la extensión de archivo sin formato mediante el **extensiones de Editor de esquemas** propiedad de la **Esquema** nodo. Obtener más detalles sobre esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

 En general, la posición inicial de un campo determinado *N* es la posición inicial del campo anterior, así como la longitud del campo anterior, más el desplazamiento (posicional) especificado para el campo *N*.  

 Cálculo de la posición de campo todos en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es realiza automáticamente, en la marcha, sin necesidad de ejecutar un comando (como era necesario en versiones anteriores de BizTalk Server).  

## <a name="see-also"></a>Vea también  
- [Consideraciones acerca de los registros posicionales](../core/positional-record-considerations.md)   
- **Longitud posicional (propiedad de nodo de esquemas de archivo sin formato)** y **desplazamiento posicional (propiedad de nodo de esquemas de archivo sin formato)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
