---
title: Cómo determinar el acceso de inicio de sesión único actual | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cab68dfc-27cd-4f7c-a0df-20c670306358
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c57cfae2c2b7545854fa7891f099a19ff7bb0098
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014773"
---
# <a name="how-to-determine-current-single-sign-on-access"></a><span data-ttu-id="e6b0d-102">Cómo determinar el acceso de inicio de sesión único actual</span><span class="sxs-lookup"><span data-stu-id="e6b0d-102">How to Determine Current Single Sign-On Access</span></span>
<span data-ttu-id="e6b0d-103">Una de las primeras tareas que puede ser necesario llevar a cabo para un usuario es determinar qué aplicaciones afiliadas se han configurado ya para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="e6b0d-103">One of the first tasks you might need to perform for a user is to determine what affiliated applications have already been set up for the current user.</span></span> <span data-ttu-id="e6b0d-104">Esta consulta puede llevarse a cabo con una llamada a ISSOMapper.GetApplications.</span><span class="sxs-lookup"><span data-stu-id="e6b0d-104">You can perform this query with a call to ISSOMapper.GetApplications.</span></span>  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a><span data-ttu-id="e6b0d-105">Para consultar la base de datos de inicio de sesión único (SSO) sobre las aplicaciones disponibles para el usuario actual</span><span class="sxs-lookup"><span data-stu-id="e6b0d-105">To query the Single Sign-On database for the applications available to the current user</span></span>  
  
1. <span data-ttu-id="e6b0d-106">Cree una nueva instancia de `ISSOMapper`.</span><span class="sxs-lookup"><span data-stu-id="e6b0d-106">Create a new instance of `ISSOMapper`.</span></span>  
  
    <span data-ttu-id="e6b0d-107">En general, `ISSOMapper` es una interfaz diseñada para recuperar información de Single Sign-On (SSO).</span><span class="sxs-lookup"><span data-stu-id="e6b0d-107">In general, `ISSOMapper` is an interface designed to retrieve information from Single Sign-On (SSO).</span></span> <span data-ttu-id="e6b0d-108">Probablemente utilizará `ISSOMapper` en muchas consultas similares.</span><span class="sxs-lookup"><span data-stu-id="e6b0d-108">You will most likely use `ISSOMapper` in many similar queries.</span></span>  
  
2. <span data-ttu-id="e6b0d-109">Recupere todas las aplicaciones que están afiliadas con el usuario actual mediante la llamada a GetApplications.</span><span class="sxs-lookup"><span data-stu-id="e6b0d-109">Retrieve all applications that are affiliated with the current user by calling GetApplications.</span></span>  
  
    <span data-ttu-id="e6b0d-110">GetApplications devuelve automáticamente solo las aplicaciones afiliadas del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="e6b0d-110">GetApplications automatically returns only the affiliated applications of the current user.</span></span>  
  
   <span data-ttu-id="e6b0d-111">En el siguiente ejemplo de código se muestra cómo consultar la base de datos de inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="e6b0d-111">The following code example demonstrates how to query the Single Sign-On database.</span></span>  
  
```  
private static string[] Applications=null;  
. . .  
public static string[] GetCurrentUserApplications()  
{  
   if(Applications==null)  
   {  
      string[] descs;  
      string[] contacts;  
      ISSOMapper mapper=new ISSOMapper();  
      mapper.GetApplications(out Applications, out descs, out contacts);  
   }  
   return Applications;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6b0d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6b0d-112">See Also</span></span>  
 [<span data-ttu-id="e6b0d-113">Programación con Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="e6b0d-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)