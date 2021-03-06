---
title: Configuración de las propiedades de confirmación de reserva (X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce33f5dd-fbd5-448c-8ea3-05dd1467131a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed4ce98bd4191d79ef05742b389e1d065325d8ed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008981"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a>Configuración de propiedades de confirmación de reserva (X12)
En el acuerdo de reserva, puede especificar cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera confirmaciones en respuesta a intercambios codificados en X12 recibidos de la entidad y el tipo de confirmación devuelta a una entidad. Esta sección proporciona instrucciones acerca de cómo hacer lo mismo.  
  
> [!NOTE]
>  Las propiedades de confirmación descritas aquí se aplican también para las confirmaciones de HIPAA.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-x12-ack-properties"></a>Para configurar las propiedades de confirmación de X12  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.  
  
2. En el **X12 configuración de reserva** cuadro de diálogo el **X12 páginas del acuerdo** , bajo el **configuración de intercambio** sección, haga clic en **confirmaciones**.  
  
3. Seleccione **TA1 esperado** para devolver una confirmación técnica (TA1) al remitente del intercambio.  
  
4. Seleccione **997 esperado** para devolver una confirmación funcional (997) al remitente del intercambio.  
  
5. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de X12 para el procesamiento de intercambio](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)