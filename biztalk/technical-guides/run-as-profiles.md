---
title: "Perfiles de ejecución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ac0a0c-91d8-4d12-aa40-2ad2e29ec784
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69fa6c9401f606619b2fb8d22d95ded48c18a092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-as-profiles"></a>Perfiles de ejecución
Cuando el módulo de administración de BizTalk Server Core Library se importa por primera vez, se crean dos nuevos perfiles de ejecución:  
  
-   **Cuenta de detección de servidor BizTalk Server**. Este perfil está asociado con todas las detecciones de componentes de la función de servidor BizTalk Server.  
  
-   **Cuenta de supervisión de BizTalk Server**. Este perfil está asociado con todos los monitores y tareas.  
  
 Forma predeterminada, todas las detecciones, monitores y tareas definidas en el valor predeterminado de módulos de administración de BizTalk Server para usar las cuentas definidas en la "Cuenta de acción predeterminada" perfil de ejecución.  Si la cuenta de acción predeterminada de un sistema concreto no tiene los permisos necesarios para detectar o supervisar BizTalk, esos sistemas pueden estar limitados por credenciales más específicas en el BizTalk Server como perfiles de ejecución, que sí tienen acceso a BizTalk Server.  
  
 Éstos son los pasos genéricos necesarios para configurar perfiles de ejecución de BizTalk Server:  
  
### <a name="to-configure-run-as-profiles"></a>Para configurar perfiles de ejecución  
  
1.  Identifique los nombres de los equipos de destino que la cuenta de acción predeterminada no tiene derechos suficientes para supervisar BizTalk Server.  
  
2.  Para cada sistema crear o usar un conjunto existente de credenciales que tienen al menos los privilegios de BizTalk Server tratados en la [entornos con pocos privilegios](../technical-guides/low-privilege-environments.md) sección de esta guía del módulo de administración.  
  
3.  Para cada conjunto de credenciales identificado en el paso 2, asegúrese de que existe una correspondiente cuenta de ejecución del grupo de administración. Si es necesario, cree la cuenta de ejecución.  
  
4.  Configurar las asignaciones entre los destinos y las cuentas Ejecutar como en el **cuentas de ejecución** ficha de cada uno de los perfiles de ejecución.