---
title: Cómo enumerar aplicaciones afiliadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], listing applications
- applications [SSO], listing applications
ms.assetid: b51ff597-824e-4488-a47f-3a9b3d4437c6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6c4d4e4118bfe5f5cab7a9c44e770dd12656c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974154"
---
# <a name="how-to-list-affiliate-applications"></a>Cómo enumerar aplicaciones afiliadas
Utilice este comando para enumerar todas las aplicaciones afiliadas. Si el usuario es miembro de la cuenta de administradores de aplicación, este comando sólo mostrará la aplicación para la que el usuario es administrador.  
  
### <a name="to-list-affiliate-applications-using-the-administration-utility"></a>Para enumerar las aplicaciones afiliadas con la utilidad de administración  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage - listapps [all]** donde **todos los** es un parámetro opcional que se mostrará también las aplicaciones que usan la característica de almacén de configuración. Si el usuario que ejecuta este comando es un administrador de aplicaciones, sólo se enumerarán las aplicaciones para las que es administrador. Si el usuario que ejecuta este comando es un administrador afiliado o un administrador de SSO, se enumerarán todas las aplicaciones afiliadas.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-list-affiliate-applications-using-the-client-utility"></a>Para enumerar las aplicaciones afiliadas con la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssoclient – listapps** para enumerar las aplicaciones afiliadas. Se enumerarán sólo las aplicaciones afiliadas de las que el usuario que realiza esta tarea es miembro, por ejemplo, será necesario que pertenezcan a la cuenta de grupo de usuarios de la aplicación afiliada.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)   
 [Cómo crear una aplicación afiliada](../core/how-to-create-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../core/managing-affiliate-applications.md)