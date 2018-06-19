---
title: Requisitos para el inicio de sesión único | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0dc92e4492d36ca8204f61354f8422d7eb47631
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015983"
---
# <a name="requirements-for-single-sign-on"></a>Requisitos para el inicio de sesión único
Para usar el inicio de sesión único (SSO), necesita:  
  
-   BizTalk Server
  
-   Visual Studio  
  
-   Inicio de sesión único (SSO) empresarial  
  
-   Un sistema de servidor compatible con SSO  
  
 El host aislado debe configurarse como autenticación de confianza.  
  
## <a name="enable-sso"></a>Habilitar SSO  
  
1.  En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.  
  
2.  Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.  
  
 Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications2.md).  
  
> [!NOTE]
>  Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**. Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.  
  
## <a name="see-also"></a>Vea también  
 [Ejecución de proyectos SSO](../core/running-sso-projects1.md)   
 [Proteger el adaptador](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)