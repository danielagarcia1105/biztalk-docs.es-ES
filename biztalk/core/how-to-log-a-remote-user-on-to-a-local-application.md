---
title: Cómo registrar un usuario remoto en una aplicación Local | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 886ee7cb-e6ba-476a-bea9-4bb4c22bf94e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f638007c3c4eb1f85a5b5a701dd2b456c2d220d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254220"
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a>Cómo registrar un usuario remoto en una aplicación Local
La otra gran característica del servicio de inicio de sesión único empresarial (ENTSSO) es que admite un proceso iniciado por host (HIP). ENTSSO interactúa con HIP cuando un usuario remoto intenta obtener acceso a un recurso local de Windows. Si utiliza ENTSSO, puede recibir la solicitud del usuario de host y solicitar acceso a la aplicación local de Windows.  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a>Inicie sesión un usuario remoto en una aplicación de Windows local  
  
1.  Espere a recibir la solicitud del usuario remoto.  
  
     Es responsabilidad suya determinar cómo obtener una solicitud del usuario remoto.  
  
2.  Solicite mediante `ISSOLookup2.LogonExternalUser` que se dé al usuario remoto acceso a la aplicación afiliada especificada.  
  
     `LogonExternalUser` se transporta en el nombre de la aplicación a la que el usuario externo desea obtener acceso, en el nombre del usuario externo, en las credenciales asociadas al usuario externo y en cualquier marca pertinente. Si se realiza correctamente, `LogonExternalUser` devuelve un identificador a un token de acceso de Windows.  
  
     El usuario remoto debe estar identificado ya en la base de datos de inicio de sesión único (SSO), tener las credenciales en la base de datos y estar asociado con una aplicación afiliada. En caso contrario, `LogonExternalUser` devuelve un error. Puede mantener los nombres y credenciales de usuario actualizados mediante Sincronización de contraseñas.  
  
     Además, debe tener habilitada la transición de protocolo.  
  
3.  Use el identificador de Windows que devuelve `LogonExternalUser` para suplantar al usuario que representa el token.  
  
## <a name="see-also"></a>Vea también  
 [Cómo registrar un usuario Local en una aplicación distinta de Windows](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md)   
 **ISSOLookup2.LogonExternalUser (método)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]