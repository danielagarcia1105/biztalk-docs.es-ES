---
title: Configuración de las propiedades de sobres de reserva (configuración del conjunto de transacciones EDIFACT) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b56a5a93-35ac-4293-b00e-28dcd89dfa2a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93f9aae6d67e5dc56d383626e36d1db412be9d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233724"
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a>Configuración de propiedades de sobres de reserva (configuración del conjunto de transacciones EDIFACT)
En el **sobres** página de la **configuración del conjunto de transacciones** sección, defina cómo BizTalk Server genera los segmentos UNG para un intercambio con codificación EDIFACT que envía a la entidad.  
  
 El segmento UNG es el encabezado que identifica y especifica un grupo funcional de un intercambio codificado en EDIFACT. Contiene información acerca de la fecha y la hora en la que el grupo funcional se preparó, junto con el tipo y la versión del documento en el grupo funcional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-define-the-ung-segments"></a>Para definir segmentos UNG  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2.  En el **configuración de reserva de EDIFACT** cuadro de diálogo la **páginas del acuerdo EDIFACT** , bajo la **configuración del conjunto de transacciones** sección, haga clic en **sobres** .  
  
3.  Para **Id. de grupo funcional (UNG1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de seis caracteres. Este campo es obligatorio.  
  
4.  Escriba los valores para identificar **remitente de aplicación (UNG2)**.  
  
    -   Para **identificación (UNG2.1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 35 caracteres. Este campo es obligatorio.  
  
    -   Para **calificador de código (UNG2.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de cuatro caracteres. Se trata de un campo opcional.  
  
5.  Escriba los valores para identificar **destinatario de la aplicación (UNG3)**.  
  
    -   Para **identificación (UNG3.1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 35 caracteres. Este campo es obligatorio.  
  
    -   Para **calificador de código (UNG3.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de cuatro caracteres. Se trata de un campo opcional.  
  
6.  Para **Agencia de control (UNG6)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de dos caracteres. Este campo es obligatorio.  
  
7.  Escriba los valores para identificar **versión del mensaje (UNG7)**.  
  
    -   Para **versión (UNG7.1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres. Este campo es obligatorio.  
  
    -   Para **versión (UNG7.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres. Este campo es obligatorio.  
  
    -   Para **código (UNG7.3) asignado a la asociación**, escriba un valor alfanumérico con un mínimo de 1 carácter y un máximo de 6 caracteres. Se trata de un campo opcional.  
  
8.  Para **contraseña de aplicaciones (UNG8)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 14 caracteres. Este campo es obligatorio.  
  
9. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar la configuración de propiedades de acuerdo de reserva de EDIFACT para la transacción](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)