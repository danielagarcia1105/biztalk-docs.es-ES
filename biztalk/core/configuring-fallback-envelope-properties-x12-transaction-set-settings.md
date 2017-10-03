---
title: "Configuración de las propiedades de sobres de reserva (configuración de conjunto de transacciones de X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a951f70-07d5-4a58-b1ea-e7117a45c545
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa7898d1e1a83da879400a89d5cd089ef2d4069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-x12-transaction-set-settings"></a>Configuración de propiedades de sobres de reserva (configuración del conjunto de transacciones X12)
En el **sobres** página de la **configuración del conjunto de transacciones** sección, defina cómo BizTalk Server genera los segmentos GS de un intercambio codificado en X12 que envía a la entidad. El segmento GS identifica y especifica un grupo funcional para un intercambio con codificación X12.  
  
> [!NOTE]
>  Este tema se aplica también a valores de configuración relacionados con HIPAA.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-define-the-gs-segments"></a>Procedimiento para definir segmentos GS  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.  
  
2.  En el **X12 configuración de reserva** cuadro de diálogo la **X12 páginas del acuerdo** , bajo la **configuración del conjunto de transacciones** sección, haga clic en **sobres**.  
  
3.  Para **código funcional (GS01)**, seleccione un valor de la lista desplegable.  
  
4.  Para **remitente de aplicación (GS02)**, escriba un valor alfanumérico con un mínimo de 2 y un máximo de 15. Este campo es obligatorio.  
  
5.  Para **receptor de aplicación (GS03)**, escriba un valor alfanumérico con un mínimo de 2 y un máximo de 15. Este campo es obligatorio.  
  
6.  Para **formato de fecha (GS04)**, seleccione SSAAMMDD o AAMMDD en la lista desplegable. Este campo es obligatorio.  
  
7.  Para **formato de hora (GS05)**, seleccione HHMM, HHMMSS o HHMMSSdd de la lista desplegable. Este campo es obligatorio.  
  
8.  Para **Agencia responsable (GS07)**, seleccione el valor de la lista desplegable.  
  
9. Para **identificador de documento (GS08)**, escriba un valor alfanumérico con un mínimo de 1 y un máximo de 12. Se trata de un campo opcional.  
  
10. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar X12 configuración propiedades del acuerdo de reserva para transacciones](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)