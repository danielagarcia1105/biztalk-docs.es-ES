---
title: Configuración de las propiedades de sobres de reserva (configuración del conjunto de transacciones EDIFACT) | Microsoft Docs
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
ms.openlocfilehash: 6f060b37004346ae5b7419acbe9f1fcf1d128179
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020264"
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a>Configuración de propiedades de sobres de reserva (configuración del conjunto de transacciones EDIFACT)
En el **sobres** página de la **configuración del conjunto de transacciones** sección, defina cómo BizTalk Server genera los segmentos UNG para un intercambio con codificación EDIFACT que envía a la entidad.  
  
 El segmento UNG es el encabezado que identifica y especifica un grupo funcional de un intercambio codificado en EDIFACT. Contiene información acerca de la fecha y la hora en la que el grupo funcional se preparó, junto con el tipo y la versión del documento en el grupo funcional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-define-the-ung-segments"></a>Para definir segmentos UNG  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2. En el **configuración de reserva de EDIFACT** cuadro de diálogo el **páginas del acuerdo EDIFACT** , bajo el **configuración del conjunto de transacciones** sección, haga clic en **sobres** .  
  
3. Para **Id. de grupo funcional (UNG1)**, escriba un valor alfanumérico con un carácter como mínimo y seis caracteres como máximo. Este campo es obligatorio.  
  
4. Escriba los valores que identificar **remitente de la aplicación (UNG2)**.  
  
   -   Para **identificación (UNG2.1)**, escriba un valor alfanumérico con un carácter como mínimo y 35 caracteres como máximo. Este campo es obligatorio.  
  
   -   Para **calificador de código (UNG2.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de cuatro caracteres. Se trata de un campo opcional.  
  
5. Escriba los valores que identificar **destinatario de la aplicación (UNG3)**.  
  
   -   Para **identificación (UNG3.1)**, escriba un valor alfanumérico con un carácter como mínimo y 35 caracteres como máximo. Este campo es obligatorio.  
  
   -   Para **calificador de código (UNG3.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de cuatro caracteres. Se trata de un campo opcional.  
  
6. Para **Agencia de control (UNG6)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de dos caracteres. Este campo es obligatorio.  
  
7. Escriba los valores que identificar **versión del mensaje (UNG7)**.  
  
   -   Para **versión (UNG7.1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres. Este campo es obligatorio.  
  
   -   Para **versión (UNG7.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres. Este campo es obligatorio.  
  
   -   Para **asignado a la asociación (UNG7.3) código**, escriba un valor alfanumérico con un mínimo de 1 carácter y un máximo de 6 caracteres. Se trata de un campo opcional.  
  
8. Para **contraseña de aplicaciones (UNG8)**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo. Este campo es obligatorio.  
  
9. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de EDIFACT para valores de conjuntos de transacciones](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)