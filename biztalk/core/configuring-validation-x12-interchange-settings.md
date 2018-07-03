---
title: Configuración de la validación (configuración de intercambio X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdad7016-1d66-4d11-b620-c28368f00133
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eba4a7cbeffe342e37c366c3ce391018beec748
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988701"
---
# <a name="configuring-validation-x12-interchange-settings"></a>Configuración de la validación (configuración de intercambio de X12)
La configuración de la generación de validación de intercambio X12 define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprueba si existen números de control duplicados en el intercambio recibido.  
  
> [!NOTE]
>  La configuración descrita aquí también se aplica a la validación de intercambio HIPAA.  
  
> [!IMPORTANT]
>  Ninguna propiedad está deshabilitada en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-validation"></a>Para configurar la validación  
  
1. Crear un acuerdo de codificación, como se describe en X12 [configuración General de las opciones (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2. En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **validación**.  
  
3. Seleccione el **número de Control de intercambio** casilla de verificación para habilitar la canalización de recepción bloquee los intercambios duplicados. Si se ha seleccionado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprobará que el número de control de intercambio (ISA13) para el intercambio recibido no coincide con el número de control de intercambio. Si se detecta una coincidencia, la canalización de recepción no procesará el intercambio.  
  
4. Si **Interchange Control Number** está seleccionado, en el **comprobar isa13 duplicados dentro de** , escriba el número de días que se realizará una comprobación de intercambios duplicados mediante un determinado número de control de intercambio.  
  
5. Seleccione **número de Control de grupo** para impedir que la canalización de recepción procese los intercambios con números de control de grupo duplicados (GS6).  
  
6. Seleccione **número de Control de conjunto de transacciones** para impedir que la canalización de recepción procese los intercambios con números de control de conjunto de transacciones duplicados (ST2).  
  
7. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las opciones de intercambio (X12)](../core/configuring-interchange-settings-x12.md)