---
title: Antes de importar el módulo de administración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3c13dd-613a-4885-a5d2-ad3ee492ff25
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c11849c379a4654bed78a8e86ba263e6da428c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299452"
---
# <a name="before-you-import-the-management-pack"></a>Antes de importar el módulo de administración
Como práctica recomendada, debe importar el módulo de administración de Windows Server para el sistema operativo que esté utilizando. Antes de importar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración, realice las acciones siguientes:  
  
-   Asegúrese de que Operations Manager 2007 R2/2012 está instalado.  
  
-   Debe ser miembro del grupo Administradores de SCOM o el grupo de autores de SCOM. Los administradores locales en el servidor de administración de SCOM tienen todos los derechos y permisos que se conceden al grupo de administradores de SCOM.  
  
-   Configurar los servidores BizTalk Server como los equipos administrados de Operations Manager mediante la implementación de los agentes de SCOM en cada servidor de BizTalk que desea administrar. La implementación del agente SCOM implica las siguientes tareas:  
  
    -   Instale al agente SCOM.  
  
    -   Cree una cuenta de agente de BizTalk SCOM.  
  
    -   Configurar un **ejecución** cuenta. Agregue la cuenta de ejecución a los siguientes grupos:  
  
        -   Grupos de BizTalk.  
  
        -   Administradores de BizTalk.  
  
        -   Administradores SSO.  
  
        -   Administradores afiliados de SSO.  
  
    -   Iniciar la supervisión.  
  
-   En consola de Operations Manager, los equipos administrados se encuentran en un estado correcto.  
  
-   Configurar las cuentas de usuario que tienen que estar configurado, como perfiles ni requiere cuentas de ejecución. Este módulo de administración incluye perfiles de ejecución denominados "Cuenta de supervisión de BizTalk Server" y "Cuenta de detección de BizTalk Server" para definir credenciales específicas por agentes. Es podrán que deba utilizar este perfil de ejecución para algunos agentes después de importar el módulo de administración.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Archivos de este módulo de administración](../technical-guides/files-in-this-management-pack.md)  
  
-   [Módulos de administración adicionales recomendados](../technical-guides/recommended-additional-management-packs.md)