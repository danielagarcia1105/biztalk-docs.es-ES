---
title: Administración de recursos | Microsoft Docs
description: Usar btstask o administración de BizTalk para trabajar con ensamblados, secuencias de comandos, certificados, los archivos de enlace y otra información en el servidor BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b478ef2e-1363-4c2c-a4b7-6a582a6b33a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9aad282dfb444c2947afca3cefc0a96cd806826
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015117"
---
# <a name="manage-resources"></a>Administración de recursos

## <a name="overview"></a>Información general
Los temas de esta sección proporcionan instrucciones sobre cómo utilizar la consola de administración de BizTalk Server o la herramienta de la línea de comandos BTSTask para administrar recursos de BizTalk Server una vez que se han implementado en un grupo de BizTalk. Los recursos incluyen los siguientes tipos de artefactos:  
  
-   Ensamblados de BizTalk  
  
-   Secuencias de comandos previas y posteriores al procesamiento  
  
-   Ensamblados .NET  
  
-   Componentes COM  
  
-   Certificados  
  
-   Archivos ad hoc  
  
-   Definiciones de BAM  
  
-   Archivos de enlace  
  
-   Directorios virtuales  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas. Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
> 
> [!NOTE]
>  No agregue varios recursos con el mismo nombre, independientemente del caso, a un grupo de BizTalk Server. No se admite la agregación de varios recursos con el mismo nombre a un grupo de BizTalk Server, incluso cuando la base de datos de administración de BizTalk Server esté alojada en un servidor SQL Server que se haya configurado para utilizar la intercalación binaria y distinga entre mayúsculas y minúsculas.  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Administración de ensamblados de BizTalk](../core/managing-biztalk-assemblies.md)  
  
-   [Administración de scripts previos y posteriores al procesamiento](../core/managing-pre-and-post-processing-scripts.md)  
  
-   [Administración de ensamblados .NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)  
  
-   [Actualizar un recurso](../core/how-to-refresh-a-resource.md)