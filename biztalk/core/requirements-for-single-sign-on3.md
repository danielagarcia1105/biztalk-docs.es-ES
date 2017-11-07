---
title: Requisitos de SSO para adaptador TIBCO Rendevous | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40cf27a3b96534239fa871bd04b90febee9beafe
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="requirements-for-single-sign-on"></a>Requisitos para el inicio de sesión único

## <a name="prerequisites"></a>Requisitos previos
Para usar el inicio de sesión único (SSO), debe tener lo siguiente:  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   Inicio de sesión único (SSO) empresarial  
  
-   Un sistema de servidor que admite el SSO  
  
-   El host aislado debe configurarse como autenticación de confianza.  
  
## <a name="enable-sso"></a>Habilitar SSO  
  
1.  En el **propiedades de transporte** ventana, seleccione **Sí** para **usar SSO**.  
  
2.  Al especificar las propiedades del transporte, seleccione una aplicación afiliada adecuada.  
  
 Para obtener más información, consulte [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).  
  
> [!NOTE]
>  Después de trabajar mediante SSO, no olvide restablecer las carpetas de uso compartido de Web en **no comparten**. Las aplicaciones que usen dichas carpetas no se actualizarán ni se desinstalarán correctamente si la carpeta es de uso compartido, ya que se considerará que están en uso.  
  
## <a name="see-also"></a>Vea también  
[Seguridad](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)