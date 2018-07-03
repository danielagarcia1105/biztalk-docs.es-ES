---
title: Cómo asignar credenciales de inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e847bde9-7a4c-4b81-8ad6-6a7cf23d19a1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5534eb63d7b9586017d77ffd84606a842f12a48d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002901"
---
# <a name="how-to-map-single-sign-on-credentials"></a>Cómo asignar credenciales de inicio de sesión único
Si sabe que tiene aplicaciones afiliadas en la base de datos de inicio de sesión único (SSO) empresarial, puede asignar las credenciales de un usuario a esa aplicación. Asignar las credenciales del usuario actual a una aplicación afiliada requiere el uso de una combinación de la `ISSOMapper` y `ISSOMapping` interfaces.  
  
### <a name="to-map-between-an-affiliated-application-and-user-credentials"></a>Para realizar una asignación entre una aplicación afiliada y las credenciales de usuario  
  
1. Crear nuevas instancias de `ISSOMapper` y `ISSOMapping`.  
  
2. Establecer el `ISSOMapping` propiedades en los valores correspondientes.  
  
    Las propiedades pertinentes para `ISSOMapping` son el nombre de dominio de Microsoft Windows del usuario, el nombre de usuario de Windows, el nombre de la aplicación afiliada y el nombre de usuario externo.  
  
3. Cree la asignación mediante una llamada a ISSOMapping.Create.  
  
    Una llamada a `ISSOMapping.Create` propaga la copia local de asignación en el servidor de Enterprise Single Sign-On.  
  
4. Establecer las credenciales de la asignación con una llamada a `ISSOMapper.SetExternalCredentials`.  
  
5. Habilite la asignación mediante una llamada a `ISSOMapping.Enable`.  
  
   En el siguiente ejemplo se muestra cómo agregar una asignación entre una aplicación de inicio de sesión único empresarial especificada y un usuario.  
  
```  
public static bool AddMapping(string application, string user, string XU, string XP)  
{  
   try  
   {  
      // Set mapping.  
      ISSOMapper mapper=new ISSOMapper();  
      ISSOMapping mapping=new ISSOMapping();  
     string username=user.Substring(user.IndexOf('\\')+1);  
      string userdomain=user.Substring(0, user.IndexOf('\\'));  
      mapping.WindowsDomainName=userdomain;  
      mapping.WindowsUserName=username;  
      mapping.ApplicationName=application;  
      mapping.ExternalUserName=XU;  
      mapping.Create(0);  
      // Set credentials.  
      string[] credentials=new string[]{XP};  
      mapper.SetExternalCredentials(application, XU, ref credentials);  
      mapping.Enable(0);  
   }  
   catch  
   {  
      return false;  
   }  
   return true;  
      }  
```  
  
## <a name="see-also"></a>Vea también  
 [Programación con Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md)