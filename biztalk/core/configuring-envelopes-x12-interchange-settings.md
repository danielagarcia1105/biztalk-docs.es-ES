---
title: "Configuración de sobres (configuración de intercambio de X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4fade73-14cf-475c-81b5-6102c75db991
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4f88ee1e5d786367c1a4bc0f5b2404fd5c1a37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-x12-interchange-settings"></a>Configuración de sobres (configuración de intercambio de X12)
La configuración de generación de sobres de intercambio X12 define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera el sobre de un intercambio con codificación X12 que va a enviarse a la entidad de recepción. En esta sección, se define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera el segmento ISA para un intercambio con codificación X12 que envía a la entidad. Un segmento ISA es el encabezado de control de intercambio para un intercambio con codificación X12.  
  
> [!NOTE]
>  Para el tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la longitud de los campos ISA alfanuméricos es fija. Sin embargo, para el [!INCLUDE[TPM](../includes/tpm-md.md)] interfaz de usuario, puede escribir un único carácter de un campo ISA alfanumérico. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]rellenará estos campos con caracteres de espacio finales para garantizar el cumplimiento con los requisitos estándar.  
  
> [!NOTE]
>  La configuración descrita aquí también se aplica a la generación de sobres de intercambio HIPAA.  
  
> [!IMPORTANT]
>  Todas las propiedades se deshabilitan en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
>   
>  Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-define-the-envelope"></a>Para definir el sobre  
  
1.  Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **sobres**.  
  
3.  En **uso de ISA11**, mantener **identificador estándar** seleccionado para especificar un identificador estándar en lugar de un separador de repeticiones y, a continuación, seleccione un valor para el identificador estándar en la lista desplegable. Seleccione **separador de repeticiones** para especificar un separador de repeticiones en lugar de un identificador estándar y, a continuación, escriba un único carácter como separador de repeticiones. El separador de repeticiones, que se usa para separar segmentos que se repiten en un conjunto de transacciones, está limitado a los valores del juego de caracteres ASCII.  
  
4.  Para **controlar el número de versión (ISA12)**, seleccione la versión de la X12 estándar que va a usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para generar un intercambio saliente.  
  
5.  Para **indicador de uso (ISA15)**, seleccione esta opción para indicar si un intercambio generado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es información, datos de producción o datos de prueba.  
  
6.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de intercambio (X12)](../core/configuring-interchange-settings-x12.md)