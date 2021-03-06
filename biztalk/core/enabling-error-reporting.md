---
title: Habilitar informes de Error | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1131bbd5-7ab3-4422-b6df-747c722f0b2c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cacb0167bf93f1a870592d0be74567be852ebebc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974549"
---
# <a name="enabling-error-reporting"></a>Habilitar informes de Error
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite seleccionar la opción de si visualizar las advertencias y errores solucionados en el visor de eventos de Windows.  
  
 El siguiente procedimiento habilita o deshabilita el informe de errores o advertencias que genera el mecanismo de informes EDI o el motor EDI. Puede habilitar la notificación de dichos errores o advertencias como parte de un acuerdo o como parte del acuerdo de reserva. Como parte de un acuerdo, este informe está habilitado de forma predeterminada. Como parte del contrato de reserva, este informe está deshabilitado de forma predeterminada. Sin embargo, generan errores de procesamiento/sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] siempre se registran en el Visor de eventos (muestra escribiendo `eventvwr` en el **ejecutar** cuadro de diálogo), independientemente de los errores o advertencias EDI estén habilitadas o no.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-enable-error-reporting-for-an-agreement"></a>Procedimiento para habilitar informes de error para un acuerdo  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y **grupo de BizTalk** nodos, haga clic en el **partes** nodo.  
  
2. En el **entidades y perfiles empresariales** panel, haga clic en la entidad que tenga el acuerdo X12 o EDIFACT para el que desea habilitar el registro de errores y advertencias en el registro de eventos.  
  
   > [!NOTE]
   >  No se pueden registrar errores y advertencia en el Visor de eventos para los acuerdos de AS2.  
  
3. En el **acuerdos** sección, haga clic en el acuerdo X12 o EDIFACT para el que desea habilitar el registro de errores y de advertencia y, a continuación, haga clic en **propiedades**.  
  
4. En el **configuración de Host común** sección, haga clic en **registrar errores en registro de eventos** o **Registrar advertencias en registro de eventos**.  
  
5. Haga clic en **Aceptar** o haga clic en **aplicar**.  
  
### <a name="to-enable-error-reporting-as-part-of-a-fallback-agreement"></a>Procedimiento para habilitar los informes como parte de un acuerdo de reserva  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo bajo el **grupo de BizTalk** nodo y, a continuación, haga clic en **X12 configuración de reserva** o **Configuración de reserva de EDIFACT**.  
  
2. En el **páginas generales de configuración de reserva** ficha para habilitar el registro de errores de EDI o las advertencias generadas por el motor de EDI de BizTalk, haga clic en **registro EDI errores y advertencias generados por el motor EDI en el registro de eventos de Windows**. El registro de errores incluirá datos de error e información contextual.  
  
   > [!NOTE]
   >  Los errores del sistema o de procesamiento se registran en el Visor de eventos independientemente de si está activada o no la casilla.  
  
   > [!NOTE]
   >  No es necesario que seleccionar la **activar informes de EDI** propiedad con el fin de seleccionar el **registro EDI errores y advertencias generados por el motor EDI en el registro de eventos de Windows** propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de soluciones EDI y AS2](../core/monitoring-edi-and-as2-solutions.md)   
 [Códigos de Error de confirmación EDI](../core/edi-acknowledgment-error-codes.md)   
 [Eventos de AS2](../core/as2-events.md)