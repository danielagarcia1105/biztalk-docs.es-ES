---
title: Configuración de Host Local de reserva (configuración de intercambio EDIFACT) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eecf5abb-9c12-44b0-bc58-94cb138515c3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a503a54e712026295c5df295e7ed6d8e2408a9a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001845"
---
# <a name="configuring-fallback-local-host-settings-edifact-interchange-settings"></a>Configuración de las opciones de host local de reserva (configuración de intercambio EDIFACT)
La configuración de host local rige cómo se procesan los intercambios EDI. La configuración de esta página puede dividirse en dos categorías: configuración del receptor (para intercambios de entrada) y configuración del remitente (para intercambios de salida). Como parte de la configuración del receptor, se puede especificar cómo se generan los números de control de confirmaciones. Como parte de la configuración del remitente, se puede especificar cómo se generan los números de control de mensajes de salida.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-local-host--receivers-settings"></a>Para configurar el host local – configuración del receptor  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.  
  
2. En el **configuración de reserva de EDIFACT** cuadro de diálogo el **páginas del acuerdo EDIFACT** , bajo el **configuración de intercambio** sección, haga clic en **Host Local Configuración de**.  
  
3. En el **EDIFACT ACK** sección, para designar los números de referencia de conjunto de transacciones que se usará en una confirmación, escriba un valor para el prefijo, un intervalo de números de referencia y el sufijo.  
  
    Haga clic en **restablecer** Restablecer actual conjunto de transacciones en el límite inferior. Seleccione **restablecer al límite inferior cuando se encuentra fuera del límite** tener [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] restablecer el número de referencia en el límite inferior del valor de intervalo si se supera el límite máximo.  
  
### <a name="to-configure-local-host--senders-settings"></a>Procedimiento para configurar el host local – configuración del remitente  
  
1.  Para **número de control de intercambio (UNB5)**, especifique un intervalo de valores para el número de control de intercambio que se usará el servidor BizTalk Server en generar un intercambio saliente. Especifique un valor numérico con un mínimo de 1 y un máximo de 999999999. Se trata de un campo obligatorio.  
  
    > [!NOTE]
    >  El primer campo (**UNB5.1**) es el prefijo; el segundo y el tercer campo (**UNB5.2**) contienen el intervalo de números que se usará como el número de control de intercambio; y el cuarto campo (**UNB5.3**) es el sufijo. El prefijo y el sufijo son opcionales; el número de control es obligatorio. El número de control aumenta para cada mensaje nuevo; el prefijo y el sufijo continúan siendo el mismo. El número máximo de caracteres es 14 para el número de control, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.  
    >   
    >  Para restablecer el número de control en el valor mínimo especificado, haga clic en el **restablecer** botón. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer automáticamente al valor mínimo si se supera el valor máximo.  
  
2.  Para **número de control de grupo (UNG5)**, escriba el prefijo, que hacen referencia a intervalo de números y el sufijo que BizTalk Server debe usar para el número de control de grupo del primer intercambio que envía.  
  
    > [!NOTE]
    >  El primer campo (**UNG5.1**) es el prefijo; el segundo y el tercer campo (**UNG5.2**) contienen el intervalo de números que se utilizará para el número de control de grupo; y el cuarto campo (**UNG5.3**) es el sufijo. El prefijo y el sufijo son opcionales; el número de control es obligatorio. El número de control aumenta para cada mensaje nuevo, hasta que se alcanza el valor máximo; el prefijo y el sufijo continúan siendo el mismo. Sólo se permiten números en **UNG5.2**. El número máximo de caracteres es 14 para el número de control, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.  
    >   
    >  Para restablecer el número de control de grupo en el valor mínimo especificado, haga clic en el **restablecer** botón. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer automáticamente al valor mínimo si se supera el valor máximo.  
  
3.  Para **encabezado del mensaje (UNH)**, haga clic en **aplicar Id. nuevo**, escriba el prefijo, escriba el intervalo de números de referencia y escriba el sufijo que BizTalk Server debe usar para el número de referencia de conjunto de transacciones.  
  
    > [!NOTE]
    >  El primer campo (**UNH1.1**) es el prefijo; el segundo y el tercer campo (**UNH1.2**) son el intervalo de números de referencia; y el cuarto campo (**UNH1.3**) es el sufijo. El prefijo y el sufijo son opcionales; el número de referencia es obligatorio. El número de referencia aumenta para cada mensaje nuevo; el prefijo y el sufijo continúan siendo el mismo. El intervalo de valores predeterminado para el número referencia es de 1 a 99999999999999. Sólo se permiten números en **UNH1.2**. El número máximo de caracteres es 14 para el número de control, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.  
    >   
    >  Para restablecer actual del conjunto de transacciones número de control en el valor mínimo, haga clic en **restablecer**. Seleccione **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer el número de control al valor mínimo si se ha superado el valor máximo.  
  
4.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de EDIFACT para el procesamiento de intercambio](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)