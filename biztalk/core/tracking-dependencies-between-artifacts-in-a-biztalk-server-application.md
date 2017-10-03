---
title: "Seguimiento de dependencias entre artefactos en una aplicación de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 503cadfc-08e5-4b34-94a2-3b0ea6ad6228
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3edd162075f1ad660c005fd387ac9bc6c8c79e38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tracking-dependencies-between-artifacts-in-a-biztalk-server-application"></a>Seguimiento de dependencias entre artefactos en una aplicación de BizTalk Server
Una aplicación típica de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implica varios artefactos como orquestaciones, puertos de envío, ubicaciones de recepción, canalizaciones, esquemas, mapas, etc. Todos estos artefactos dependen unos de otros. La siguiente lista muestra estas dependencias.  
  
|Artefactos|Orquestación|Puerto de envío|Puerto de recepción|Ubicación de recepción|Canalización|Mapas|Esquemas|  
|---------------|-------------------|---------------|------------------|----------------------|--------------|----------|-------------|  
|**Orquestación**||![Usar](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![Usar](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||||  
|**Puerto de envío**|![Utilizado por](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![Usar](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|![Usar](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**Puerto de recepción**|![Utilizado por](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|||![Usar](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![Usar](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**Ubicación de recepción**|||![Utilizado por](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![Usar](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|||  
|**Canalización**||![Utilizado por](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![Utilizado por](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||  
|**Mapa**||![Utilizado por](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|![Utilizado por](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![Usar](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|  
|**Esquema**||||||![Utilizado por](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||  
  
 Como sugiere la tabla, hay dos modos de dependencias.  
  
-   Usa (![mediante](../core/media/dependency-using-icon.png "Dependency_Using_Icon")): un artefacto usa otro artefacto, por ejemplo, un puerto de envío utiliza una canalización.  
  
-   Usado por (![utilizado por](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")): un artefacto es usado por otro artefacto, por ejemplo, un puerto de envío se utiliza una orquestación.  
  
 Con estas dependencias, si necesita actualizar un artefacto, debe saber qué artefactos de la jerarquía de dependencias debe detenerse o volver a implementarse. Esta información de dependencia está disponible en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración muestra la información de dependencia en ambos modos: si un artefacto usa otro artefacto *como* si un artefacto es usado por otro artefacto.  
  
## <a name="viewing-dependencies"></a>Visualización de dependencias  
 Esta sección proporciona información sobre cómo ver la dependencia usando la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  El siguiente procedimiento usa instrucciones sobre cómo ver una dependencia de una orquestación. También puede seguir las mismas instrucciones para ver la dependencia de otros artefactos.  
  
#### <a name="to-view-dependencies-for-an-artifact"></a>Para ver dependencias de un artefacto  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda una aplicación y, a continuación, haga clic en **orquestaciones**. En el panel central, haga clic en la orquestación para la que desea ver las dependencias y, a continuación, haga clic en **ver dependencias**.  
  
2.  Hacia la parte inferior del panel, el **estadísticas de dependencias** panel, muestra dos categorías de dependencias. El **usado por** categoría muestra los artefactos que usan esa orquestación específica. El **Using** categoría muestra los artefactos que se usan por la orquestación específica.  
  
     ![Dependencias de una orquestación](../core/media/dependency-orchestration.jpg "Dependency_Orchestration")  
  
     Dado que no hay otro artefacto es dependiente de una orquestación, el **usado por** categoría de dependencia de una orquestación está vacía. Sin embargo, en la **Using** modo de dependencia, la imagen muestra que la orquestación es dependiente de un puerto de envío. El número de dependencias se muestra como hipervínculo que, cuando se hace clic en él, solo muestra los puertos de los que depende la orquestación. Tenga en cuenta que, incluso después de hacer clic en el vínculo para mostrar los puertos de envío, el panel de dependencias sigue mostrando las estadísticas de dependencias de la orquestación y no del puerto de envío.  
  
     Puede haga clic en los puertos de envío y, a continuación, haga clic en **ver dependencias** nuevo, para ver la matriz de dependencia para el puerto de envío. Puede ver el árbol de dependencias de cualquier nivel. El nivel en el que se encuentre en el árbol de dependencia se muestra con un desglose en la parte superior del panel, como se muestra en la imagen anterior.  
  
     ![Pan de navegación para ver un árbol de dependencia](../core/media/dependency-breadcrumbs.jpg "Dependency_BreadCrumbs")