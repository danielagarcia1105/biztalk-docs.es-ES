---
title: Actualizar mediante el control de versiones en paralelo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9721a091-98ec-4f0b-ad1f-6ca184956e7c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36be63c9cef6a016ea4ad34d98a2750be86491d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974261"
---
# <a name="updating-using-side-by-side-versioning"></a>Actualizar mediante el control de versiones en paralelo
Si no puede programar el tiempo de inactividad, o tiene instancias de orquestación de ejecución muy prolongada que no se puede finalizar, control de versiones en paralelo puede ser necesario. En este tipo de actualización, las dos versiones de la misma aplicación o los artefactos de la aplicación ejecuten en paralelo. El tiempo de ejecución de .NET permite intrínsecamente para ejecución y que se implementen ensamblados con el mismo nombre pero de manera diferente con control de versiones y BizTalk Server también permite.  
  
 Control de versiones en paralelo de las aplicaciones es útil cuando desea implementar una actualización importantes de la aplicación de forma incremental, por ejemplo ponerlo a disposición un subconjunto de socios comerciales inicialmente, en lugar de a todos los asociados a la vez. Este enfoque permite continuar ejecutando la aplicación existente para prestar servicio a los usuarios que aún no están usando la versión nueva hasta que esté preparado para pasar totalmente a la nueva versión.  
  
 Las versiones de aplicaciones no se crean incrementando el número de versión de la misma manera que con las versiones de ensamblados. En su lugar, cree una nueva aplicación que tiene un nombre diferente de la aplicación original y rellenarlo con las nuevas versiones de los artefactos de la aplicación.  
  
 Puesto que en un mismo grupo de BizTalk pueden existir muchos tipos de artefactos, tales como ensamblados, es preciso incrementar el número de versión de todos los ensamblados que ya existan en el grupo para poder implementarlos en la nueva aplicación.  
  
 Para obtener una lista de paso a paso de las tareas necesarias para actualizar una aplicación o una orquestación mediante el control de versiones en paralelo, vea [lista de comprobación: actualización de un control de versiones de aplicaciones mediante Side-by-Side](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md) y [lista de comprobación: actualización de un Orquestación mediante el control de versiones en paralelo](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md). Para obtener instrucciones detalladas sobre cómo hacer la implementación en paralelo de las aplicaciones, consulte "[cómo implementar una nueva versión de una aplicación en ejecución en paralelo con una versión existente](http://go.microsoft.com/fwlink/?LinkId=155143) (<http://go.microsoft.com/fwlink/?LinkId=155143>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo actualizar una asignación mediante el control de versiones en paralelo](../technical-guides/how-to-update-a-map-using-side-by-side-versioning.md)  
  
-   [Cómo actualizar una canalización mediante el control de versiones en paralelo](../technical-guides/how-to-update-a-pipeline-using-side-by-side-versioning.md)  
  
-   [Actualización de un esquema mediante el control de versiones en paralelo](../technical-guides/updating-a-schema-using-side-by-side-versioning.md)