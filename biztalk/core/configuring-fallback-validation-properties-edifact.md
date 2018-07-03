---
title: Configuración de las propiedades de validación de reserva (EDIFACT). | Microsoft Docs
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
ms.openlocfilehash: 4276ad1b5ae995cfb6370377d7d1671ede09bd52
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975453"
---
# <a name="configuring-fallback-validation-properties-edifact"></a>Configuración de las propiedades de validación de reserva (EDIFACT)
En esta sección se proporcionan instrucciones acerca de cómo impedir que se procesen números de control duplicados.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-duplicate-validation"></a>Para configurar la validación de duplicados  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2. En el **configuración de reserva de EDIFACT** cuadro de diálogo el **páginas del acuerdo EDIFACT** , bajo el **configuración de intercambio** sección, haga clic en **validación** .  
  
3. Seleccione el **número de control de intercambio (UNB5)** casilla de verificación para habilitar la canalización de recepción bloquee los intercambios duplicados. Si se selecciona, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprobará que el número de control de intercambio para el intercambio recibido no coincida con el número de control de intercambio de otro intercambio recibido. Si se detecta una coincidencia, la canalización de recepción no procesará el intercambio.  
  
4. Si **número de control de intercambio (UNB5)** está seleccionado, en el **comprobar unb5 duplicado dentro de** , escriba el número de días para buscar un intercambio duplicado.  
  
5. Seleccione **el número de control de grupo (UNG5) en intercambio** para impedir que la canalización de recepción procese grupos duplicados.  
  
6. Seleccione **establecer Control número transacciones (UNH1) en el grupo** para evitar que la canalización de recepción de procesamiento de transacciones duplicados de conjuntos.  
  
7. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de EDIFACT para el procesamiento de intercambio](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)