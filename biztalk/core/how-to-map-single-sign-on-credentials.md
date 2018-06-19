---
title: Cómo asignar credenciales de inicio de sesión único | Documentos de Microsoft
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
ms.openlocfilehash: 1a2717a990cf6ac2bac92067354afd42931c9a75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254212"
---
# <a name="how-to-map-single-sign-on-credentials"></a><span data-ttu-id="2e51a-102">Cómo asignar credenciales de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="2e51a-102">How to Map Single Sign-On Credentials</span></span>
<span data-ttu-id="2e51a-103">Si sabe que tiene aplicaciones afiliadas en la base de datos de inicio de sesión único (SSO) empresarial, puede asignar las credenciales de un usuario a esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e51a-103">When you know that you have affiliated applications in your Enterprise Single Sign-On database, you can map the credentials for a user to that application.</span></span> <span data-ttu-id="2e51a-104">Asignación de las credenciales del usuario actual a una aplicación afiliada requiere el uso de una combinación de la `ISSOMapper` y `ISSOMapping` interfaces.</span><span class="sxs-lookup"><span data-stu-id="2e51a-104">Mapping the credentials of the current user to an affiliated application requires that you use a combination of the `ISSOMapper` and `ISSOMapping` interfaces.</span></span>  
  
### <a name="to-map-between-an-affiliated-application-and-user-credentials"></a><span data-ttu-id="2e51a-105">Para realizar una asignación entre una aplicación afiliada y las credenciales de usuario</span><span class="sxs-lookup"><span data-stu-id="2e51a-105">To map between an affiliated application and user credentials</span></span>  
  
1.  <span data-ttu-id="2e51a-106">Crear nuevas instancias de `ISSOMapper` y `ISSOMapping`.</span><span class="sxs-lookup"><span data-stu-id="2e51a-106">Create new instances of `ISSOMapper` and `ISSOMapping`.</span></span>  
  
2.  <span data-ttu-id="2e51a-107">Establecer el `ISSOMapping` propiedades en los valores correspondientes.</span><span class="sxs-lookup"><span data-stu-id="2e51a-107">Set the `ISSOMapping` properties to the relevant values.</span></span>  
  
     <span data-ttu-id="2e51a-108">Las propiedades pertinentes para `ISSOMapping` son el nombre de dominio de Microsoft Windows del usuario, el nombre de usuario de Windows, el nombre de la aplicación afiliada y el nombre de usuario externo.</span><span class="sxs-lookup"><span data-stu-id="2e51a-108">The relevant properties for `ISSOMapping` are the Microsoft Windows domain name of the user, the Windows user name, the name of the affiliated application, and the external user name.</span></span>  
  
3.  <span data-ttu-id="2e51a-109">Cree la asignación mediante una llamada a ISSOMapping.Create.</span><span class="sxs-lookup"><span data-stu-id="2e51a-109">Create the mapping with a call to ISSOMapping.Create.</span></span>  
  
     <span data-ttu-id="2e51a-110">Al llamar a `ISSOMapping.Create` propaga la copia local de asignación en el servidor de Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="2e51a-110">Calling `ISSOMapping.Create` propagates the local copy of the mapping out to the Enterprise Single Sign-On server.</span></span>  
  
4.  <span data-ttu-id="2e51a-111">Establecer las credenciales en la asignación con una llamada a `ISSOMapper.SetExternalCredentials`.</span><span class="sxs-lookup"><span data-stu-id="2e51a-111">Set the credentials on the mapping with a call to `ISSOMapper.SetExternalCredentials`.</span></span>  
  
5.  <span data-ttu-id="2e51a-112">Habilite la asignación mediante una llamada a `ISSOMapping.Enable`.</span><span class="sxs-lookup"><span data-stu-id="2e51a-112">Enable the mapping with a call to `ISSOMapping.Enable`.</span></span>  
  
 <span data-ttu-id="2e51a-113">En el siguiente ejemplo se muestra cómo agregar una asignación entre una aplicación de inicio de sesión único empresarial especificada y un usuario.</span><span class="sxs-lookup"><span data-stu-id="2e51a-113">The following example shows how to add mapping between a specified Enterprise Single Sign-On application and a user.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2e51a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e51a-114">See Also</span></span>  
 [<span data-ttu-id="2e51a-115">Programar con Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="2e51a-115">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)