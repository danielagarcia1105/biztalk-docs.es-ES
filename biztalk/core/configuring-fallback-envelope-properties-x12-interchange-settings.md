---
title: Configuración de las propiedades de sobres de reserva (configuración de intercambio X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e9b05ea-2a0f-42d6-adc2-c1f1f2b7a993
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72fa2217b04b118160853b8c229a7d514a6583c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010677"
---
# <a name="configuring-fallback-envelope-properties-x12-interchange-settings"></a>Configuración de propiedades de sobre de reserva (configuración de intercambio X12)
La configuración de generación de sobres de intercambio X12 define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera el sobre de un intercambio con codificación X12 que va a enviarse a la entidad de recepción. En este acuerdo de reserva, defina cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera el segmento ISA para un intercambio con codificación X12 que envía a la entidad. Un segmento ISA es el encabezado de control de intercambio para un intercambio con codificación X12.  
  
> [!NOTE]
>  Para el tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la longitud de los campos ISA alfanuméricos es fija. Sin embargo, para el [!INCLUDE[TPM](../includes/tpm-md.md)] interfaz de usuario, puede escribir un único carácter para un campo ISA alfanumérico. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rellenará estos campos con caracteres de espacio finales para garantizar el cumplimiento con los requisitos estándar.  
> 
> [!NOTE]
>  La configuración descrita aquí también se aplica a la generación de sobres de intercambio HIPAA.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-define-the-envelope"></a>Para definir el sobre  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.  
  
2. En el **X12 configuración de reserva** cuadro de diálogo el **X12 páginas del acuerdo** , bajo el **configuración de intercambio** sección, haga clic en **sobres**.  
  
3. En **uso de ISA11**, mantener **identificador estándar** seleccionado para especificar un identificador estándar en lugar de un separador de repeticiones y, a continuación, seleccione un valor para el identificador estándar en la lista desplegable. Seleccione **separador de repeticiones** para especificar un separador de repeticiones en lugar de un identificador estándar y, a continuación, escriba un único carácter como separador de repeticiones. El separador de repeticiones, que se usa para separar segmentos que se repiten en un conjunto de transacciones, está limitado a los valores del juego de caracteres ASCII.  
  
4. Para **controlar el número de versión (ISA12)**, seleccione la versión de los estándar que va a usar X12 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para generar un intercambio saliente.  
  
5. Para **indicador de uso (ISA15)**, seleccione esta opción para indicar si un intercambio generado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es información, datos de producción o datos de prueba.  
  
6. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdos de reserva de X12 para el procesamiento de intercambio](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)