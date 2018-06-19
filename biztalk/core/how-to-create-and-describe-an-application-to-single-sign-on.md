---
title: Cómo crear y describir una aplicación para inicio de sesión único | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d717885-b132-4ba0-a93b-03377ac5eb97
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 423439795d9a3822427edbee2e062c3c0aa6bb80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249092"
---
# <a name="how-to-create-and-describe-an-application-to-single-sign-on"></a>Cómo crear y describir una aplicación para inicio de sesión único
Una tarea administrativa común que puede que necesite llevar a cabo consiste en agregar una aplicación afiliada a la base de datos de inicio de sesión único (SSO) empresarial. Agregar una aplicación afiliada a la base de datos de SSO empresarial permite asociar usuarios y credenciales a la aplicación afiliada.  
  
> [!NOTE]
>  Para crear una aplicación afiliada es necesario pertenecer a la cuenta "Administradores afiliados de SSO" o superior.  
  
### <a name="to-create-and-describe-an-application-in-the-sso-database"></a>Para crear y describir una aplicación en la base de datos de SSO  
  
1.  Crear un nuevo `ISSOAdmin` objeto.  
  
2.  Cree una nueva aplicación con una llamada a `ISSOAdmin.CreateApplication`.  
  
3.  Agregue los campos correspondientes que describe la aplicación con una llamada a `ISSOAdmin.CreateFieldInfo`.  
  
     Durante este paso, comunica a la base de datos que una aplicación tiene usuarios y contraseñas asociadas.  
  
4.  Enviar la descripción recién creada en el servidor con una llamada a `ISSOAdmin.UpdateApplication` o `ISSOAdmin2.UpdateApplication2`.  
  
     La diferencia entre los dos métodos es que `UpdateApplication2` utiliza un `IPropertyBag` como las actualizaciones de la manera de describir la aplicación, mientras `UpdateApplication` tiene varios parámetros.  
  
5.  Purgar la caché local para que los cambios realizados mediante una llamada a `ISSOAdmin.PurgeCacheForApplication`.  
  
     Purgar la caché local es una medida de seguridad que evita tener los nombres y contraseñas descritas en el paso 3 en una ubicación no segura.  
  
 En el siguiente ejemplo se muestra cómo crear una aplicación y agregar información de campo.  
  
```  
public static bool AddApplication(string name, string admins, string users)  
    {  
       try  
       {  
          ISSOAdmin admin=new ISSOAdmin();  
          // Create application.  
          admin.CreateApplication(name, "SSO Sample Application", "administrator@ssoaffiliateapplication.com", users, admins, SSOFlag.SSO_WINDOWS_TO_EXTERNAL | SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, 2);  
          // Add fields.  
          admin.CreateFieldInfo(name, "User Id", SSOFlag.SSO_FLAG_NONE);  
          admin.CreateFieldInfo(name, "Password", SSOFlag.SSO_FLAG_FIELD_INFO_MASK);  
          // Enable application.  
          admin.UpdateApplication(name, null, null, null, null, SSOFlag.SSO_FLAG_ENABLED, SSOFlag.SSO_FLAG_ENABLED);  
          // Purge changes.  
          admin.PurgeCacheForApplication(name);  
       }  
       catch  
       {  
          return false;  
       }  
       return true;  
    }  
```  
  
## <a name="see-also"></a>Vea también  
 [Programar con Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md)