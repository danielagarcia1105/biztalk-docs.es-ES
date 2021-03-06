---
title: Cómo quitar un certificado de una ubicación de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 717d41bf-4260-4df4-9d0a-07243bb9b12c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5af6db7dcbb9efb20846520db6b800f5c3226316
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991981"
---
# <a name="how-to-remove-a-certificate-from-a-receive-location"></a>Cómo quitar un certificado de una ubicación de recepción
En este tema se describe cómo usar la consola de administración de BizTalk Server para quitar un certificado de seguridad de una ubicación de recepción. Al hacerlo, la ubicación de recepción dejará de cifrar mensajes; los mensajes se enviarán en texto no cifrado. Cuando se quita un certificado de una ubicación de recepción, no se quita del almacén de certificados.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-remove-a-certificate-from-a-receive-location"></a>Para quitar un certificado de una ubicación de recepción  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee quitar un certificado de una ubicación de recepción.  
  
3. Expanda **ubicaciones de recepción**, haga clic en la ubicación de recepción, haga clic en **propiedades**y, a continuación, haga clic en **certificados**.  
  
4. Haga clic en **quitar certificado**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de ubicaciones de recepción](../core/managing-receive-locations.md)