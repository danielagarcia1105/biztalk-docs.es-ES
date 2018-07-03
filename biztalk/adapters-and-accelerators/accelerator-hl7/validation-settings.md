---
title: Configuración de la validación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, configuring
- configuring, validating
ms.assetid: ee08acac-99f9-4403-b2ae-01b80378aa58
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01f85c02434f8b20124258d95fd484c79809b509
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966325"
---
# <a name="validation-settings"></a>Configuración de la validación
Uso de [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], puede validar los mensajes con el estándar HL7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] garantiza que los mensajes que envíe o reciba un segmento de estructura y el cuerpo de mensaje que se ajusta al estándar HL7. También puede validar HL7 admitidas tipos de datos personalizados y permitir delimitadores finales. Usa el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración **validación** tab para configurar la validación.  

## <a name="configuring-validation-settings"></a>Configuración de las opciones de validación  
 Usa el **validación** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración (bajo el alto nivel **partes** pestaña) para configurar las opciones de validación. Puede seleccionar los siguientes tipos de validación:  

- Sintaxis, estructura y la validación esquemática en segmentos de cuerpo, según el esquema de mensaje  

- Validación de estándar HL7 en tipos de datos personalizados (DT, TS, TM y TN)  

- Validación de los delimitadores de campo (se permiten delimitadores finales)  

  Mediante esta pestaña, también puede establecer el espacio de nombres de esquema utilizado para la validación en los mensajes para esta entidad.  

  La siguiente ilustración muestra el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración Explorer **validación** ficha.  

  ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")  
  Pestaña validación de explorador de configuración de BTAHL7  

  Use los procedimientos siguientes para configurar las opciones de validación.  

#### <a name="to-open-btahl7-configuration-explorer"></a>Para abrir el Explorador de configuración de BTAHL7  

-   Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  

#### <a name="to-configure-validation-settings"></a>Procedimiento para configurar la configuración de validación  

1. En el Explorador de configuración de BTAHL7 en el **validación** ficha, realice lo siguiente:  


   |                  Use                  |                                            Para                                            |
   |--------------------------------------------|--------------------------------------------------------------------------------------------------|
   |         **Validar los segmentos de cuerpo**         |             Seleccione esta opción para realizar la sintaxis, estructura y la validación de esquema.              |
   |       **Validar tipo de datos personalizado**        |  Seleccione esta opción para realizar una validación estándar HL7 en DT, TS, TM y TN tipos de datos personalizados.  |
   | **Permitir (separadores) delimitadores finales** |           Seleccione esta opción para habilitar los delimitadores de campo finales en las instancias de mensaje.           |
   |            **Esquema Namespace**            | Escriba la ubicación del espacio de nombres de esquema. El valor predeterminado es http://microsoft.com/HealthCare/HL7/2X. |


2. Haga clic en **Guardar**.  

## <a name="see-also"></a>Vea también  
 [Configuración de registro](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)   
 [Configuración de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)   
[Registro operativo, procesamiento de mensajes por lotes, validación y configuración de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)