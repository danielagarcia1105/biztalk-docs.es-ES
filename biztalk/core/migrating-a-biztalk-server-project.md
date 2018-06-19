---
title: Migrar un proyecto de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a4dde72-6555-4bf6-b90e-676aa65312ff
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2752203b0498a6cd5a4a8b6df6bc558c444e355
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973466"
---
# <a name="migrating-a-biztalk-server-project"></a>Migración de un proyecto de BizTalk Server
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] los proyectos desarrollan para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pueden migrar a los entornos más recientes mediante el uso de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] conversión. Para obtener una lista de las versiones de migración compatibles, consulte [admiten rutas de acceso de actualización y guías de instalación](http://social.technet.microsoft.com/wiki/contents/articles/28554.biztalk-server-supported-upgrade-paths-and-installation-guides.aspx).  
  
## <a name="biztalk-project-changes-after-running-the-conversion-wizard"></a>Cambios de proyectos de BizTalk después de ejecutar al Asistente para conversión  
 La tabla siguiente se muestra cómo [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] cambian los nombres de configuración del proyecto y dónde cambiar la posición de algunas propiedades de configuración específicas después de que el proyecto se convierte en una más reciente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto. La mayoría de los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-configuración del proyecto relacionados se encuentra en el **implementación** pestaña del Diseñador de proyectos.  
  
|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] Proyecto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Proyecto|  
|------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|  
|**Incrustar información de seguimiento** propiedad de configuración de salida|**Definir constante TRACE** opción de generación el **generar** pestaña del Diseñador de proyectos|  
|**Generar información de depuración** propiedad de configuración de salida|**Definir constante DEBUG** opción de generación el **generar** pestaña del Diseñador de proyectos|  
|**Compatibilidad con BPEL** propiedad de configuración de generación de código|**Compatibilidad con BPEL** propiedad de generación en la ventana de propiedades del proyecto de código|  
  
> [!NOTE]
>  Proyectos de BizTalk ahora tienen dos tipos de compilación: **versión** y **depurar**, que sustituyen **desarrollo** y **implementación** de versiones anteriores versiones. Sin embargo, continuarán viendo el **desarrollo** y **implementación** configuraciones para los proyectos que se migran desde [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)].  
  
> [!CAUTION]
>  Solo *.btproj y \*. se copian los archivos de proyecto btproj.user como resultado de elegir la copia de seguridad de la opción durante la conversión. Es necesario realizar una copia de seguridad manual de los demás archivos.  
  
> [!CAUTION]
>  Las personalizaciones de elementos generados automáticamente, como los archivos XSD y ODX, se perderán durante la conversión. Esto se aplica a los archivos XSD generados cuando se agrega una referencia web también a un proyecto BizTalk.  
  
## <a name="project-migration-and-delay-signing"></a>Migración de proyectos y retraso de firma  
 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] los proyectos que utilizan [retrasar la firma de](http://go.microsoft.com/fwlink/p/?LinkId=140992) puede producir un error durante el proceso de compilación después de que se está convirtiendo para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esto puede suceder si **generar ensamblados de serialización** de compilación para la configuración del proyecto migrado no está establecida en **desactivar**.  
  
## <a name="project-migration-and-msmqt"></a>Migración de proyectos y MSMQT  
 MSMQT ha dejado de formar parte de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre cómo esto puede afectar a la migración de proyecto, vea el tema [degradación de MSMQT](../core/msmqt-deprecation.md).  
  
## <a name="project-conversion-requires-the-project-and-solution-file"></a>La conversión del proyecto requiere el proyecto y el archivo de solución  
 Si trata de convertir un proyecto de [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y no tiene el archivo de solución, recibirá el siguiente error:  
  
 **Error al convertir el archivo de proyecto. Elemento secundario \<BIZTALK\> del elemento \<VisualStudioProject\> no es válido.**  
  
 La conversión del proyecto requiere el archivo de solución (.sln) del proyecto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si no se encuentra disponible el archivo de solución, deberá crear uno con [!INCLUDE[btsVStudioNet2005](../includes/btsvstudionet2005-md.md)] y agregar el proyecto [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] a la solución. A continuación, ejecute el asistente para conversión de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
> [!NOTE]
>  Es posible que pueda convertir el proyecto mediante el archivo de proyecto (.btproj) con Visual Studio.