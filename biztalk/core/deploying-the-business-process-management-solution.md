---
title: Implementar la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, process management solution tutorial
- process management solution tutorial, deploying
ms.assetid: e033e0cd-0333-4f16-a4a0-eaae9ce98fcc
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0a61048ecb90876b251657f00361c35587a7ec1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239444"
---
# <a name="deploying-the-business-process-management-solution"></a>Implementar la solución de administración de procesos empresariales
La solución de administración de procesos empresariales (BPM) muestra una forma de construir un administrador de procesos en una aplicación de BizTalk. La solución utiliza un componente para seleccionar y controlar la secuencia de fases en el procesamiento de pedidos. La solución toma un pedido, que puede ser de un nuevo servicio, una actualización o la terminación del servicio, lo registra y lo confirma antes de pasarlo para su procesamiento. El procesamiento consta de uno o más fases de control del pedido. Por último, la solución devuelve una respuesta a la solicitud de pedido original.  
  
 Esta guía de implementación describe cómo instalar y ejecutar la solución de administración de procesos empresariales en un equipo de desarrollo y varios servidores de producción.  
  
 Para obtener más información acerca de la solución de administración de procesos empresariales, vea [descripción de la solución de administración de procesos empresariales](../core/understanding-the-business-process-management-solution.md).  
  
 **Instrucciones para el lector**  
  
 En este documento se supone que el usuario ya conoce BizTalk Server, Windows Server y Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. También supone que comprende conceptos básicos acerca de la integración de aplicaciones de negocio y servicios Web. Además, recomendamos que esté familiarizado con la generación de aplicaciones mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] así como con la creación de proyectos, establecimiento de referencias y utilización del modo de depuración para depurar y probar su solución. Para obtener más información acerca de los requisitos previos conocimientos y para profesionales de TI y desarrolladores, consulte [Prerequisite conocimientos y](../core/prerequisite-skills-and-knowledge5.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración del equipo del desarrollador para la solución de administración de procesos empresariales](../core/developer-machine-setup-for-the-business-process-management-solution.md)