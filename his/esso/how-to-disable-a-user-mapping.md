---
title: Cómo deshabilitar una asignación de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c745dd-4d39-46e5-88bf-b803ae2e0a1b
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 93694ed8a3238be51b255bcad79122169461d885
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250976"
---
# <a name="how-to-disable-a-user-mapping"></a>Cómo deshabilitar una asignación de usuario
Puede deshabilitar una asignación de usuarios cuando desee desactivar todas las operaciones que están asociadas a una asignación determinada. Debe deshabilitar una asignación de usuarios antes de que pueda quitarla.  
  
 Cuando se deshabilita una asignación de usuarios, aparecerá como (D) *\<dominio >\\< nombre de usuario\>* al enumerar las asignaciones de usuario.  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a>Para deshabilitar una asignación de usuarios con la utilidad de administración  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, presione **ENTRAR**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –disablemapping <domain>\<username><application name>`, donde  *\<dominio >* es el dominio de Windows para la cuenta de usuario  *\<nombre de usuario >* es el nombre de usuario de Windows para el que desea deshabilitar el las credenciales, y  *\<nombre de aplicación >* es el nombre de la aplicación afiliada para la que desea quitar la asignación de usuario.  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a>Para deshabilitar una asignación de usuarios con la utilidad de cliente  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, presione **ENTRAR**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssoclient –disablemapping <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada para la que desea quitar la asignación de usuario.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de SSO](../esso/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../esso/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../esso/managing-user-mappings.md)