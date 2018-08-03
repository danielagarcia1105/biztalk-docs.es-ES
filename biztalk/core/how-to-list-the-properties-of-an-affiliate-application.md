---
title: Cómo enumerar las propiedades de una aplicación afiliada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], listing properties
- managing [SSO applications], listing properties
ms.assetid: a120acd7-2f0b-4c72-8a8a-f8e500a773c8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5920263006a9188da83f82dcf65dad8fb8faada
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002725"
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a>Cómo enumerar las propiedades de una aplicación afiliada
Este comando muestra la siguiente información acerca de la aplicación afiliada. Para obtener más información acerca de las propiedades de una aplicación afiliada, vea [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).  
  
 El sistema de SSO obtiene esta información a partir del archivo .xml empleado para actualizar la aplicación afiliada. Para obtener más información, consulte [cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md).  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a>Para mostrar las propiedades de una aplicación afiliada con la utilidad de administración  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo ** ssomanage-displayapp *\<nombre de la aplicación\>**<em>, donde *\<nombre de la aplicación\></em>  es el nombre de la aplicación afiliada que desea mostrar el propiedades de.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a>Para mostrar las propiedades de una aplicación afiliada con la utilidad de cliente  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad de instalación*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo ** ssoclient – displayapp *\<nombre de la aplicación\>**<em>, donde *\<nombre de la aplicación\></em>  es el nombre de la aplicación afiliada que desea mostrar el propiedades de.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../core/managing-affiliate-applications.md)