---
title: "Cómo habilitar SSL para SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, SSL
- managing [SSO], enabling SSL
- SSL
ms.assetid: 0d75962a-a0b0-4e69-8001-54e7df617006
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae2f3840cd2620f9c03a5b207b32d8bbd4feee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-ssl-for-sso"></a>Cómo habilitar SSL para SSO
Este comando se utiliza para habilitar Capa de sockets seguros (SSL) entre todos los servidores de inicio de sesión único (SSO) empresarial y la base de datos de SSO.  
  
### <a name="to-enable-ssl-for-enterprise-single-sign-on"></a>Para habilitar SSL para el inicio de sesión único empresarial  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad >**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssoconfig – setSSL \<sí/no >**, donde \< **sí/no**> indica si desea habilitar SSL en el sistema SSO.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Uso de SSO](../core/using-sso.md)