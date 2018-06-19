---
title: Cómo agregar un artefacto de 64 bits a una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, 64-bit support
- scripts, 64-bit support
- virtual directories, 64-bit support
- artifacts, applications
- 64-bit support, COM components
- 64-bit support, virtual directories
- applications, artifacts
- 64-bit support, scripts
- 64-bit support, artifacts
- COM components, 64-bit support
- BizTalk Server, 64-bit support
- applications, 64-bit support
ms.assetid: 46aca7d4-c5be-421e-b16d-7f3095c8cc67
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69707401fee8b7f48b30a79bab166a9f22c29a89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246628"
---
# <a name="how-to-add-a-64-bit-artifact-to-an-application"></a>Cómo agregar un artefacto de 64 bits a una aplicación
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]incluye compatibilidad con aplicaciones de 64 bits. Esto significa que puede agregar artefactos de 64 bits a una aplicación de BizTalk de la misma manera que los artefactos de 32 bits; no obstante, se pueden producir los siguientes problemas al instalar los siguientes artefactos de 64 bits en un equipo de 32 bits:  
  
-   **Directorio virtual desde un servidor Web que se ejecuta un proceso de trabajo de 64 bits.** el directorio virtual se instalará en un equipo de 32 bits pero es posible que no funcione correctamente. Se registrará una falta de coincidencia.  
  
-   **Componentes no administrados COM o COM + administrados marcan como 64 bits.** estos componentes no se instalarán en un equipo de 32 bits.  
  
-   **secuencias de comandos de 64 bits guardados como archivos .exe.** es posible que este tipo de secuencias de comandos no funcione correctamente.  
  
 Para obtener instrucciones generales sobre cómo agregar artefactos, vea [cómo crear o agregar un artefacto](../core/how-to-create-or-add-an-artifact.md). Para obtener instrucciones sobre cómo agregar tipos de artefactos específicos, consulte [administrar artefactos](../core/managing-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)   
 [Cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md)