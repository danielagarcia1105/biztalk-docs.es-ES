---
title: Configuración de identificadores de reserva (X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cb5b32c-96ec-4192-9a10-6668a2cb1195
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cced4cbb22be0f486542f092946462906bd674df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998229"
---
# <a name="configuring-fallback-identifiers-x12"></a>Configuración de identificadores de reserva (X12)
En el acuerdo de reserva, debe establecer las propiedades Autorización y Seguridad de X12, para asegurarse de que los destinatarios no autorizados no van a recibir el intercambio.  
  
> [!NOTE]
>  Las propiedades de procesamiento de intercambio que se describen aquí se aplican también a los intercambios HIPAA.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-set-sender-receiver-and-security-properties"></a>Para establecer las propiedades de remitente, destinatario y seguridad  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.  
  
2. En el **X12 configuración de reserva** cuadro de diálogo el **X12 páginas del acuerdo** , bajo el **configuración de intercambio** sección, haga clic en **identificadores**.  
  
3. Escriba valores para el **ISA1-2 (información y calificador de autorización)**. Seleccione el valor de la **calificador de autorización (ISA1)** de la lista desplegable asociada. Si este valor es distinto de **00**, para el **valor (ISA2)** texto, escriba un mínimo de un carácter alfanumérico y un máximo de 10. Se trata de un campo opcional. Si especifica estos valores, asegúrese de que coinciden con los campos ISA1 e ISA2 en un intercambio recibido; en caso contrario, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspenderá el intercambio.  
  
4. Escriba valores para el **ISA3-4 (información y calificador de seguridad)**. Seleccione el valor de la **calificador de seguridad (ISA3)** en la lista desplegable. Si este valor es distinto de **00**, para el **valor (ISA4)** texto, escriba un mínimo de caracteres alfanuméricos y un máximo de 10. Se trata de un campo opcional. Si estos valores no coinciden con los campos ISA3 e ISA4 en un intercambio recibido, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspenderá el intercambio.  
  
   > [!NOTE]
   >  El valor **03 – contraseña (para compatibilidad con versiones anteriores)**, se incluye por compatibilidad con versiones anteriores con [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y se quitará en futuras versiones.  
  
5. Especifique los valores de **ISA5-6 (identificador y calificador de remitente)**. Seleccione un valor para el calificador de la **calificador de Id. de remitente (ISA5)** lista desplegable. Para obtener el identificador, en el **valor (ISA6)** texto, escriba un mínimo de un carácter alfanumérico y un máximo de 15 caracteres.  
  
6. Especifique los valores de **ISA7-8 (calificador e identificador)**. Seleccione un valor para el calificador de la **calificador de Id. de receptor (ISA7)** lista desplegable. Para obtener el identificador, en el **valor (ISA8)** texto, escriba un mínimo de un carácter alfanumérico y un máximo de 15 caracteres.  
  
7. Haga clic en **aplicar** para aceptar los cambios o haga clic en **Aceptar** para introducir y validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de X12 para el procesamiento de intercambio](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)