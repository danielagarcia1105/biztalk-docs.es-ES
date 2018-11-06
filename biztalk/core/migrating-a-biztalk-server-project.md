---
title: Migrar un proyecto de BizTalk Server | Microsoft Docs
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
ms.openlocfilehash: b0fd15de7aec81c046ab6b2fc23b6c63a1ec0615
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752708"
---
# <a name="migrating-a-biztalk-server-project"></a>Migración de un proyecto de BizTalk Server
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] los proyectos desarrollan para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueden migrarse a los entornos más recientes mediante el uso de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] conversión. Para obtener una lista de las versiones de migración admitidos, consulte [rutas de actualización compatibles y guías de instalación](http://social.technet.microsoft.com/wiki/contents/articles/28554.biztalk-server-supported-upgrade-paths-and-installation-guides.aspx).  

## <a name="biztalk-project-changes-after-running-the-conversion-wizard"></a>Cambios de proyectos de BizTalk después de ejecutar al Asistente para conversión  
 La tabla siguiente muestra cómo [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] cambian los nombres de configuración del proyecto, y donde reubicar algunas propiedades de configuración específica del proyecto se convierte en una más reciente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto. La mayoría de los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-opciones de proyecto relacionados se encuentran en el **implementación** ficha del Diseñador de proyectos.  


| [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] proyecto | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|             **Insertar información de seguimiento** propiedad de configuración de salida             |      **Definir constante TRACE** opción de compilación el **compilar** ficha del Diseñador de proyectos       |
|           **Generar información de depuración** propiedad de configuración de salida           |      **Definir constante DEBUG** opción de compilación el **compilar** ficha del Diseñador de proyectos       |
|              **Cumplimiento de BPEL** propiedad de configuración de generación de código              |       **Cumplimiento de BPEL** propiedad de generación en la ventana Propiedades del proyecto de código        |

> [!NOTE]
>  Proyectos de BizTalk ahora tienen dos tipos de compilación: **versión** y **depurar**, que reemplaza **desarrollo** y **implementación** de versiones anteriores versiones. Sin embargo, continuará ver el **desarrollo** y **implementación** configuraciones para los proyectos que se migran desde [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)].  
> 
> [!CAUTION]
>  Solo el \*.btproj y \*. son una copia de seguridad de archivos de proyecto btproj.user como resultado de elegir la copia de seguridad de la opción durante la conversión. Es necesario realizar una copia de seguridad manual de los demás archivos.  
> 
> [!CAUTION]
>  Las personalizaciones de elementos generados automáticamente, como los archivos XSD y ODX, se perderán durante la conversión. Esto se aplica a los archivos XSD generados cuando se agrega una referencia web también a un proyecto BizTalk.  

## <a name="project-migration-and-delay-signing"></a>Migración de proyectos y retraso de firma  
 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] los proyectos que utilizan [firma retardada](http://go.microsoft.com/fwlink/p/?LinkId=140992) puede producir un error durante el proceso de compilación después de que se va a convertir por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esto puede suceder si **generar ensamblados de serialización** ajuste de la compilación de la configuración del proyecto migrado no está establecida en **desactivar**.  

## <a name="project-migration-and-msmqt"></a>Migración de proyectos y MSMQT  
 MSMQT ha dejado de formar parte de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre cómo esto puede afectar a la migración de proyecto, vea el tema [degradación de MSMQT](../core/msmqt-deprecation.md).  

## <a name="project-conversion-requires-the-project-and-solution-file"></a>La conversión del proyecto requiere el proyecto y el archivo de solución  
 Si trata de convertir un proyecto de [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y no tiene el archivo de solución, recibirá el siguiente error:  

 **Error al convertir el archivo de proyecto. Elemento secundario \<BIZTALK\> del elemento \<VisualStudioProject\> no es válido.**  

 La conversión del proyecto requiere el archivo de solución (.sln) del proyecto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si no se encuentra disponible el archivo de solución, deberá crear uno con [!INCLUDE[btsVStudioNet2005](../includes/btsvstudionet2005-md.md)] y agregar el proyecto [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] a la solución. A continuación, ejecute el asistente para conversión de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  

> [!NOTE]
>  Es podrán que pueda convertir el proyecto con el archivo de proyecto (.btproj) con Visual Studio.