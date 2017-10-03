---
title: "Configuración de sobres (configuración de intercambio EDIFACT) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 501ccc5f-e21c-4c36-9509-217d5b3ba21f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531b559e690fae5369298a90cd372edcae79db57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a>Configuración de sobres (configuración de intercambio de EDIFACT)
Esta sección proporciona instrucciones acerca de cómo configurar el sobre para mensajes EDIFACT salientes.  
  
> [!IMPORTANT]
>  Todas las propiedades se deshabilitan en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
>   
>  Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-interchange-envelope"></a>Para configurar el sobre de intercambio  
  
1.  Crear un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **sobres**.  
  
3.  Para **(UNB8) código de prioridad de procesamiento**, escriba un valor con un carácter como mínimo y un máximo de un carácter alfabético. Se trata de un campo opcional.  
  
4.  Para **acuerdo de comunicaciones (UNB10)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 35 caracteres. Este campo es opcional  
  
5.  Seleccione **indicador de prueba (UNB11)** para indicar que el intercambio generado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son datos de prueba.  
  
6.  Seleccione **aplicar segmento UNA (notificación del servicio)** para generar un segmento UNA para el intercambio que se va a enviar. Si se activa esta opción, a continuación, **UNA6** no puede estar vacío y **el sufijo una 6** no puede ser **ninguno**.  
  
    > [!NOTE]
    >  Especifique **UNA6** y **sufijo UNA6** en el **juego de caracteres y separadores** tal y como se describe en la página [configurar el juego de caracteres y separadores (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).  
  
7.  Seleccione **aplicar segmentos UNG (encabezado de grupo funcional)** para crear segmentos de agrupación en el encabezado de grupo funcional en los mensajes salientes.  
  
8.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de intercambio (EDIFACT).](../core/configuring-interchange-settings-edifact.md)