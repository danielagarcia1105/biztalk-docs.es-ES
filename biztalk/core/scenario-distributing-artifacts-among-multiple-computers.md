---
title: 'Escenario: Distribuir artefactos entre varios equipos | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying [artifacts], multiple computers
- examples, distributing
- examples, artifacts
- artifacts, distributing
- artifacts, examples
- deploying [artifacts], examples
- examples, deploying
ms.assetid: 7000cded-1fda-4276-b7f3-3f427f686f64
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abedc60ad13c7e8b2be3ce4caa7b8d34262b4e5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-distributing-artifacts-among-multiple-computers"></a>Escenario: Distribuir artefactos entre varios equipos
En este tema se describe el escenario de implementación de la aplicación cuando los artefactos de una aplicación se instalan de forma selectiva en diferentes equipos. Puede que desee hacerlo si quiere instalar determinados ensamblados u otros tipos de artefactos de una aplicación solo en determinados equipos de un grupo de BizTalk. Para ello, puede exportar los artefactos que se incluyen en una aplicación a varios archivos .msi, según los artefactos que desee instalar juntos en un equipo físico.  
  
 El siguiente diagrama muestra un archivo .msi que se importa en la base de datos de administración de BizTalk para el grupo de BizTalk 1. Esto crea la aplicación de procesamiento de pedidos y todos sus artefactos en ese grupo. Los artefactos de la aplicación se exportan, a continuación, a dos archivos .msi diferentes. Un archivo .msi contiene Assembly1, Certificate1 y Script1. El otro archivo .msi contiene Assembly2, Script2 y VirtualDirectory1.  
  
 Ambos archivos .msi se importan en 2 del grupo de BizTalk. Ya que ambos pertenecen a la aplicación de procesamiento de pedidos, todos los artefactos en los dos archivos .msi se importan en la misma aplicación, denominada procesamiento de pedidos en el nuevo grupo.  
  
 Además, los artefactos de la aplicación se instalan de los archivos .msi en los equipos del grupo que los ejecutarán. Observe que el archivo .msi que contiene el directorio virtual se instala en el servidor B y en el servidor C de BizTalk Server; los dos que ejecutan IIS.  
  
 ![Artefactos instalados en equipos diferentes](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de administración e implementación de aplicaciones](../core/application-deployment-and-management-scenarios.md)   
 [Cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md)   
 [Cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md)   
 [Cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md)