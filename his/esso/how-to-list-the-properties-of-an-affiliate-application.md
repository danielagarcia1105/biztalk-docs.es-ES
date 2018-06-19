---
title: Cómo mostrar las propiedades de una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac15775-39d0-470e-b9d2-21b2d02e1de7
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: e35f1f068f63d4db9738733bcada55047e81a19a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250960"
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a>Cómo mostrar las propiedades de una aplicación afiliada
El **displayapp** comando muestra la siguiente información acerca de la aplicación afiliada. Para obtener más información acerca de las propiedades para una aplicación afiliada, vea [aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md).  
  
 El sistema de inicio de sesión único (SSO) obtiene esta información desde el archivo XML que utiliza para actualizar la aplicación afiliada. Para obtener más información, consulte [cómo actualizar las propiedades de una aplicación afiliada](../esso/how-to-update-the-properties-of-an-affiliate-application.md).  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a>Para mostrar las propiedades de una aplicación afiliada con la utilidad de administración  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –displayapp <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada que desea mostrar las propiedades.  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a>Para mostrar las propiedades de una aplicación afiliada con la utilidad de cliente  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es \< *unidad de instalación*>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssoclient –displayapp <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada que desea mostrar las propiedades.  
  
## <a name="see-also"></a>Vea también  
 [Administrar asignaciones de usuario](../esso/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../esso/managing-affiliate-applications.md)