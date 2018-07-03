---
title: Configuración de identificadores (EDIFACT). | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097292f2-1aa5-42e4-aeee-c7d4cbdae17c
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c50743c237c66edcba1e6609dcd1ab9cb0081bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997221"
---
# <a name="configuring-identifiers-edifact"></a>Configuración de identificadores (EDIFACT)
En el acuerdo de socios comerciales, debe establecer la contraseña de referencia del destinatario para comprobar que no se recibe el intercambio por parte de destinatarios no autorizados.  
  
> [!IMPORTANT]
>  Las siguientes propiedades están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.  
> 
> - **DestinationPartyName** en **resoluciones de acuerdos adicionales** sección.  
> 
>   Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la lista anterior de propiedades están deshabilitadas en el **entidad A -> entidad B** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-set-the-sender-recipient-and-recipient-password"></a>Procedimiento para establecer el remitente, el destinatario y la contraseña de destinatario  
  
1.  Cree un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **identificadores**.  
  
3.  En el **remitente (UNB2)** sección, realice lo siguiente:  
  
    1.  Para **identificación (UNB2.1)**, escriba un valor alfanumérico con un mínimo y 35 como máximo. Este campo es obligatorio.  
  
    2.  Para **calificador de código (UNB2.2)**, seleccione un valor de la lista desplegable. Se trata de un campo opcional.  
  
    3.  Para **(UNB2.3) la dirección de enrutamiento inverso**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo. Se trata de un campo opcional.  
  
4.  En el **destinatario (UNB3)** sección, realice lo siguiente:  
  
    1.  Para **identificación (UNB3.1)**, escriba un valor alfanumérico con un mínimo y 35 como máximo. Este campo es obligatorio.  
  
    2.  Para **calificador de código (UNB3.2)**, seleccione un valor de la lista desplegable. Se trata de un campo opcional.  
  
    3.  Para **(UNB3.3) la dirección de enrutamiento inverso**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo. Se trata de un campo opcional.  
  
    4.  Si es necesario, en el **contraseña de referencia de destinatario (UNB6)** sección, especifique valores para la contraseña de referencia del destinatario. Para **valor (UNB6.1)**, escriba un valor alfanumérico con un mínimo y 14 como máximo. Para **calificador (UNB6.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de dos caracteres. Estos son los campos opcionales. Si estos valores no coinciden con los campos UNB6.1 y UNB6.2 en un intercambio recibido, BizTalk Server suspenderá el intercambio.  
  
        > [!NOTE]
        >  La combinación de **UNB6.1** y **UNB6.2** deben ser únicos.  
  
        > [!NOTE]
        >  Si escribe valores para UNB6.1 y UNB6.2, aplique los cambios y deje en blanco UNB6.1, el valor de UNB6.2 también se eliminará y el campo quedará deshabilitado.  
  
5.  En el **resoluciones de acuerdos adicionales** sección, para **DestinationPartyName** propiedad, especifique un valor para la entidad de destino. Este valor también se usa para resolver los mensajes de salida a un acuerdo. Para obtener más información, vea [resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).  
  
    > [!NOTE]
    >  Normalmente no es necesario establecer la **DestinationPartyName** propiedad. Esta propiedad está disponible como parte de las propiedades de acuerdo para admitir escenarios de actualización. Al actualizar desde BizTalk Server 2006 R2 o BizTalk Server 2009, el **DestinationPartyName** propiedad está establecida en el nombre de la entidad en BizTalk Server 2006 R2 o BizTalk Server 2009.  
  
6.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
    > [!IMPORTANT]
    >  Si hace clic en **Aceptar** o **aplicar** en esta fase, se producirá un error. Eso es porque aún tiene que proporcionar valores UNB2 y UNB3 en la **identificadores** pestaña de la ficha del acuerdo unidireccional.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las opciones de intercambio (EDIFACT)](../core/configuring-interchange-settings-edifact.md)