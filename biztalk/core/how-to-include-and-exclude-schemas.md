---
title: Cómo incluir y excluir esquemas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9206458-e5d6-48d7-87a6-9471ba60dca7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dfa1f610cef6e67f17ca14737c6ca853dd5cd16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254348"
---
# <a name="how-to-include-and-exclude-schemas"></a>Cómo incluir y excluir esquemas
Un archivo de esquema puede estar presente en una carpeta de proyecto de BizTalk, pero no incluirse en ese proyecto. En ese caso, se dice que el esquema se puede excluir del proyecto. Los esquemas excluidos no se compilan cuando se genera el proyecto de BizTalk. Este tema describe los pasos necesarios para incluir un esquema excluido en un proyecto de BizTalk, así como para excluir un esquema de un proyecto de BizTalk.  
  
### <a name="to-include-a-schema-in-a-biztalk-project"></a>Para incluir un esquema en un proyecto de BizTalk  
  
1.  En el Explorador de soluciones, abra el proyecto de BizTalk que contiene el esquema que va a incluir en la carpeta de proyecto.  
  
2.  Si todos los archivos no se muestran, en la **proyecto** menú, haga clic en **mostrar todos los archivos**.  
  
3.  En el Explorador de soluciones, haga clic en el esquema excluido que desea incluir y, a continuación, haga clic en **incluir en el proyecto**.  
  
     El icono del esquema excluido anteriormente en el Explorador de soluciones cambia de un esquema vacío a un icono de esquema normal.  
  
4.  Si lo desea, en la **proyecto** menú, haga clic en **mostrar todos los archivos** para ocultar todos los archivos en la carpeta del proyecto que no están incluidos en el proyecto.  
  
### <a name="to-exclude-a-schema-from-a-biztalk-project"></a>Para excluir un esquema de un proyecto de BizTalk  
  
-   En el Explorador de soluciones, haga clic en el esquema que desea excluir y, a continuación, haga clic en **excluir del proyecto**.  
  
     El esquema se excluye del proyecto de BizTalk.  
  
    > [!NOTE]
    >  Al excluir un esquema de un proyecto, éste no se quita del sistema de archivos. Sin embargo, el esquema no se incluye al generar el proyecto. Puede elegir si se debe o no mostrar archivos excluidos en la carpeta del proyecto, cambie la **mostrar todos los archivos** herramienta en la parte superior de la ventana Explorador de soluciones.  
  
    > [!NOTE]
    >  Si desea eliminar el esquema del sistema de archivos, así como quitar el archivo de esquema del proyecto, debe eliminar el esquema. Para obtener más información acerca de cómo eliminar esquemas, vea [eliminar esquemas](../core/how-to-delete-schemas.md).  
  
## <a name="see-also"></a>Vea también  
 [Administrar esquemas en proyectos](../core/managing-schemas-within-projects.md)