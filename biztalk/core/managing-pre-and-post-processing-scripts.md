---
title: Administrar secuencias de comandos previas y posteriores al procesamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 107ada12-fef2-4b56-8ff8-228c13761104
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18926a0c51e5ab5f65b32373d20b2931ccaa627d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262476"
---
# <a name="manage-pre--and-post-processing-scripts"></a>Administrar secuencias de comandos previas y posteriores al procesamiento

## <a name="overview"></a>Información general
Esta sección proporciona instrucciones sobre cómo utilizar la consola de administración de BizTalk Server o la herramienta de la línea de comandos BTSTask para administrar secuencias de comandos previas y posteriores al procesamiento. Puede crear una secuencia de comandos que deba ejecutarse cuando se importe, instale o desinstale (quite) una aplicación de BizTalk, y luego agregar esta secuencia de comandos a la aplicación. Al agregar una secuencia de comandos, debe especificar si es una secuencia de comandos previa al procesamiento (que se ejecuta antes de la importación o instalación, y después de la desinstalación), o posterior al procesamiento (que se ejecuta después de la importación o instalación, y antes de la desinstalación).  
  
 Si selecciona la secuencia de comandos al exportar la aplicación, la secuencia de comandos se incluye en el archivo .msi de la aplicación. Al instalar, desinstalar o importar la aplicación, la secuencia de comandos se ejecuta automáticamente, según cómo la haya escrito. Para obtener más información sobre cómo crear y utilizar secuencias de comandos, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Agregar una secuencia de comandos previa y posteriores al procesamiento a una aplicación](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [Cambiar la ubicación de destino de una secuencia de comandos previa y posteriores al procesamiento](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [Quitar una secuencia de comandos previa y posteriores al procesamiento de una aplicación](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)