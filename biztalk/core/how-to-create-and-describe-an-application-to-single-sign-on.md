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
# <a name="how-to-create-and-describe-an-application-to-single-sign-on"></a><span data-ttu-id="32786-102">Cómo crear y describir una aplicación para inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="32786-102">How to Create and Describe an Application to Single Sign-On</span></span>
<span data-ttu-id="32786-103">Una tarea administrativa común que puede que necesite llevar a cabo consiste en agregar una aplicación afiliada a la base de datos de inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="32786-103">A common administrative task that you might need to perform is adding an affiliate application into the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="32786-104">Agregar una aplicación afiliada a la base de datos de SSO empresarial permite asociar usuarios y credenciales a la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="32786-104">Adding an affiliate application to the Enterprise SSO database enables you to associate users and credentials with the affiliated application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32786-105">Para crear una aplicación afiliada es necesario pertenecer a la cuenta "Administradores afiliados de SSO" o superior.</span><span class="sxs-lookup"><span data-stu-id="32786-105">Creating an affiliated application requires membership in the "SSO Affiliate Administrator" account or above.</span></span>  
  
### <a name="to-create-and-describe-an-application-in-the-sso-database"></a><span data-ttu-id="32786-106">Para crear y describir una aplicación en la base de datos de SSO</span><span class="sxs-lookup"><span data-stu-id="32786-106">To create and describe an application in the SSO database</span></span>  
  
1.  <span data-ttu-id="32786-107">Crear un nuevo `ISSOAdmin` objeto.</span><span class="sxs-lookup"><span data-stu-id="32786-107">Create a new `ISSOAdmin` object.</span></span>  
  
2.  <span data-ttu-id="32786-108">Cree una nueva aplicación con una llamada a `ISSOAdmin.CreateApplication`.</span><span class="sxs-lookup"><span data-stu-id="32786-108">Create a new application with a call to `ISSOAdmin.CreateApplication`.</span></span>  
  
3.  <span data-ttu-id="32786-109">Agregue los campos correspondientes que describe la aplicación con una llamada a `ISSOAdmin.CreateFieldInfo`.</span><span class="sxs-lookup"><span data-stu-id="32786-109">Add the relevant fields describing the application with a call to `ISSOAdmin.CreateFieldInfo`.</span></span>  
  
     <span data-ttu-id="32786-110">Durante este paso, comunica a la base de datos que una aplicación tiene usuarios y contraseñas asociadas.</span><span class="sxs-lookup"><span data-stu-id="32786-110">During this step, you tell the database that an application has users and associated passwords.</span></span>  
  
4.  <span data-ttu-id="32786-111">Enviar la descripción recién creada en el servidor con una llamada a `ISSOAdmin.UpdateApplication` o `ISSOAdmin2.UpdateApplication2`.</span><span class="sxs-lookup"><span data-stu-id="32786-111">Push the newly created description out to the server with a call to `ISSOAdmin.UpdateApplication` or `ISSOAdmin2.UpdateApplication2`.</span></span>  
  
     <span data-ttu-id="32786-112">La diferencia entre los dos métodos es que `UpdateApplication2` utiliza un `IPropertyBag` como las actualizaciones de la manera de describir la aplicación, mientras `UpdateApplication` tiene varios parámetros.</span><span class="sxs-lookup"><span data-stu-id="32786-112">The difference between the two methods is that `UpdateApplication2` uses an `IPropertyBag` as the way to describe the application updates, while `UpdateApplication` has multiple parameters.</span></span>  
  
5.  <span data-ttu-id="32786-113">Purgar la caché local para que los cambios realizados mediante una llamada a `ISSOAdmin.PurgeCacheForApplication`.</span><span class="sxs-lookup"><span data-stu-id="32786-113">Purge the local cache for the changes you made by calling `ISSOAdmin.PurgeCacheForApplication`.</span></span>  
  
     <span data-ttu-id="32786-114">Purgar la caché local es una medida de seguridad que evita tener los nombres y contraseñas descritas en el paso 3 en una ubicación no segura.</span><span class="sxs-lookup"><span data-stu-id="32786-114">Purging the local cache is a security measure that prevents having the names and passwords that you describe in step 3 to exist in an unsecured location.</span></span>  
  
 <span data-ttu-id="32786-115">En el siguiente ejemplo se muestra cómo crear una aplicación y agregar información de campo.</span><span class="sxs-lookup"><span data-stu-id="32786-115">The following example shows how to create an application and add field information.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="32786-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="32786-116">See Also</span></span>  
 [<span data-ttu-id="32786-117">Programar con Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="32786-117">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)