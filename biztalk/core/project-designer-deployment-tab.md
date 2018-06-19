---
title: 'Diseñador de proyectos: Pestaña de implementación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- properties, Configuration database [BizTalk Server]
- Redeploy property
- configuration properties [deployment], Server property
- Server property
- configuration properties [deployment], Install to Global Assembly Cache (GAC) property
- properties, Management database
- Install to Global Assembly Cache (GAC) property
- Configuration database [BizTalk Server], properties
- Management database, properties
- Administration Group property
- configuration properties [deployment], Redeploy property
- configuration properties [deployment], Management database property
- configuration properties [deployment], Administration Group property
ms.assetid: 5b64f99c-4ec6-4ed3-8590-46420e2f75b8
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972f3956a19d66d47238ee8170584b4faf6ba886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264948"
---
# <a name="project-designer-deployment-tab"></a>Diseñador de proyectos: pestaña Implementación
El **implementación** ficha de propiedades del Diseñador de proyectos le permite configurar los atributos de implementación del proyecto de BizTalk. Debe configurar tanto el **Server** y la **base de datos de configuración** (también conocido como la base de datos de administración de BizTalk) propiedades como un conjunto para la implementación se realice correctamente.  
  
## <a name="application-name"></a>Application Name  
 Especificar la aplicación de BizTalk en la que se va a implementar el ensamblado. Si está vacío, el proyecto se implementará en la aplicación predeterminada.  
  
## <a name="configuration-database"></a>Base de datos de configuración  
 Este campo se utiliza para especificar el nombre de la base de datos de configuración de BizTalk para el ensamblado implementado. Esto es aplicable si ha configurado el proyecto de BizTalk como un proyecto de implementación.  
  
> [!NOTE]
>  La base de datos de configuración de BizTalk también se llama base de datos de administración de BizTalk.  
  
 El nombre de la base de datos de configuración predeterminada es BizTalkMgmtDb.  
  
## <a name="server"></a>Server  
 Éste es el nombre del servidor en el que está ubicado el Repositorio de configuración (también conocido como base de datos de administración o de configuración de BizTalk). El proyecto de BizTalk se implementa en este servidor si configura el proyecto de BizTalk como "Implementación".  
  
## <a name="redeploy"></a>Volver a implementar  
 Usa el **volver a implementar** propiedad para determinar si se debe eliminar la configuración existente y volver a crear la configuración cada vez que implemente el ensamblado. El valor predeterminado es `True`.  
  
## <a name="install-to-global-assembly-cache"></a>Instalar caché de ensamblados total (GAC)  
 Usa el **instalar en la caché Global de ensamblados** propiedad para indicar si [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] necesita instalar el ensamblado de BizTalk a la caché de ensamblados global (GAC).  
  
## <a name="restart-host-instances"></a>Reiniciar instancias de host  
 Si establece **reiniciar instancias de Host** a **True**, las instancias de host en el equipo local se reiniciará cuando se implementa el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Esto resulta útil durante el ciclo de desarrollo cuando se hacen cambios y, con frecuencia, vuelve a realizarse la implementación; no tendrá que reiniciar manualmente las instancias de host relacionadas.  
  
 Si no reinicia las instancias de host relacionadas, los últimos cambios no se verán reflejados en la aplicación de BizTalk porque es posible que la versión antigua esté aún almacenada en la memoria caché. Reiniciar la instancia de host purga los ensamblados almacenados en caché.  
  
## <a name="enable-unit-testing"></a>Habilitar pruebas de unidades  
 Se especifica si se va a habilitar la prueba de unidad para el proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [Ventana de propiedades de proyecto de BizTalk](../core/biztalk-project-properties-window.md)