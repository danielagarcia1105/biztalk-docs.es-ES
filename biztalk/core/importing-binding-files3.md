---
title: "Importación de enlace 3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- target computer, cleaning
- importing binding files
- cleaning target computer
ms.assetid: 955bb3e1-3dbc-43ce-9126-205d838ae662
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1d95c40e3e556068e15a269ee4cbb7e995429a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a>Importar archivos de enlace
Antes de utilizar el servidor BizTalk Server para importar un archivo de enlace, compruebe lo siguiente:  
  
-   CLASSPATH apunta a una ubicación específica para los archivos específicos de JD Edwards. Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.  
  
-   Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.  
  
-   Las contraseñas del sistema de JD Edwards, si hay en la configuración se guardan como ***** en el archivo de enlaces. Para obtener más información, consulte [limitaciones de la implementación](../core/deployment-limitations2.md).  
  
> [!NOTE]
>  La implementación sobrescribe la configuración de ubicación de recepción. Al implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.  
  
## <a name="importing-the-binding-files"></a>Importar los archivos de enlace  
 Use el procedimiento siguiente para importar los archivos de enlace.  
  
#### <a name="to-import-the-binding-files"></a>Para importar archivos de enlace  
  
1.  En el **iniciar** menú, elija **archivos de programa**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server** Para iniciar la consola de administración de BizTalk Server.  
  
2.  Expanda Administración de BizTalk Server, **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Haga clic en la aplicación que desee, seleccione **importación**y, a continuación, haga clic en **enlaces**.  
  
4.  En el **importar enlaces** cuadro de diálogo, busque y seleccione los archivos de enlace y, a continuación, haga clic en **abiertos**.  
  
## <a name="cleaning-the-target-computer"></a>Limpiar el equipo de destino  
 Use el procedimiento siguiente para limpiar el equipo de destino.  
  
#### <a name="to-clean-the-target-computer"></a>Para limpiar el equipo de destino  
  
-   Quite los puertos de envío y las ubicaciones de recepción que están enlazados a la orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Crear controladores de envío de OneWorld JD Edwards](../core/creating-jd-edwards-oneworld-send-handlers.md)   
 [Implementación de puertos y ensamblados](../core/deploying-ports-and-assemblies4.md)