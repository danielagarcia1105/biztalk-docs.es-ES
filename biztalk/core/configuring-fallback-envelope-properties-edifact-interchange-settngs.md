---
title: Configuración de las propiedades de sobres de reserva (configuración de intercambio de EDIFACT EDIFACT) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8826041e-02fa-4086-a774-d44a388f42b1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6a141b852f85947165d3d3d4d638cf1cb10ccb0
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22233036"
---
# <a name="configuring-fallback-envelope-properties-edifact-interchange-settngs"></a>Configuración de propiedades de sobre de reserva (configuración de intercambio EDIFACT)
Esta sección proporciona instrucciones acerca de cómo configurar el sobre para mensajes EDIFACT salientes.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-interchange-envelope"></a>Para configurar el sobre de intercambio  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2.  En el **configuración de reserva de EDIFACT** cuadro de diálogo la **páginas del acuerdo EDIFACT** , bajo la **configuración de intercambio** sección, haga clic en **sobres** .  
  
3.  Para **(UNB8) código de prioridad de procesamiento**, escriba un valor con un carácter como mínimo y un máximo de un carácter alfabético. Se trata de un campo opcional.  
  
4.  Para **acuerdo de comunicaciones (UNB10)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 35 caracteres. Este campo es opcional  
  
5.  Seleccione **indicador de prueba (UNB11)** para indicar que el intercambio generado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son datos de prueba.  
  
6.  Seleccione **aplicar segmento UNA (notificación del servicio)** para generar un segmento UNA para el intercambio que se va a enviar. Si se activa esta opción, a continuación, **UNA6** no puede estar vacío y **el sufijo una 6** no puede ser **ninguno**.  
  
    > [!NOTE]
    >  Especifique **UNA6** y **sufijo UNA6** en el **juego de caracteres y separadores** tal y como se describe en la página [(configuración de juego de caracteres de reserva y propiedades del separador EDIFACT)](../core/configuring-fallback-charset-and-separator-properties-edifact.md).  
  
7.  Seleccione **aplicar segmentos UNG (encabezado de grupo funcional)** para crear segmentos de agrupación en el encabezado de grupo funcional en los mensajes salientes.  
  
8.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de EDIFACT para el procesamiento de intercambio](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)