---
title: "Cómo establecer el servidor SSO con la utilidad de cliente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], selecting servers
- managing [SSO applications], selecting servers
- SSOClient [SSO], selecting servers
ms.assetid: a0f1038c-60c9-4e9d-a730-1ecfa036743b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49b2145320bd8e22b01d312d62246fa282fb534e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-the-sso-server-using-the-client-utility"></a>Cómo establecer el servidor SSO con la utilidad de cliente
Cada vez que utilice el cliente de SSO, en primer lugar debe seleccionar al usuario para el servidor de inicio de sesión único adecuado que contenga la información de configuración.  
  
### <a name="to-set-the-sso-server-for-a-user-using-the-client-utility"></a>Para establecer el servidor de SSO para un usuario con la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssoclient – server  *\<Single Sign-On Server\>***, donde \< *servidor de inicio de sesión único\>*  es el nombre del servidor Single Sign-On el usuario que va a conectar.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)   
 [Administración de aplicaciones afiliadas](../core/managing-affiliate-applications.md)