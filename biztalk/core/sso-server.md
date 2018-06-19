---
title: Servidor de SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, tasks
- Master Secret server, SSO
- servers, SSO
- SSO, servers
- SSO, Master Secret server
ms.assetid: 40240d6b-b7d1-48fb-b750-be0e380d52e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f2f24911a0336a734125436d97dbce6f9e0b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277620"
---
# <a name="sso-server"></a>Servidor de SSO
El servidor de inicio de sesión único (SSO) empresarial puede realizar cualquiera de las tareas siguientes:  
  
-   **Funciones como el servidor secreto principal.** El servidor secreto principal contiene una copia persistida del secreto o clave principal que se utiliza para cifrar las credenciales en el sistema de SSO. Aunque el servidor secreto principal puede actuar como servidor para búsquedas y administración, por motivos de seguridad se recomienda que utilice este servidor para actuar sólo como servidor secreto principal. Para obtener más información acerca de las funciones que realiza el servidor secreto principal, consulte [servidor secreto principal](../core/master-secret-server.md).  
  
-   **Realiza operaciones administrativas.** Los administradores de SSO pueden utilizar cualquier servidor de inicio de sesión único para realizar tareas administrativas, como administrar aplicaciones afiliadas, establecer credenciales de usuario y que administrar asignaciones de usuario.  
  
-   **Realiza operaciones de búsqueda.** El servidor de SSO utiliza el componente de tiempo de ejecución para buscar las credenciales de usuario.  
  
-   **Emite y canjea vales.** El servidor de SSO también emite y canjea vales de SSO.  
  
-   **Sincronización de contraseñas.** Puede crear y administrar adaptadores de sincronización de contraseñas en el servidor de SSO.  
  
## <a name="see-also"></a>Vea también  
 [Uso de SSO](../core/using-sso.md)   
 [Instalación de SSO](../core/installing-sso.md)