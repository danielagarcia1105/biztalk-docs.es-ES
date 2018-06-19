---
title: Cómo quitar SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, deleting
- SSO, deleting
- deleting, SSO
- deleting, Master Secret server
ms.assetid: 0e1ad8e3-0938-4f36-b85b-4631d0eeb8c9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7134186161c3c0647a20047afcbbe317fcbad1ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254660"
---
# <a name="how-to-remove-sso"></a>Cómo quitar SSO
Si se quita BizTalk Server, el inicio de sesión único (SSO) empresarial deja de estar configurado a menos que haya un programa dependiente que lo utilice. No obstante, no se quita. Debe quitar SSO por separado. Asimismo, se puede restaurar la información de configuración, incluido el secreto principal, para reutilizar los datos existentes. Para obtener más información, consulte [cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md).  
  
### <a name="to-remove-enterprise-single-sign-on"></a>Para quitar el inicio de sesión único empresarial  
  
1.  Haga una copia de seguridad de la clave secreta principal. Para obtener más información, consulte [cómo volver la seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md).  
  
2.  Desinstale [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
3.  En el menú **Inicio** , haga clic en **Panel de control**.  
  
4.  Haga clic en **agregar o quitar programas**.  
  
5.  En el **agregar o quitar programas** cuadro de diálogo, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **quitar**.  
  
6.  Haga clic en **Sí** cuando se le pida que confirme la eliminación de Microsoft Enterprise Single Sign-On.  
  
    > [!NOTE]
    >  Si tiene instaladas las características Administración, Desarrollo y Tiempo de ejecución de BizTalk Server, o las características de administración de Host Integration Server, no será posible desinstalar los componentes Administración y Tiempo de ejecución de SSO hasta que se quiten todas las dependencias.  
  
## <a name="see-also"></a>Vea también  
 [Instalación de SSO](../core/installing-sso.md)