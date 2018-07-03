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
# <a name="validation-settings"></a><span data-ttu-id="745cf-102">Configuración de la validación</span><span class="sxs-lookup"><span data-stu-id="745cf-102">Validation Settings</span></span>
<span data-ttu-id="745cf-103">Uso de [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], puede validar los mensajes con el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="745cf-103">Using [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], you can validate your messages against the HL7 standard.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="745cf-104"> garantiza que los mensajes que envíe o reciba un segmento de estructura y el cuerpo de mensaje que se ajusta al estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="745cf-104"> ensures that the messages you send or receive have a message structure and body segment that conforms to the HL7 standard.</span></span> <span data-ttu-id="745cf-105">También puede validar HL7 admitidas tipos de datos personalizados y permitir delimitadores finales.</span><span class="sxs-lookup"><span data-stu-id="745cf-105">You can also validate HL7 supported custom data types, and allow trailing delimiters.</span></span> <span data-ttu-id="745cf-106">Usa el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración **validación** tab para configurar la validación.</span><span class="sxs-lookup"><span data-stu-id="745cf-106">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab to configure validation.</span></span>  

## <a name="configuring-validation-settings"></a><span data-ttu-id="745cf-107">Configuración de las opciones de validación</span><span class="sxs-lookup"><span data-stu-id="745cf-107">Configuring Validation Settings</span></span>  
 <span data-ttu-id="745cf-108">Usa el **validación** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración (bajo el alto nivel **partes** pestaña) para configurar las opciones de validación.</span><span class="sxs-lookup"><span data-stu-id="745cf-108">You use the **Validation** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure validation settings.</span></span> <span data-ttu-id="745cf-109">Puede seleccionar los siguientes tipos de validación:</span><span class="sxs-lookup"><span data-stu-id="745cf-109">You can select the following types of validation:</span></span>  

- <span data-ttu-id="745cf-110">Sintaxis, estructura y la validación esquemática en segmentos de cuerpo, según el esquema de mensaje</span><span class="sxs-lookup"><span data-stu-id="745cf-110">Syntax, structure, and schematic validation on body segments, based on the message schema</span></span>  

- <span data-ttu-id="745cf-111">Validación de estándar HL7 en tipos de datos personalizados (DT, TS, TM y TN)</span><span class="sxs-lookup"><span data-stu-id="745cf-111">HL7 standard validation on custom data types (DT, TS, TM, and TN)</span></span>  

- <span data-ttu-id="745cf-112">Validación de los delimitadores de campo (se permiten delimitadores finales)</span><span class="sxs-lookup"><span data-stu-id="745cf-112">Validation of field delimiters (trailing delimiters are allowed)</span></span>  

  <span data-ttu-id="745cf-113">Mediante esta pestaña, también puede establecer el espacio de nombres de esquema utilizado para la validación en los mensajes para esta entidad.</span><span class="sxs-lookup"><span data-stu-id="745cf-113">Using this tab, you can also set the schema namespace used for the validation on the messages for this party.</span></span>  

  <span data-ttu-id="745cf-114">La siguiente ilustración muestra el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración Explorer **validación** ficha.</span><span class="sxs-lookup"><span data-stu-id="745cf-114">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab.</span></span>  

  <span data-ttu-id="745cf-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span><span class="sxs-lookup"><span data-stu-id="745cf-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span></span>  
  <span data-ttu-id="745cf-116">Pestaña validación de explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="745cf-116">BTAHL7 Configuration Explorer Validation tab</span></span>  

  <span data-ttu-id="745cf-117">Use los procedimientos siguientes para configurar las opciones de validación.</span><span class="sxs-lookup"><span data-stu-id="745cf-117">Use the following procedures to configure validation settings.</span></span>  

#### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="745cf-118">Para abrir el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="745cf-118">To open BTAHL7 Configuration Explorer</span></span>  

-   <span data-ttu-id="745cf-119">Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="745cf-119">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  

#### <a name="to-configure-validation-settings"></a><span data-ttu-id="745cf-120">Procedimiento para configurar la configuración de validación</span><span class="sxs-lookup"><span data-stu-id="745cf-120">To configure validation settings</span></span>  

1. <span data-ttu-id="745cf-121">En el Explorador de configuración de BTAHL7 en el **validación** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="745cf-121">In BTAHL7 Configuration Explorer on the **Validation** tab, do the following:</span></span>  


   |                  <span data-ttu-id="745cf-122">Use</span><span class="sxs-lookup"><span data-stu-id="745cf-122">Use this</span></span>                  |                                            <span data-ttu-id="745cf-123">Para</span><span class="sxs-lookup"><span data-stu-id="745cf-123">To do this</span></span>                                            |
   |--------------------------------------------|--------------------------------------------------------------------------------------------------|
   |         <span data-ttu-id="745cf-124">**Validar los segmentos de cuerpo**</span><span class="sxs-lookup"><span data-stu-id="745cf-124">**Validate body segments**</span></span>         |             <span data-ttu-id="745cf-125">Seleccione esta opción para realizar la sintaxis, estructura y la validación de esquema.</span><span class="sxs-lookup"><span data-stu-id="745cf-125">Select this option to perform syntax, structure, and schema validation.</span></span>              |
   |       <span data-ttu-id="745cf-126">**Validar tipo de datos personalizado**</span><span class="sxs-lookup"><span data-stu-id="745cf-126">**Validate custom data type**</span></span>        |  <span data-ttu-id="745cf-127">Seleccione esta opción para realizar una validación estándar HL7 en DT, TS, TM y TN tipos de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="745cf-127">Select this option to perform HL7 standard validation on DT, TS, TM, and TN custom data types.</span></span>  |
   | <span data-ttu-id="745cf-128">**Permitir (separadores) delimitadores finales**</span><span class="sxs-lookup"><span data-stu-id="745cf-128">**Allow trailing delimiters (separators)**</span></span> |           <span data-ttu-id="745cf-129">Seleccione esta opción para habilitar los delimitadores de campo finales en las instancias de mensaje.</span><span class="sxs-lookup"><span data-stu-id="745cf-129">Select this option to enable trailing field delimiters in message instances.</span></span>           |
   |            <span data-ttu-id="745cf-130">**Esquema Namespace**</span><span class="sxs-lookup"><span data-stu-id="745cf-130">**Schema Namespace**</span></span>            | <span data-ttu-id="745cf-131">Escriba la ubicación del espacio de nombres de esquema.</span><span class="sxs-lookup"><span data-stu-id="745cf-131">Type the schema namespace location.</span></span> <span data-ttu-id="745cf-132">El valor predeterminado es http://microsoft.com/HealthCare/HL7/2X.</span><span class="sxs-lookup"><span data-stu-id="745cf-132">The default value is http://microsoft.com/HealthCare/HL7/2X.</span></span> |


2. <span data-ttu-id="745cf-133">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="745cf-133">Click **Save**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="745cf-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="745cf-134">See Also</span></span>  
 <span data-ttu-id="745cf-135">[Configuración de registro](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="745cf-135">[Logging Configuration](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span></span>  
 <span data-ttu-id="745cf-136">[Configuración de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span><span class="sxs-lookup"><span data-stu-id="745cf-136">[Acknowledgment Settings](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span></span>  
[<span data-ttu-id="745cf-137">Registro operativo, procesamiento de mensajes por lotes, validación y configuración de confirmaciones</span><span class="sxs-lookup"><span data-stu-id="745cf-137">Operational logging, message batching, validation and asknowledgment settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)