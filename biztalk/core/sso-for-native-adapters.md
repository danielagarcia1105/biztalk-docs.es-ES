---
title: SSO para adaptadores nativos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, SSO
- SSO, adapters
ms.assetid: d8527f0f-910c-42ce-9bd3-83ab6d4349c0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45aaf357d943853cc9504762437f554f1d28efb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278060"
---
# <a name="sso-for-native-adapters"></a>SSO para adaptadores nativos
El inicio de sesión único (SSO) empresarial le permite iniciar sesión sólo una vez al interoperar con diferentes sistemas informáticos o sitios Web. Esta característica de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite a los adaptadores de BizTalk proporcionar el Id. de usuario y las credenciales apropiadas para varias aplicaciones de la red que utilizan un mecanismo de autenticación común basado en sus credenciales de Microsoft Windows. Después de que Windows haya autenticado sus credenciales, no necesita proporcionar credenciales adicionales para conectarse a las aplicaciones.  
  
 SSO está disponible para los adaptadores de HTTP y SOAP aunque está deshabilitado de forma predeterminada. Para el adaptador de HTTP, puede configurar el puerto de envío y la ubicación de recepción para que utilicen SSO. Para el adaptador de SOAP, puede configurar solo la ubicación de recepción para que utilice SSO. Para los dos adaptadores, utilice la consola de administración de BizTalk Server para configurar SSO.  
  
 La autenticación en SSO se basa principalmente en la autenticación de Windows y en los grupos de Windows que se crearon en Active Directory. Todas las operaciones que completó el usuario o el administrador con SSO necesitan que Windows autentique primero el usuario o administrador.  
  
 Para obtener más información acerca del funcionamiento de SSO con los adaptadores de HTTP y SOAP, vea el tema apropiado en la sección Vea también.  
  
## <a name="see-also"></a>Vea también  
 [Uso de SSO](../core/using-sso.md)   
 [Adaptador de HTTP](../core/http-adapter.md)   
 [Adaptador de SOAP](../core/soap-adapter.md)