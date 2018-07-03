---
title: Requisitos de inicio de sesión único para el adaptador TIBCO EMS | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8baf665a7f997293130a2c1eb93f893167f39a4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967885"
---
# <a name="requirements-for-single-sign-on"></a>Requisitos para el inicio de sesión único

## <a name="overview"></a>Información general
El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) proporciona compatibilidad con inicio de sesión único (SSO). Una aplicación afiliada, creada por herramientas de Inicio de sesión único de la empresa, representa un sistema de servidor como TBCO EMS.  
  
 Para usar el inicio de sesión único (SSO), debe tener:  
  
- Microsoft BizTalk Server
  
- Visual Studio  
  
- Inicio de sesión único (SSO) empresarial  
  
- Un sistema de servidor que admita el inicio de sesión único  
  
  El host aislado debe configurarse como autenticación de confianza.
  
## <a name="enable-sso"></a>Habilitar el inicio de sesión único  
  
1.  En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.  
  
2.  Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.  
  
     Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).  
  
    > [!NOTE]
    >  Después de trabajar mediante SSO, no olvide restablecer cualquier carpeta de uso compartido de Web **no comparten**. Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.  
  
## <a name="see-also"></a>Vea también  
[Proteger el adaptador](../core/security-in-biztalk-adapter-for-tibco-ems.md)