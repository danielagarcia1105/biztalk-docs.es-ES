---
title: Configuración de confirmaciones (X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eec2dbff-5d04-4a38-bad0-33d040b6dd12
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28df03b8955c17888a4722c361a2e4481c63b413
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970701"
---
# <a name="configuring-acknowledgements-x12"></a>Configuración de confirmaciones (X12)
En el acuerdo de socios comerciales, se puede especificar cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera las confirmaciones en respuesta a intercambios con codificación X12 recibidos de la entidad y qué tipo de confirmación se devuelve a la entidad. También se puede especificar si una confirmación debe procesarse por lotes y si se generan bucles AK2 para los conjuntos de transacciones aceptados. Esta sección proporciona instrucciones acerca de cómo hacerlo.  
  
> [!NOTE]
>  Las propiedades de confirmación descritas aquí se aplican también para las confirmaciones de HIPAA.  
> 
> [!IMPORTANT]
>  Las siguientes propiedades están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.  
> 
> - **Incluir bucle AK2 para conjuntos de transacciones aceptadas (si se desactiva, bucle se generará sólo si AK501 no es igual a)**.  
> 
>   Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la lista anterior de propiedades están deshabilitadas en el **entidad A -> entidad B** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-x12-ack-properties"></a>Para configurar las propiedades de confirmación de X12  
  
1.  Crear un acuerdo de codificación, como se describe en X12 [configuración General de las opciones (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de intercambio**, haga clic en **confirmaciones**.  
  
3.  Seleccione **TA1 esperado** para devolver una confirmación técnica (TA1) al remitente del intercambio. Si ha seleccionado, seleccione **no procesar por lotes TA1** para enviar cada confirmación técnica por separado, o bien deje la casilla desactivada para procesar por lotes las confirmaciones técnicas.  
  
4.  Seleccione **997 esperado** para devolver una confirmación funcional (997) al remitente del intercambio. Si ha seleccionado, seleccione **no procesar por lotes 997** para enviar cada confirmación funcional por separado, o bien deje la casilla desactivada para procesar por lotes las confirmaciones funcionales.  
  
5.  Para habilitar la generación de bucles AK2 en 997 confirmaciones para conjuntos de transacciones aceptadas, seleccione **incluir bucle AK2 para conjuntos de transacciones aceptadas (si se desactiva, bucle se generará sólo si AK501 no es igual a)**. Para obtener más información acerca de los bucles AK2, vea [X12 confirmación 997](../core/x12-997-acknowledgment.md).  
  
6.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las opciones de intercambio (X12)](../core/configuring-interchange-settings-x12.md)