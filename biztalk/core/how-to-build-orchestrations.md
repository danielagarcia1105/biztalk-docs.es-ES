---
title: Cómo generar orquestaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, orchestrations
- building, solutions
- building, projects
- solutions, building
- projects, building
- orchestrations, building
ms.assetid: f12d5da0-fbae-4f0e-85bf-1ca2e9bf7d62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9000c986e95270328d9c31ef4f5e3bda7f1576e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987333"
---
# <a name="how-to-build-orchestrations"></a>Cómo generar orquestaciones
Tras finalizar el diseño de una orquestación, se crea el proyecto de BizTalk en un ensamblado que encapsula una orquestación ejecutable.  
  
 Durante el proceso de generación, el Diseñador de orquestaciones de BizTalk examina todas las formas para determinar si están completas y son correctas, y presenta un error en la lista de tareas si no lo son.  
  
 Existen varias opciones para generar aplicaciones en Visual Studio:  
  
- Puede generar la solución completa en la que resida su orquestación.  
  
- Puede generar un único proyecto dentro de la solución.  
  
- Puede omitir la orquestación al generar el proyecto o solución.  
  
  Si desea generar otros componentes, incluidas otras orquestaciones, pero no desea generar una orquestación específica, puede indicar en las propiedades del archivo .odx de la orquestación que no desea generarla y ésta se omitirá.  
  
### <a name="to-build-an-orchestration"></a>Para generar una orquestación  
  
-   Tras crear una orquestación, debe generar el proyecto de BizTalk que la contiene para poder probarla o usarla. Puede generar la solución completa o un único proyecto dentro de la solución.  
  
### <a name="to-build-a-solution"></a>Para generar una solución  
  
-   En el Explorador de soluciones, haga clic en la solución y seleccione **compilar solución**.  
  
### <a name="to-build-a-project"></a>Para generar un proyecto  
  
-   Haga clic en un proyecto y seleccione **compilar**.  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a>Para generar un proyecto o solución sin compilar una orquestación específica  
  
-   Haga clic en el archivo .odx correspondiente a la orquestación y, en la ventana Propiedades, haga clic en el **acción de compilación** propiedad y seleccione **ninguno**.