---
title: "Cómo agregar suscriptores a una alerta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- subscriptions
- managing [BAM], adding alert subscribers
ms.assetid: c76a117d-4516-4f48-995c-7e018dbba755
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e86bde9f47e04c17f62c3cacff5d779cf0bed56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-subscribers-to-an-alert"></a>Cómo agregar suscriptores a una alerta
Los administradores utilizan el **Agregar suscripción** comando para agregar un suscriptor a una alerta específica.  
  
### <a name="to-add-subscribers-to-an-alert"></a>Para agregar suscriptores a una alerta  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento. Presione **ENTRAR**.  
  
3.  Type `bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.  
  
    > [!NOTE]
    >  *Tipo* especifica el método de entrega que utiliza BAM para entregar la alerta. Si especifica un tipo de entrega de correo electrónico, deberá proporcionar una dirección de correo electrónico en la que se entregue la alerta.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4.  Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Cómo quitar suscriptores de una alerta](../core/how-to-remove-subscribers-from-an-alert.md)