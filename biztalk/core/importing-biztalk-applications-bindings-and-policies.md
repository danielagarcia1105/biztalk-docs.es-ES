---
title: "Importación de aplicaciones de BizTalk, los enlaces y directivas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing, applications
- importing, policies
- applications, importing
- policies, importing
- importing, bindings
- bindings, importing
ms.assetid: 678bdb03-efaa-4053-9048-b71fc539d191
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18f7ea348fb34f4f8cc08e748799dcf8368a3c35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-biztalk-applications-bindings-and-policies"></a>Importar aplicaciones, enlaces y directivas de BizTalk
Los temas que figuran en esta sección describen cómo importar aplicaciones, enlaces y directivas de BizTalk en un grupo o aplicación de BizTalk. Como se mencionó en [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md), al exportar una aplicación crea un archivo de Windows Installer (.msi) que, a continuación, puede usar para importar los artefactos de la aplicación a una aplicación en un grupo de BizTalk diferente. Si la aplicación especificada para la importación aún no existe en el grupo, se creará. Además, los artefactos de la aplicación se registran y sus datos se almacenan en las bases de datos del grupo de BizTalk. Para obtener más información, consulte [¿qué ocurre cuando artefactos se importarán](../core/what-happens-when-artifacts-are-imported.md).  
  
 También puede importar en un grupo de BizTalk o una aplicación los enlaces que exportó desde un grupo de BizTalk, aplicación o ensamblado, tal como se describe en [exportar enlaces](../core/exporting-bindings6.md). Al importar enlaces, éstos sobrescriben cualquier enlace con el mismo nombre que haya en el grupo, la aplicación o el ensamblado de BizTalk.  
  
 Además, puede importar una directiva a un grupo de BizTalk que exportó desde un grupo de BizTalk o una aplicación, como se describe en [cómo exportar una directiva](../core/how-to-export-a-policy.md). A continuación, las aplicaciones del grupo nuevo podrán utilizar la directiva.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md)  
  
-   [Importar enlaces](../core/importing-bindings2.md)  
  
-   [Cómo importar una directiva](../core/how-to-import-a-policy.md)