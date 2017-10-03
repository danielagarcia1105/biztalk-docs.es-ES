---
title: Asignaciones de SSO | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO]
- maps [SSO], creating
- SSO, maps
ms.assetid: b44f7a0c-595c-49dc-9d75-2e76f29dca88
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98b44a1a9e8be3b275a4dd328c70323d79eb8a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sso-mappings"></a>Asignaciones de SSO
Cuando un administrador de inicio de sesión único (SSO) o un administrador afiliado de SSO define una aplicación afiliada, el administrador puede definirla como aplicación con asignaciones individuales o como aplicación de asignaciones de grupo.  
  
## <a name="individual-mappings"></a>Asignaciones individuales  
 Las asignaciones individuales de SSO permiten a usuarios y administradores crear una asignación de uno a uno entre usuarios de Windows y sus correspondientes credenciales ajenas a Windows. Cuando utiliza asignaciones individuales, los usuarios pueden administrar sus propias asignaciones. El sistema de SSO mantiene la relación de uno a uno para la cuenta de usuario de Windows y la cuenta de usuario ajena a Windows.  
  
 Los usuarios finales de Windows pueden crear y administrar sus propias asignaciones para aplicaciones de tipo individual. La misma aplicación afiliada puede actuar como una aplicación de tipo SSO iniciado por Windows y una aplicación de tipo SSO iniciado por host.  
  
> [!IMPORTANT]
>  Las asignaciones se pueden crear sólo para cuentas de dominio de Windows. No se puede asignar cuentas locales.  
  
> [!NOTE]
>  Sólo los usuarios individuales pueden obtener las credenciales a sus cuentas individuales cuando utilizan asignaciones individuales.  
  
## <a name="group-mapping"></a>Asignación de grupo  
 La asignación de grupo de SSO consiste en asignar un grupo de Windows que contenga varios usuarios de Windows a una sola cuenta en la aplicación afiliada.  
  
 Asimismo, puede especificar varias cuentas para la función de usuarios de aplicación de SSO. Cada cuenta que especifica se puede asociar a una cuenta externa. Por ejemplo, puede asignar un grupo de dominio a EXTERNALUSER1 y una cuenta de dominio individual a EXTERNALUSER2. Si el mismo usuario dispone de más de una asignación, se utiliza la primera asignación de usuarios de aplicación de SSO.  
  
 Una asignación de grupo sólo la puede crear o administrar un administrador de aplicaciones, un administrador afiliado de SSO o un administrador de SSO.  
  
 No puede especificar la misma aplicación de grupo para SSO iniciado por Windows y SSO iniciado por host.  
  
> [!IMPORTANT]
>  Las asignaciones se pueden crear sólo para cuentas de dominio de Windows. No se puede asignar cuentas locales.  
  
> [!IMPORTANT]
>  Cuando utiliza asignaciones de grupos, los miembros del grupo pueden obtener la información de credenciales para la asignación de grupo.  
  
## <a name="see-also"></a>Vea también  
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)   
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)