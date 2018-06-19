---
title: Cómo actualizar un recurso | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [resources], refreshing
- refreshing resources
- resources, refreshing
ms.assetid: d6ff7c9d-8aaf-42a4-b1a3-00c05f6ac869
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bee05b9f137bbec92eccfa217084b66f1e5bf8ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254548"
---
# <a name="how-to-refresh-a-resource"></a>Cómo actualizar un recurso
En este tema se describe cómo usar la consola de administración de BizTalk Server para actualizar un artefacto de recurso. La información del artefacto se actualiza en la base de datos de administración de BizTalk. Otra manera de hacerlo es mediante la adición del artefacto a la aplicación mediante BTSTask [comando AddResource](../core/addresource-command.md) con la opción de sobrescritura.  
  
 Los artefactos de recursos están incluidos en la carpeta Recursos de una aplicación. Puede ser conveniente actualizar un artefacto de recurso si realiza cambios en el archivo de origen y desea reemplazar el archivo en la aplicación con el archivo actualizado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-refresh-a-resource-artifact"></a>Para actualizar un artefacto de recurso  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene el artefacto de recurso para actualizar y, a continuación, expanda la aplicación que contiene el artefacto.  
  
3.  Haga clic en el **recursos** carpeta, menú contextual del archivo para actualizar y, a continuación, haga clic en **modificar**.  
  
4.  En el **modificar recursos** cuadro de diálogo, seleccione el archivo que desee actualizar y, a continuación, haga clic en **actualizar**.  
  
5.  Busque el archivo actualizado con el que desea reemplazar el archivo actual y, a continuación, haga clic en **Aceptar**.  
  
     El archivo actual se reemplaza por el archivo actualizado. En suma, la configuración, la configuración que aparece en el **opciones** pestaña de la **modificar recursos** cuadro de diálogo se aplican al archivo actualizado. Para obtener más información acerca de cómo cambiar esta configuración, haga clic en **ayuda** en el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Administrar secuencias de comandos previas y posteriores al procesamiento](../core/managing-pre-and-post-processing-scripts.md)   
 [Administrar ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [Administración de recursos](../core/managing-resources.md)