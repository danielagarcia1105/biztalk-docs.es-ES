---
title: Configuración de Host Local de reserva (configuración del conjunto de transacciones EDIFACT) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0142b3fc-009f-4da5-b34d-dddf4fb96e0f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 222b10c5145b67d7381a00cb389b9705a50c7d5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987405"
---
# <a name="configuring-fallback-local-host-settings-edifact-transaction-set-settings"></a>Configuración de las opciones de host local de reserva (configuración del conjunto de transacciones de EDIFACT)
Para procesar un intercambio entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe determinar el esquema que necesita usar en el procesamiento y la validación del intercambio. Esto consiste en determinar el espacio de nombres de destino asociado al esquema y el esquema que se va a utilizar. En esta página de acuerdo de reserva, especifique las propiedades que se van a usar en la determinación del espacio de nombres de destino. Cómo BizTalk Server determina el esquema se describe en [resolución de acuerdos, detección de esquemas y autorización para los mensajes EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>Para configurar el host local para conjuntos de transacciones  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2. En el **configuración de reserva de EDIFACT** cuadro de diálogo el **páginas del acuerdo EDIFACT** , bajo el **configuración del conjunto de transacciones** sección, haga clic en **Host Local Configuración de**.  
  
3. Seleccione **crear etiquetas XML vacías para separadores finales** para que el remitente del intercambio incluya etiquetas XML vacías para separadores finales.  
  
4. Seleccione **usar punto (.) como separador decimal** para habilitar BizTalk Server incluya un punto (.) en el mensaje XML creado a partir de un intercambio que contiene un número decimal.  
  
5. Para **Target Namespace**, escriba (o seleccione en la lista desplegable) el espacio de nombres de destino que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para determinar el esquema para procesar el mensaje recibido con  
  
6. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de EDIFACT para valores de conjuntos de transacciones](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)