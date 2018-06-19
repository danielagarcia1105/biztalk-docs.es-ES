---
title: ¿Qué ocurre cuando se agregan y quitan artefactos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, deleting
- artifacts, creating
- deleting, artifacts
ms.assetid: 811166ba-3ff4-4224-9d84-a2f4ed31bf4d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 464964714993205ef65d5a67de3399935f79320f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288884"
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a>¿Qué ocurre cuando se agregan y se quitan los artefactos?
En este tema se describe lo que sucede cuando se agregan artefactos a una aplicación. Puede agregar artefactos basados en archivos a una aplicación mediante la consola de administración de BizTalk Server o la herramienta de la línea de comandos BTSTask. Los artefactos basados en archivos incluyen los siguientes tipos:  
  
-   Ensamblados de BizTalk  
  
-   Ensamblados .NET que no son específicos de BizTalk  
  
-   Archivos (.xml) de enlace  
  
-   Componentes COM  
  
-   Certificados  
  
-   Secuencias de comandos previas y posteriores al procesamiento  
  
-   Directivas  
  
-   Archivos ad hoc, como archivos Léame  
  
-   Directorios virtuales  
  
-   Artefactos de BAM  
  
> [!NOTE]
>  Los puertos de envío, grupos de puertos de envío, ubicaciones de recepción y puertos de recepción no son artefactos basados en archivos y no se pueden agregar a una aplicación. Debe crear estos artefactos dentro de una determinada aplicación. A continuación, puede moverlos a una aplicación diferente si desea. Las orquestaciones, los esquemas, las asignaciones y las canalizaciones se implementan y se administran como parte de los ensamblados que contienen estos elementos.  
  
 Cuando agregue un artefacto a una aplicación, el artefacto se asocia a la aplicación de la base de datos de administración de BizTalk y los datos basados en archivos del artefacto se agregan también a la base de datos de administración. Esto le permite transportar aplicaciones y artefactos con facilidad de un grupo de BizTalk a otro ya que puede exportar la aplicación y los datos de los artefactos a un archivo .msi desde la base de datos de administración y, a continuación, importarlos a una base de datos de administración de un grupo de BizTalk diferente.  
  
 Cuando agrega un archivo de enlace a una aplicación, puede especificar el entorno de implementación de destino en el que desea que se apliquen los enlaces. A diferencia de lo que ocurre al importar un archivo de enlace, cuando agrega un archivo de enlace no se aplican los enlaces correspondientes.  
  
 Al agregar un ensamblado de BizTalk o un ensamblado .NET a una aplicación, éste se agrega a la caché de ensamblados global si especifica esta opción.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué ocurre con los artefactos durante la implementación de aplicaciones](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [Cómo crear o agregar un artefacto](../core/how-to-create-or-add-an-artifact.md)   
 [Cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md)   
 [Cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md)