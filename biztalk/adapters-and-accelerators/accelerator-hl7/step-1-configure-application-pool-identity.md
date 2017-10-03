---
title: 'Paso 1: Configurar la identidad del grupo de aplicaciones | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, application pools
- application pools
ms.assetid: 66286327-8580-4378-89ee-ddd7204b03c6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e61ee2994e81c3fdd352506d6a9757cde557fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-application-pool-identity"></a>Paso 1: Configurar la identidad del grupo de aplicaciones
En este tutorial, utilice un grupo de aplicaciones en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet Information Services (IIS) para procesar la orquestación, que se publique como un servicio Web. Un grupo de aplicaciones es una agrupación de una o más direcciones URL servidas por un proceso de trabajo.  
  
 La identidad de un grupo de aplicaciones es el nombre de la cuenta de servicio en la que se ejecuta el proceso de trabajo del grupo de aplicaciones. De forma predeterminada, grupos de aplicaciones funcionan bajo la cuenta de usuario del servicio de red, que tiene derechos de bajo nivel de acceso de usuario y no es suficiente para que la función de este tutorial. Por motivos de seguridad que desea configurar la identidad del grupo de aplicaciones a una cuenta de usuario con los permisos mínimos, pero al menos permisos para escribir en la base de datos de cuadro de mensajes (BizTalkMsgBoxDb) y la base de datos de configuración (también conocido como el de BizTalk Base de datos de administración, o BizTalkMgmtDb).  
  
### <a name="to-change-the-service-account-under-which-an-application-pool-runs"></a>Para cambiar la cuenta de servicio en la que se ejecuta un grupo de aplicaciones  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el Administrador de Internet Information Services (IIS), expanda el equipo local y expanda **grupos de aplicaciones**.  
  
3.  Haga clic en el grupo de aplicaciones que desea configurar (de forma predeterminada, este tutorial se ejecuta bajo la **DefaultAppPool**) y, a continuación, haga clic en **propiedades**.  
  
4.  En el cuadro de diálogo Propiedades de DefaultAppPool, en la **identidad** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Predefinidos**|Anule la selección de **predefinidos**. **Predefinidos** hace referencia a las cuentas de servicio estándar, como el siguiente:<br /><br /> -   **Servicio de red** (valor predeterminado), que tiene derechos de acceso de usuario de bajo nivel que se pueden usar para tener acceso a recursos en equipos remotos.<br />-   **Servicio local**, que tiene derechos de acceso de bajo nivel. Use esta opción para las situaciones que no requieren acceso a los recursos de equipos remotos.<br />-   **Sistema local**, que es una cuenta con más derechos de usuario de la cuenta de servicio de red o servicio Local.|  
    |**Configurable**|Seleccione **Configurable**. **Puede configurar** hace referencia a nombres de usuario registrado.|  
    |**Nombre de usuario.**|Escriba el nombre de usuario de la cuenta bajo la que desea que funcione el proceso de trabajo.|  
    |**Contraseña**|Escriba la contraseña.|  
  
5.  Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  O bien, para mayor seguridad, podría crear un grupo de aplicaciones completamente nuevo que se ejecuta bajo una identidad personalizada que cree con permisos personalizados para este tutorial.  
  
 Continúe con [paso 2: crear un nuevo proyecto](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)