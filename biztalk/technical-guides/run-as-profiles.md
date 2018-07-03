---
title: Perfiles de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ac0a0c-91d8-4d12-aa40-2ad2e29ec784
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a1281fa77956d96e4461a91fffb737499327ef2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982093"
---
# <a name="run-as-profiles"></a>Perfiles de ejecución
Cuando el módulo de administración de BizTalk Server Core Library se importa por primera vez, crea dos nuevos perfiles de ejecución:  
  
- **Cuenta de detección de servidor BizTalk Server**. Este perfil se asocia con todas las detecciones de componentes de la función de servidor BizTalk Server.  
  
- **Cuenta de supervisión de BizTalk Server**. Este perfil está asociado con todos los monitores y tareas.  
  
  Forma predeterminada, todas las detecciones, monitores y tareas definidas en el valor predeterminado de módulos de administración de BizTalk Server al uso de las cuentas definidas en la "Cuenta de acción predeterminada" perfil de ejecución.  Si la cuenta de acción predeterminada de un sistema concreto no tiene los permisos necesarios para detectar o supervisar BizTalk, esos sistemas pueden estar limitados por credenciales más específicas en el BizTalk Server como perfiles de ejecución, que sí tienen acceso a BizTalk Server.  
  
  Los siguientes son los pasos genéricos para configurar perfiles de ejecución de BizTalk Server:  
  
### <a name="to-configure-run-as-profiles"></a>Para configurar perfiles de ejecución  
  
1.  Identifique los nombres de los equipos de destino donde la cuenta de acción predeterminada no tiene derechos suficientes para supervisar BizTalk Server.  
  
2.  Para cada sistema crear o usar un conjunto existente de credenciales que tengan al menos los privilegios de BizTalk Server se describe en el [entornos con pocos privilegios](../technical-guides/low-privilege-environments.md) sección de esta guía del módulo de administración.  
  
3.  Para cada conjunto de credenciales identificado en el paso 2, asegúrese de que existe una correspondiente cuenta de ejecución en el grupo de administración. Si es necesario, cree la cuenta de ejecución.  
  
4.  Configurar las asignaciones entre los destinos y las cuentas de ejecución en el **cuentas de ejecución** pestaña de cada uno de los perfiles de ejecución.