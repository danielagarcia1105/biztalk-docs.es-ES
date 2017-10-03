---
title: "Configuración de Host Local de reserva (configuración de intercambio de X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b552fa2b-1154-491f-9bcf-aaba3b8f343f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a220f9c15c09cf667cf9b7b1805eba72634a17a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-local-host-settings-x12-interchange-settings"></a>Configuración de las opciones de host local de reserva (configuración de intercambio X12)
La configuración de host local rige cómo se procesan los intercambios EDI. La configuración de esta página puede dividirse en dos categorías: configuración del receptor (para intercambios de entrada) y configuración del remitente (para intercambios de salida). Como parte de la configuración del destinatario, puede especificar cómo se generará ST02, el número de control de confirmación. Como parte de la configuración del remitente, se puede especificar cómo se generan los números de control de mensajes de salida.  
  
> [!NOTE]
>  La configuración descrita aquí también se aplica a los intercambios HIPAA.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-local-host--receivers-settings"></a>Para configurar el host local – configuración del receptor  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.  
  
2.  En el **X12 configuración de reserva** cuadro de diálogo la **X12 páginas del acuerdo** , bajo la **configuración de intercambio** sección, haga clic en **configuración de Host Local** .  
  
3.  Para designar el intervalo de números de control de conjunto de transacciones utilizados en una confirmación, escriba valores en la **número de Control de confirmación (ST02)** campos. Especifique un valor numérico para los dos campos que quedan en la mitad y un valor alfanumérico (si desea) para los campos de prefijo y sufijo. Los campos que quedan en la mitad son necesarios y contienen los valores mínimo y máximo para el número de control, el prefijo y el sufijo son opcionales. La longitud máxima de los tres campos es de nueve caracteres.  
  
     Restablecer actual del conjunto de transacciones número de control en el valor mínimo, haga clic en **restablecer**. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer el número de control en el límite inferior una vez que ha superado el valor máximo.  
  
### <a name="to-configure-local-host--senders-settings"></a>Procedimiento para configurar el host local – configuración del remitente  
  
1.  Para **número de control de intercambio (ISA13)**, especifique un intervalo de valores para el número de control de intercambio que se usará el servidor BizTalk Server para generar un intercambio saliente. Especifique un valor numérico con un mínimo de 1 y un máximo de 999999999. Se trata de un campo obligatorio.  
  
     Para restablecer el número de control en el valor mínimo especificado, haga clic en el **restablecer** botón. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer automáticamente al valor mínimo si se supera el valor máximo.  
  
2.  Para **número de control de grupo (GS06)**, escriba el intervalo de números que BizTalk Server debe usar para el número de control de grupo. Especifique un valor numérico con un mínimo de un carácter y un máximo de nueve caracteres. Este campo es obligatorio.  
  
     Para restablecer el número de control de grupo para el valor mínimo especificado, haga clic en el **restablecer** botón. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer automáticamente al valor mínimo si se supera el valor máximo.  
  
3.  Para **número de Control de conjunto de transacciones (ST02)**, haga clic en **aplicar Id. nuevo**y, a continuación, escriba un intervalo de valores numéricos para los campos obligatorios centrales y valores alfanuméricos para el prefijo y sufijo opcionales. La longitud máxima de los cuatro campos es de nueve caracteres.  
  
     Restablecer actual del conjunto de transacciones número de control en el valor mínimo, haga clic en **restablecer**. Seleccione **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer el número de control en el valor mínimo si se ha superado el valor máximo.  
  
4.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de X12 propiedades de acuerdo de reserva para el procesamiento de intercambio](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)