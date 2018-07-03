---
title: Los artefactos que deben ser únicos en una aplicación o un grupo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, artifacts
- artifacts, requirements
- applications, artifacts
ms.assetid: a758cd74-a962-4e75-aea2-47752ab72a64
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb81ffe1f97681f82ddc3d45b9d93ff34b5e172a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023266"
---
# <a name="artifacts-that-must-be-unique-in-an-application-or-group"></a>Artefactos que deben ser únicos en una aplicación o en un grupo
Ciertos tipos de artefactos de un grupo o una aplicación de BizTalk deben ser únicos, como se indica a continuación:  
  
- Los ensamblados de BizTalk y los ensamblados .NET que no son de BizTalk deben tener un nombre completo único en el grupo. El nombre completo consta de un nombre de archivo, del token de clave pública, de la referencia cultural y de la versión.  
  
- Las reglas y las directivas deben tener un nombre y un número de versión únicos en el grupo.  
  
- Los puertos de envío, grupos de puertos de envío, puertos de recepción y ubicaciones de recepción deben tener un nombre único en el grupo.  
  
- Los sitios Web deben tener un nombre de directorio virtual único en el grupo.  
  
- Los recursos de BAM deben tener un nombre de archivo único en el grupo.  
  
- Los certificados deben tener una huella digital única en el grupo.  
  
- Los componentes COM deben tener un nombre de archivo único en el grupo.  
  
- Los artefactos basados en archivos, como secuencias de comandos y otros archivos sin formato, deben tener nombres de archivo únicos en la aplicación, pero no en el grupo.  
  
  Puede especificar la opción de sobrescritura para importar o agregar un artefacto a una aplicación si el artefacto ya existe en la aplicación y es de un tipo que debe ser único. Si el artefacto ya existe en otra aplicación del grupo y es de un tipo que debe ser único en el grupo, no podrá ni agregarlo ni importarlo.  
  
  Si necesita usar un artefacto en una aplicación y ya existe en otra aplicación del grupo, puede crear una referencia a la aplicación que contiene el artefacto. Para obtener más información, consulte [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).  
  
> [!NOTE]
>  Puede ver el nombre completo de la mayoría de los tipos de artefactos de una aplicación mediante el comando ListApp de BTSTask, como se describe en [comando ListApp](../core/listapp-command.md).  
  
## <a name="see-also"></a>Vea también  
 [Descripción de la implementación y administración de aplicaciones de BizTalk](../core/understanding-biztalk-application-deployment-and-management.md)