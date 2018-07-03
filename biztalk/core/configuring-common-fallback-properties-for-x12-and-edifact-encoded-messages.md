---
title: Configuración de propiedades comunes de reserva para X12 y EDIFACT mensajes con codificación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7393d6ac-b901-43ef-a8d6-c5b0b3033257
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6f6fa22298221369bfb2c5600bb0ef086ee167d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996765"
---
# <a name="configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages"></a>Configuración de las propiedades comunes de reserva para mensajes codificados en X12 y EDIFACT
Las propiedades de reserva se aplican tanto a intercambios X12 (incluido HIPAA) como a intercambios con codificación EDIFACT. Al igual que sucede con las propiedades del acuerdo de reserva, estas propiedades solamente se aplican si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha determinado el acuerdo en el cual se resuelve el mensaje de entrada o salida.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-set-common-global-properties"></a>Para establecer propiedades globales comunes  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva** o **configuración de reserva de EDIFACT**.  
  
2. En el **páginas generales de configuración de reserva** ficha la **General** página, realice lo siguiente:  
  
   1. Haga clic en **habilitar la configuración de reserva** para habilitar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar la configuración de acuerdo de reserva si no hay ningún acuerdo se resuelve para mensajes entrantes o salientes.  
  
      > [!IMPORTANT]
      >  Si no se activa esta opción, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no usará las propiedades configuradas en el acuerdo de reserva.  
  
   2. Haga clic en **activar informes de EDI** para activar los informes para todos los mensajes EDI. Esto garantiza que los mensajes se muestran en el estado de informes de las pantallas mostradas, haga clic en los vínculos en la parte inferior de la **concentrador de grupo** panel de la consola de administración de BizTalk Server.  
  
   3. Si hizo clic en **activar informes de EDI**, haga clic en **Store carga y conjunto de transacciones para los informes** almacenar la transacción se establece en las tablas EDI de la base de datos de seguimiento (BizTalkDTADb).  
  
   4. Haga clic en **registro EDI errores y advertencias generados por el motor EDI en el registro de eventos de Windows** para registrar los mensajes de error/advertencia generados por el motor EDI (canalizaciones EDI, orquestación, enrutamiento, etc., orquestación de procesamiento por lotes), con contextuales información en el Visor de eventos de Windows. Si se desactiva, estos mensajes de error o de advertencia no se registrarán en el Visor de eventos.  
  
      > [!NOTE]
      >  Los errores del sistema o de procesamiento se registran en el Visor de eventos independientemente de si está activada o no la casilla.  
  
3. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar y aceptar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos globales o de respaldo](../core/configuring-global-or-fallback-agreement-properties.md)