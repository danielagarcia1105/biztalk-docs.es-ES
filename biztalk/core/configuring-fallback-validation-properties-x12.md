---
title: "Configuración de las propiedades de validación de reserva (X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a64431d-373a-4d63-9b83-cbb323620152
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc6eb44f2ee4c2f9c63011dc14be41380c245996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-validation-properties-x12"></a>Configuración de propiedades de validación de reserva (X12)
La configuración de reserva de generación de validación de intercambio X12 define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprueba si hay números de control duplicados en el intercambio recibido.  
  
> [!NOTE]
>  La configuración descrita aquí también se aplica a la validación de intercambio HIPAA.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-validation"></a>Para configurar la validación  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.  
  
2.  En el **X12 configuración de reserva** cuadro de diálogo la **X12 páginas del acuerdo** , bajo la **configuración de intercambio** sección, haga clic en **validación**.  
  
3.  Seleccione el **número de Control de intercambio** casilla de verificación para habilitar la canalización de recepción y bloquear los intercambios duplicados. Si se ha seleccionado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprobará que el número de control de intercambio (ISA13) para el intercambio recibido no coincide con el número de control de intercambio. Si se detecta una coincidencia, la canalización de recepción no procesará el intercambio.  
  
4.  Si **número de Control de intercambio** está seleccionada, en la **comprobar isa13 duplicados dentro de** , escriba el número de días que se realizará una comprobación de intercambios duplicados mediante un determinado número de control de intercambio.  
  
5.  Seleccione **número de Control de grupo** para impedir que la canalización de recepción procese los intercambios con números de control de grupo duplicado (GS6).  
  
6.  Seleccione **número de Control de conjunto de transacciones** para impedir que la canalización de recepción procese los intercambios con números de control de conjunto de transacciones duplicados (ST2).  
  
7.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de X12 propiedades de acuerdo de reserva para el procesamiento de intercambio](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)