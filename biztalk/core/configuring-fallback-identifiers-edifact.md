---
title: Configuración de identificadores de reserva (EDIFACT). | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2ce56c1-44f1-42dc-94e8-36e5ba664f53
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7db7e20f8ccb4db8da53483e7c33285f4b75afb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991989"
---
# <a name="configuring-fallback-identifiers-edifact"></a>Configuración de identificadores de reserva (EDIFACT)
En el acuerdo de reserva, debe establecer la contraseña de referencia del destinatario para comprobar que no se recibe el intercambio por parte de destinatarios no autorizados.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-set-the-sender-recipient-recipient-password"></a>Para establecer el remitente, destinatario y la contraseña de destinatario  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2. En el **configuración de reserva de EDIFACT** cuadro de diálogo el **páginas del acuerdo EDIFACT** , bajo el **configuración de intercambio** sección, haga clic en **identificadores** .  
  
3. En el **remitente (UNB2)** sección, realice lo siguiente:  
  
   1.  Para **identificación (UNB2.1)**, escriba un valor alfanumérico con un mínimo y 35 como máximo. Este campo es obligatorio.  
  
   2.  Para **calificador de código (UNB2.2)**, seleccione un valor de la lista desplegable. Se trata de un campo opcional.  
  
   3.  Para **(UNB2.3) la dirección de enrutamiento inverso**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo. Se trata de un campo opcional.  
  
   4.  Para **Id. de referencia (UNB7)**, escriba un valor alfanumérico con un carácter como mínimo y seis caracteres como máximo. Este campo es obligatorio.  
  
4. En el **destinatario (UNB3)** sección, realice lo siguiente:  
  
   1.  Para **identificación (UNB3.1)**, escriba un valor alfanumérico con un mínimo y 35 como máximo. Este campo es obligatorio.  
  
   2.  Para **calificador de código (UNB3.2)**, seleccione un valor de la lista desplegable. Se trata de un campo opcional.  
  
   3.  Para **(UNB3.3) la dirección de enrutamiento inverso**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo. Se trata de un campo opcional.  
  
   4.  Si es necesario, en el **contraseña de referencia de destinatario (UNB6)** sección, especifique valores para la contraseña de referencia del destinatario. Para **valor (UNB6.1)**, escriba un valor alfanumérico con un mínimo y 14 como máximo. Para **calificador (UNB6.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de dos caracteres. Estos son los campos opcionales. Si estos valores no coinciden con los campos UNB6.1 y UNB6.2 en un intercambio recibido, BizTalk Server suspenderá el intercambio.  
  
       > [!NOTE]
       >  La combinación de **UNB6.1** y **UNB6.2** deben ser únicos.  
  
       > [!NOTE]
       >  Si escribe valores para UNB6.1 y UNB6.2, aplique los cambios y deje en blanco UNB6.1, el valor de UNB6.2 también se eliminará y el campo quedará deshabilitado.  
  
5. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de EDIFACT para el procesamiento de intercambio](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)