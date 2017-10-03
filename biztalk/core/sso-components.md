---
title: Componentes de SSO | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, synchronizing [SSO]
- SSO, components
- SSO, password synchronization
- SSO, sub-services
ms.assetid: e29e68df-f770-4220-a9f8-cb9323403017
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1111f1a0dfac47412ae28b58f93ddc51e1f562b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sso-components"></a>Componentes de SSO
Los subservicios del servicio de inicio de sesión único (SSO) empresarial son los siguientes:  
  
-   **Asignación.** Este componente asigna la cuenta de usuario en el sistema de Windows a cuentas de usuarios de los sistemas de servidor.  
  
-   **Búsqueda.** Este componente busca las credenciales de usuario en la base de datos de SSO en el sistema de servidor. Éste es el componente en tiempo de ejecución de SSO.  
  
-   **Administración.** Este componente administra las aplicaciones afiliadas y las asignaciones para cada aplicación afiliada.  
  
-   **Secreto.** Este componente genera el secreto principal y lo distribuye a los servidores de SSO del sistema. Sólo está activo en el servidor de inicio de sesión único (SSO) que actúa como servidor secreto principal.  
  
-   **Sincronización de contraseñas.** Este componente simplifica la administración de la base de datos de SSO y sincroniza las contraseñas en todos los directorios de usuario.  
  
## <a name="see-also"></a>Vea también  
 [Servidor de SSO](../core/sso-server.md)   
 [Instalación de SSO](../core/installing-sso.md)