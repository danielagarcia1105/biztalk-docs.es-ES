---
title: "Cómo quitar las cuentas de una vista | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- managing [BAM], deleting accounts from views
- Remove-Account command [BAM]
ms.assetid: b74a64a0-ddb3-45d2-add7-6261c31be0f0
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80c0909a5544334cd9f0f8540ff5a4c357b851e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-accounts-from-a-view"></a>Cómo quitar cuentas de una vista
Los administradores utilizan el **remove-account** comando para quitar usuarios de vistas de BAM y proteger las vistas de hojas de cálculo de Excel de BAM de accesos no autorizados.  
  
 Para obtener información acerca de cómo ver las vistas de BAM, consulte [cómo enumerar vistas de BAM](../core/how-to-list-bam-views.md).  
  
### <a name="to-remove-an-account-from-a-view"></a>Para quitar una cuenta de una vista  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
3.  Tipo de **bm remove-account - AccountName:\<nombre de cuenta >-View:\<nombre de vista >**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)