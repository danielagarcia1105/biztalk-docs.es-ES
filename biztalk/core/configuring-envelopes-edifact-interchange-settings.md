---
title: Configuración de sobres (configuración de intercambio EDIFACT) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501ccc5f-e21c-4c36-9509-217d5b3ba21f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80957d82a70b0fca8a11ace428f87496b45dcb31
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993597"
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a>Configuración de sobres (configuración de intercambio de EDIFACT)
Esta sección proporciona instrucciones acerca de cómo configurar el sobre para mensajes EDIFACT salientes.  
  
> [!IMPORTANT]
>  Todas las propiedades están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.  
>   
>  Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la lista anterior de propiedades están deshabilitadas en el **entidad A -> entidad B** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-interchange-envelope"></a>Para configurar el sobre de intercambio  
  
1. Cree un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2. En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **sobres**.  
  
3. Para **procesamiento (UNB8) del código de prioridad**, escriba un valor con un carácter como mínimo y un máximo de un carácter alfabético. Se trata de un campo opcional.  
  
4. Para **acuerdo de comunicaciones (UNB10)**, escriba un valor alfanumérico con un carácter como mínimo y 35 caracteres como máximo. Este campo es opcional  
  
5. Seleccione **indicador de prueba (UNB11)** para indicar que el intercambio generado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son datos de prueba.  
  
6. Seleccione **aplicar segmento UNA (notificación del servicio)** para generar un segmento UNA para el intercambio se envíen. Si se activa esta opción, a continuación, **UNA6** no puede estar vacío y **el sufijo una 6** no puede ser **ninguno**.  
  
   > [!NOTE]
   >  Especifique **UNA6** y **sufijo UNA6** en el **juego de caracteres y separadores** como se describe en la página [configurar el juego de caracteres y separadores (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).  
  
7. Seleccione **aplicar segmentos UNG (encabezado de grupo funcional)** para crear segmentos de agrupación en el encabezado de grupo funcional en los mensajes salientes.  
  
8. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las opciones de intercambio (EDIFACT)](../core/configuring-interchange-settings-edifact.md)