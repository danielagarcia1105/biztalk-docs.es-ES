---
title: ¿Qué ocurre cuando se implementa un ensamblado desde Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 421df529-1ddb-4f49-a40a-c06f2a434ffc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c74336e90e1ac58088de0d528695dbfed617d9b5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985269"
---
# <a name="what-happens-when-you-deploy-an-assembly-from-visual-studio"></a>¿Qué ocurre cuando se implementa un ensamblado desde Visual Studio?
En este tema se describe lo que sucede al implementar ensamblados desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en una aplicación de BizTalk en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Puede implementar un proyecto de forma individual o todos los proyectos al mismo tiempo en una solución. Antes de implementar un proyecto, ya sea por separado o como parte de una solución, debe especificar la aplicación en el que se va a implementar su ensamblado en las propiedades del proyecto, como se describe en [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md). Cuando implementa un proyecto o una solución en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], los ensamblados se crean y se implementan automáticamente en la aplicación especificada. Si el nombre de una aplicación que ya existe en el grupo de BizTalk local es el mismo que el de la aplicación especificada en las propiedades del proyecto, el ensamblado se implementa en la aplicación que ya existe; en caso contrario, se crea una nueva aplicación con el nombre especificado y el ensamblado se implementa en ella. Como parte de este proceso, el ensamblado junto con las orquestaciones, canalizaciones, esquemas y asignaciones que contiene (denominados "artefactos") se importan a la base de datos de administración de BizTalk local y se asocian en ella con la aplicación especificada.  
  
 Puede implementar los proyectos en una solución en la misma aplicación de BizTalk o en aplicaciones de BizTalk diferentes, incluso cuando implementa los proyectos en una solución al mismo tiempo. En el diagrama siguiente se ilustra la implementación de tres ensamblados, que una solución de BizTalk contiene en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en dos aplicaciones de BizTalk diferentes.  
  
 ![Implementar ensamblados de BizTalk](../core/media/visualstudiodeploy.gif "VisualStudioDeploy")  
  
 Después de implementar un proyecto o una solución, puede ver y administrar los ensamblados y sus artefactos desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o mediante la herramienta de la línea de comandos BTSTask.  
  
## <a name="destination-locations"></a>Ubicaciones de destino  
 Cuando se implementan ensamblados desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], la ubicación de destino de un ensamblado toma de forma predeterminada la ubicación de origen del ensamblado. Cuando se instala o exporta un ensamblado desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], si el entorno de "procedencia" no es el mismo que el de "destino", se producirá un error en la instalación. Por ejemplo, si la ubicación de origen es D:[ruta]/[nombre de archivo] y el equipo de instalación de destino no dispone de una unidad "D", se producirá un error en la instalación.  
  
 Este comportamiento contrasta con la acción de agregar un recurso mediante el administrador de BizTalk, en cuyo caso, la ubicación de destino predeterminada es %BTAD_InstallDir%. Esta variable de entorno se expande en el directorio de instalación especificado durante la propia instalación.  
  
 Para solucionar este problema, siga el procedimiento siguiente:  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], implemente el ensamblado.  
  
2. Una vez implementado, abra el administrador de BizTalk.  
  
3. Modifique la ubicación de destino como corresponda. Por ejemplo, cambie la ubicación de destino a %BTAD_InstallDir%.  
  
   Una vez que haya modificado la ubicación de destino, se usará la nueva de forma predeterminada para las nuevas implementaciones posteriores del mismo ensamblado.  
  
   Para obtener más información, consulte [cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).  
  
## <a name="deploying-solutions-vs-projects"></a>Implementación de soluciones de vs. Proyectos  
 Se recomienda encarecidamente implementar siempre una solución en vez de un proyecto individual. Cuando implementa un proyecto individual y existen dependencias entre el ensamblado que implementa y otro, debe efectuar una serie de pasos manuales para completar la implementación. Sin embargo, cuando implementa una solución, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lleva a cabo automáticamente todos los pasos para administrar las dependencias que existan entre ensamblados. Para obtener más información, consulte [cómo volver a implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md).  
  
 El siguiente diagrama ilustra los pasos que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tarda en volver a implementar los ensamblados que tienen dependencias cuando implementa una solución.  
  
 ![Implementar ensamblados en una solución](../core/media/deployassemblies.gif "DeployAssemblies")  
  
## <a name="see-also"></a>Vea también  
 [Implementación de ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)