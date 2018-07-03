---
title: Configuración de las propiedades de confirmación de reserva (EDIFACT). | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6062b881-3214-4e68-acbc-1f8c255fd86b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1422e524d9527b5e7e5362d5867654026cc03768
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974181"
---
# <a name="configuring-fallback-acknowledgement-properties-edifact"></a>Configuración de las propiedades de confirmación de reserva (EDIFACT)
En el acuerdo de reserva, puede especificar qué tipo de confirmación se va a devolver a una entidad.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a>Para configurar las propiedades globales de confirmación (CONTRL) de EDIFACT  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2. En el **configuración de reserva de EDIFACT** cuadro de diálogo el **páginas del acuerdo EDIFACT** , bajo el **configuración de intercambio** sección, haga clic en  **Confirmaciones**.  
  
3. Seleccione **recepción del mensaje (CONTRL) esperada** para devolver una confirmación técnica (CONTRL) al remitente del intercambio.  
  
4. Seleccione **confirmación (CONTRL) esperada** para devolver una confirmación funcional (CONTRL) al remitente del intercambio.  
  
5. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de EDIFACT para el procesamiento de intercambio](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)