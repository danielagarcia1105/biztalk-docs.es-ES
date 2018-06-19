---
title: Supervisión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7effa38f-f9f2-40b7-8d8b-fa13cf94aa4f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c45bb70e3f92f4c85def07add4390a0451cb87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298908"
---
# <a name="monitoring"></a>Supervisión
De forma predeterminada, todos los de supervisión de BizTalk Server y tareas utilizan la cuenta de acción predeterminada cuando no hay que ninguna cuenta de ejecución específica definida para el destino en el perfil de ejecución de la cuenta de supervisión de BizTalk Server. Para configurar una cuenta de ejecución con el conjunto mínimo de permisos necesarios para que BizTalk Server con fines de supervisión, se requieren los permisos siguientes:  
  
-   La cuenta debe ser miembro del grupo de administradores integrado y el grupo de usuarios de monitores de rendimiento del equipo supervisado.  
  
-   La cuenta debe ser miembro del rol SysAdmin en la instancia SQL o instancias que hospeda las bases de datos y los trabajos para el grupo de BizTalk que se está supervisando.  
  
-   Para fines de supervisión de BizTalk Server, la cuenta debe ser una parte del grupo de operadores de BizTalk.  
  
-   Para ejecutar tareas a través de la consola de SCOM, la cuenta debe ser una parte del grupo de usuarios de la aplicación de BizTalk.  
  
-   Para realizar tareas administrativas, la cuenta debe ser una parte del grupo de administradores de BizTalk.