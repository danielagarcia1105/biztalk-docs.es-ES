---
title: Configuración de las propiedades de validación de reserva (EDIFACT) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b925d063-e24b-4cfb-acbd-dcadb511011d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf0e103eb2e20bb64973cd207ed2a55c2f91e58d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233204"
---
# <a name="configuring-fallback-validation-properties-edifact"></a>Configuración de las propiedades de validación de reserva (EDIFACT)
En esta sección se proporcionan instrucciones acerca de cómo impedir que se procesen números de control duplicados.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-duplicate-validation"></a>Para configurar la validación de duplicados  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2.  En el **configuración de reserva de EDIFACT** cuadro de diálogo la **páginas del acuerdo EDIFACT** , bajo la **configuración de intercambio** sección, haga clic en **validación** .  
  
3.  Seleccione el **número de control de intercambio (UNB5)** casilla de verificación para habilitar la canalización de recepción y bloquear los intercambios duplicados. Si se selecciona, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprobará que el número de control de intercambio para el intercambio recibido no coincida con el número de control de intercambio de otro intercambio recibido. Si se detecta una coincidencia, la canalización de recepción no procesará el intercambio.  
  
4.  Si **número de control de intercambio (UNB5)** está seleccionada, en la **comprobar unb5 duplicados dentro de** , escriba el número de días para comprobar si un intercambio duplicado.  
  
5.  Seleccione **el número de control de grupo (UNG5) en intercambio** para impedir que la canalización de recepción procese grupos duplicados.  
  
6.  Seleccione **establecer Control número transacciones (UNH1) en el grupo** impedir que la canalización de recepción procese una transacción duplicada establece.  
  
7.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades de acuerdo de reserva de EDIFACT para el procesamiento de intercambio](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)