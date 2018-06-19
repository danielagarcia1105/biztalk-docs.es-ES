---
title: Formas de interpretar los caracteres especiales como parte de un valor de campo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e19a202-4e4d-42e0-ba1e-fddc52792b21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b96a3c7502a47541e8e58ec3df3eccf6098e3abc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288388"
---
# <a name="ways-to-interpret-special-characters-as-part-of-a-field-value"></a>Formas de interpretar los caracteres especiales como parte de un valor de campo
Los campos de los registros posicionales y delimitados pueden contener caracteres especiales de distintos tipos, como caracteres controlador, de ajuste y de escape. Los registros delimitados también pueden tener uno o más caracteres de delimitador distintos para separar los campos de un registro o un registro de otro. Estos caracteres especiales a veces forman parte de los propios datos, en cuyo caso no deben interpretarse como especiales.  
  
 Los esquemas de archivo sin formato usados por Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite dos técnicas distintas para marcar los casos de especial en caso contrario caracteres simplemente como parte de los datos contenidos en un campo. Estas dos técnicas se basan en el uso de caracteres de escape y de ajuste.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Caracteres de escape](../core/escape-characters.md)  
  
-   [Ajustar caracteres](../core/wrap-characters.md)