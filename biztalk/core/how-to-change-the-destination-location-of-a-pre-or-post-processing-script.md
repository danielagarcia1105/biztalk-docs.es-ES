---
title: Cómo cambiar la ubicación de destino de una secuencia de comandos previa y posteriores al procesamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, file locations
- scripts, modifying
- managing [scripts], modifying
- managing [scripts], file locations
ms.assetid: 4a4fdaef-099f-4c29-9815-12404c7a2212
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eb4ba338790e301e54a9bf262a49808a0a55315
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249292"
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a>Cómo cambiar la ubicación de destino de secuencias de comandos previas y posteriores al procesamiento
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para cambiar la ubicación de destino de secuencias de comandos previas y posteriores al procesamiento. Se trata de la ubicación en la que se copia la secuencia de comandos cuando se instala la aplicación. Puede que desee cambiar la ubicación de destino al implementar una aplicación en otro entorno.  
  
> [!IMPORTANT]
>  Asegúrese de proporcionar una ubicación de destino para la secuencia de comandos que se va a ejecutar al desinstalar la aplicación. Si no se hace así, la secuencia de comandos no se copiará en el sistema de archivos local y, por tanto, no se ejecutará durante la desinstalación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a>Para modificar las propiedades de implementación de secuencias de comandos previas y posteriores al procesamiento  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk que contiene el script que se va a modificar y, a continuación, expanda la aplicación que contiene el script.  
  
3.  Haga clic en el **recursos** carpeta, haga clic en la secuencia de comandos y, a continuación, haga clic en **modificar**.  
  
4.  En **ubicación de destino**, escriba la ruta de acceso completa de la ubicación de destino, incluidos el nombre de archivo y, a continuación, haga clic en **Aceptar**. (Puede utilizar la variable de entorno %BTAD_InstallDir% en la ruta para especificar la carpeta de instalación de la aplicación).  
  
## <a name="see-also"></a>Vea también  
 [Administrar secuencias de comandos previas y posteriores al procesamiento](../core/managing-pre-and-post-processing-scripts.md)