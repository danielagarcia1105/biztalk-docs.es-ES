---
title: El comando ListTypes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94febe8a-4c1e-4581-a6d1-ef579633e745
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe2519fc5507ae0975d050a998faec78f2940a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262220"
---
# <a name="listtypes-command"></a>ListTypes (comando)
Enumera todos los tipos de artefactos que se pueden agregar a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el uso de la **AddResource** comando. Para obtener más información sobre la **AddResource** command, consulte [comando AddResource](../core/addresource-command.md).  
  
 Los nombres completos de los tipos de artefactos compatibles son los que se muestran a continuación:  
  
-   Ensamblado .NET: System.BizTalk:Assembly  
  
-   Definición de BAM: BizTalk: BAM  
  
-   Ensamblado de BizTalk: System.BizTalk:BizTalkAssembly  
  
-   Archivo de enlace de BizTalk: BizTalk: biztalkbinding  
  
-   Certificado de seguridad: System.BizTalk:Certificate  
  
-   Componente COM: BizTalk: com  
  
-   Archivo ad hoc: BizTalk: File  
  
-   Secuencias posteriores al procesamiento de secuencia de comandos: System.BizTalk:PostProcessingScript  
  
-   Secuencia de comandos de preprocesamiento: System.BizTalk:PreProcessingScript  
  
-   Directiva o regla: System.BizTalk:Rules  
  
-   Directorio virtual: System.BizTalk:WebDirectory  
  
> [!NOTE]
>  Para evitar conflictos de espacio de nombres, siempre debería utilizar el nombre de tipo completo (como, System.BizTalk:Assembly) en lugar del nombre de tipo solo (como Ensamblado).  
  
## <a name="usage"></a>Uso  
 **BTSTask ListTypes**  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)