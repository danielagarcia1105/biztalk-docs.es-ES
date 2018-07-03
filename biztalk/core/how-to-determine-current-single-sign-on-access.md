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
# <a name="how-to-determine-current-single-sign-on-access"></a>Cómo determinar el acceso de inicio de sesión único actual
Una de las primeras tareas que puede ser necesario llevar a cabo para un usuario es determinar qué aplicaciones afiliadas se han configurado ya para el usuario actual. Esta consulta puede llevarse a cabo con una llamada a ISSOMapper.GetApplications.  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a>Para consultar la base de datos de inicio de sesión único (SSO) sobre las aplicaciones disponibles para el usuario actual  
  
1. Cree una nueva instancia de `ISSOMapper`.  
  
    En general, `ISSOMapper` es una interfaz diseñada para recuperar información de Single Sign-On (SSO). Probablemente utilizará `ISSOMapper` en muchas consultas similares.  
  
2. Recupere todas las aplicaciones que están afiliadas con el usuario actual mediante la llamada a GetApplications.  
  
    GetApplications devuelve automáticamente solo las aplicaciones afiliadas del usuario actual.  
  
   En el siguiente ejemplo de código se muestra cómo consultar la base de datos de inicio de sesión único (SSO).  
  
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
  
## <a name="see-also"></a>Vea también  
 [Programación con Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md)