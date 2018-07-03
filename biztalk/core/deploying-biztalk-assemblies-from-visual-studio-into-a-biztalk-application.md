---
title: Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: accef4b8-acdf-4043-8fd7-2db9ea752074
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4dcacede998ec0c921a379841e9b31389f2aa20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007189"
---
# <a name="deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application"></a>Implementar ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio
Implementar y volver a implementar ensamblados de BizTalk desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en una aplicación de BizTalk. Puede que desee realizarlo para probar la funcionalidad de los ensamblados que ha estado desarrollando y empaquételos para su entrega.  

## <a name="overview"></a>Información general  
 Las aplicaciones de BizTalk proporcionan una manera de ver y administrar los elementos, denominados "artefactos", que conforman una solución empresarial de BizTalk. Los artefactos incluyen ensamblados de BizTalk (que contienen orquestaciones, esquemas, asignaciones y canalizaciones), que puede implementar en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Los artefactos también incluyen elementos, tales como ensamblados, certificados, scripts, archivos Léame y directivas de .NET, que se agregan a la aplicación de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o la herramienta de línea de comandos BTSTask. El programador de soluciones o administrador de TI puede ver, empaquetar, implementar y administrar la aplicación y sus artefactos como entidad individual. Para obtener más información acerca de cómo crear, implementar y administrar aplicaciones de BizTalk, consulte [implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md).  
  
 Antes de generar e implementar un ensamblado de BizTalk, debe crear un proyecto en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], así como crear o agregar los elementos que desee incluir en el ensamblado. Es posible crear una solución en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] que contenga varios proyectos y, a continuación, generar e implementar todos los ensamblados a la vez en la misma aplicación o en aplicaciones diferentes. Para obtener instrucciones sobre cómo realizar estas tareas, consulte [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md).  
  
 Una vez finalizadas dichas tareas, puede generar, implementar y anular la implementación de los ensamblados de BizTalk siguiendo estos pasos, como se describe en los temas de esta sección:  
  
- Configure un archivo de clave de ensamblado de nombre seguro para cada proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
- Establezca las propiedades de implementación del proyecto, incluida la configuración de la opción Volver a implementar, para implementar de nuevo el ensamblado fácilmente.  
  
- Use el comando Implementar en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para generar los ensamblados de BizTalk incluidos en una solución e implementarlos en una aplicación de BizTalk. Otra opción consiste en usar el comando Implementar para generar e implementar un ensamblado en un solo proyecto, aunque no se recomienda hacerlo.  
  
- Después de probar la aplicación y realizar los cambios necesarios, use el comando Implementar en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para recompilar e implementar el ensamblado.  
  
- En caso de que sea necesario, instale el ensamblado en la caché de ensamblados global (GAC) o quite el ensamblado de la GAC.  
  
- Anule la implementación del ensamblado.  
  
  Después de implementar uno o varios ensamblados en una aplicación de BizTalk, puede completar la configuración de la aplicación e implementarla en la prueba y, a continuación, en el entorno de producción. Para obtener más información, consulte [tareas de desarrollo para la implementación de la aplicación de BizTalk](../core/development-tasks-for-biztalk-application-deployment.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Qué ocurre cuando se implementa un ensamblado desde Visual Studio](../core/what-happens-when-you-deploy-an-assembly-from-visual-studio.md)  
  
-   [Instalación de ensamblados en la caché de ensamblados global](../core/assembly-installation-in-the-gac.md)  
  
-   [Cómo configurar un archivo de clave de ensamblado de nombre seguro](../core/how-to-configure-a-strong-name-assembly-key-file.md)  
  
-   [Cómo establecer las propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md)  
  
-   [Cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [Cómo volver a implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [Cómo instalar o desinstalar un ensamblado en la GAC](../core/how-to-install-an-assembly-in-the-gac.md)  