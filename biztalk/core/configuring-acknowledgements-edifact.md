---
title: Configuración de confirmaciones (EDIFACT). | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9436feb7-4c29-4b7c-b5c2-991660e6c1a9
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 269acfa79808f133f4332371d98e491fc8a0b2e1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991373"
---
# <a name="configuring-acknowledgements-edifact"></a>Configuración de confirmaciones (EDIFACT)
En el acuerdo de socios comerciales, puede especificar qué tipo de confirmación se va a devolver a una entidad y qué tipo de puerto de envío se va a usar para enviar la confirmación. También se especifica si se va a procesar por lotes una confirmación, el número de referencia inicial del conjunto de transacciones correspondiente a la confirmación y si se generan bucles SG1/SG4 para los conjuntos de transacciones aceptados.  
  
> [!IMPORTANT]
>  Las siguientes propiedades están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.  
> 
> - **Generar bucle SG1/SG4 para conjuntos de transacciones aceptadas (si se desactiva, bucle se generará sólo si UCM.5 no es igual a 7)**.  
> 
>   Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la lista anterior de propiedades están deshabilitadas en el **entidad A -> entidad B** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a>Para configurar las propiedades globales de confirmación (CONTRL) de EDIFACT  
  
1.  Cree un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **confirmaciones**.  
  
3.  En el **sección EDIFACT ACK (Control)**, realice lo siguiente:  
  
    1.  Seleccione **recepción del mensaje (CONTRL) esperada** para devolver una confirmación técnica (CONTRL) al remitente del intercambio. Si **recepción del mensaje (CONTRL) esperada** está seleccionada, seleccione **no procesar por lotes la recepción de mensaje del mensaje (CONTRL)** para enviar cada confirmación por separado, o déjela desactivada para procesar por lotes las confirmaciones.  
  
    2.  Seleccione **confirmación (CONTRL) esperada** para devolver una confirmación funcional (CONTRL) al remitente del intercambio. Si **confirmación (CONTRL) esperada** está seleccionada, seleccione **no procesar por lotes confirmación (CONTRL)** para enviar cada confirmación funcional por separado, o déjela desactivada para procesar por lotes la funcional confirmaciones.  
  
4.  En el **informe de aceptación del estado del conjunto de transacciones** sección, para forzar la generación de bucles SG1/SG4 en confirmaciones CONTRL funcionales para conjuntos de transacciones aceptados, seleccione **SG1/SG4 generar bucle para aceptado conjuntos de transacciones (si se desactiva, bucle se generará sólo si UCM.5 no es igual a 7)**. Para obtener más información acerca de los bucles SG1/SG4, vea [mensaje CONTRL de EDIFACT como confirmación funcional](../core/edifact-contrl-message-as-functional-acknowledgment.md).  
  
5.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las opciones de intercambio (EDIFACT)](../core/configuring-interchange-settings-edifact.md)