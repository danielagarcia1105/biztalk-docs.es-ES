---
title: "Comprobar la implementación Setup1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLASSPATH, verifying
- deployment, verifying setup
ms.assetid: 6c719e4c-9a61-480f-a4e4-0a1c518d1364
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5799d164dc2470236c3ab0286e38d19986a4d5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="verifying-the-deployment-setup"></a>Comprobar la configuración de implementación
Antes de usar BizTalk Server para importar un archivo de enlace, debe comprobar lo siguiente:  
  
-   CLASSPATH apunta a una ubicación concreta para los archivos específicos de JD Edwards EnterpriseOne. Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.  
  
-   Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.  
  
-   Las contraseñas del sistema JD Edwards EnterpriseOne, si están presentes en la configuración, se guardan como ***** en el archivo de enlace. Para obtener más información, consulte [limitaciones de la implementación](../core/deployment-limitations4.md).  
  
## <a name="see-also"></a>Vea también  
 [Implementación de puertos y ensamblados](../core/deploying-ports-and-assemblies3.md)