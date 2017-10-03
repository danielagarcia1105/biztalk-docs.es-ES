---
title: "Configuración de la validación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, configuring
- configuring, validating
ms.assetid: ee08acac-99f9-4403-b2ae-01b80378aa58
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 108f13dfbdc7b42027f57e70d913202b4d4e3100
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validation-settings"></a><span data-ttu-id="f05d8-102">Configuración de la validación</span><span class="sxs-lookup"><span data-stu-id="f05d8-102">Validation Settings</span></span>
<span data-ttu-id="f05d8-103">Usar [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], puede validar los mensajes en el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="f05d8-103">Using [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], you can validate your messages against the HL7 standard.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="f05d8-104">garantiza que los mensajes que envíe o reciba un segmento de estructura y el cuerpo de mensaje que se ajusta al estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="f05d8-104"> ensures that the messages you send or receive have a message structure and body segment that conforms to the HL7 standard.</span></span> <span data-ttu-id="f05d8-105">También puede validar HL7 admitidas tipos de datos personalizados y permitir que los delimitadores finales.</span><span class="sxs-lookup"><span data-stu-id="f05d8-105">You can also validate HL7 supported custom data types, and allow trailing delimiters.</span></span> <span data-ttu-id="f05d8-106">Usa el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **validación** ficha para configurar la validación.</span><span class="sxs-lookup"><span data-stu-id="f05d8-106">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab to configure validation.</span></span>  
  
## <a name="configuring-validation-settings"></a><span data-ttu-id="f05d8-107">Configuración de opciones de validación</span><span class="sxs-lookup"><span data-stu-id="f05d8-107">Configuring Validation Settings</span></span>  
 <span data-ttu-id="f05d8-108">Usa el **validación** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración (en el nivel superior **partes** pestaña) para configurar los valores de validación.</span><span class="sxs-lookup"><span data-stu-id="f05d8-108">You use the **Validation** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure validation settings.</span></span> <span data-ttu-id="f05d8-109">Puede seleccionar los siguientes tipos de validación:</span><span class="sxs-lookup"><span data-stu-id="f05d8-109">You can select the following types of validation:</span></span>  
  
-   <span data-ttu-id="f05d8-110">Sintaxis, la estructura y la validación de esquema en segmentos de cuerpo, tomando como base el esquema de mensaje</span><span class="sxs-lookup"><span data-stu-id="f05d8-110">Syntax, structure, and schematic validation on body segments, based on the message schema</span></span>  
  
-   <span data-ttu-id="f05d8-111">Validación de estándar HL7 en tipos de datos personalizados (DT, TS, TM y TN)</span><span class="sxs-lookup"><span data-stu-id="f05d8-111">HL7 standard validation on custom data types (DT, TS, TM, and TN)</span></span>  
  
-   <span data-ttu-id="f05d8-112">Validación de los delimitadores de campo (se permiten los delimitadores finales)</span><span class="sxs-lookup"><span data-stu-id="f05d8-112">Validation of field delimiters (trailing delimiters are allowed)</span></span>  
  
 <span data-ttu-id="f05d8-113">Mediante esta pestaña, también puede establecer el espacio de nombres de esquema utilizado para la validación en los mensajes para esta entidad.</span><span class="sxs-lookup"><span data-stu-id="f05d8-113">Using this tab, you can also set the schema namespace used for the validation on the messages for this party.</span></span>  
  
 <span data-ttu-id="f05d8-114">La siguiente ilustración muestra la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración explorador **validación** ficha.</span><span class="sxs-lookup"><span data-stu-id="f05d8-114">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")  
<span data-ttu-id="f05d8-115">Pestaña validación de explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="f05d8-115">BTAHL7 Configuration Explorer Validation tab</span></span>  
  
 <span data-ttu-id="f05d8-116">Utilice los procedimientos siguientes para configurar los valores de validación.</span><span class="sxs-lookup"><span data-stu-id="f05d8-116">Use the following procedures to configure validation settings.</span></span>  
  
#### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="f05d8-117">Para abrir el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="f05d8-117">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="f05d8-118">Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="f05d8-118">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
#### <a name="to-configure-validation-settings"></a><span data-ttu-id="f05d8-119">Procedimiento para configurar la configuración de validación</span><span class="sxs-lookup"><span data-stu-id="f05d8-119">To configure validation settings</span></span>  
  
1.  <span data-ttu-id="f05d8-120">En el Explorador de configuración de BTAHL7 en el **validación** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f05d8-120">In BTAHL7 Configuration Explorer on the **Validation** tab, do the following:</span></span>  
  
    |<span data-ttu-id="f05d8-121">Use</span><span class="sxs-lookup"><span data-stu-id="f05d8-121">Use this</span></span>|<span data-ttu-id="f05d8-122">Para</span><span class="sxs-lookup"><span data-stu-id="f05d8-122">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f05d8-123">**Validar los segmentos de cuerpo**</span><span class="sxs-lookup"><span data-stu-id="f05d8-123">**Validate body segments**</span></span>|<span data-ttu-id="f05d8-124">Seleccione esta opción para realizar la validación del esquema, la estructura y la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="f05d8-124">Select this option to perform syntax, structure, and schema validation.</span></span>|  
    |<span data-ttu-id="f05d8-125">**Validar el tipo de datos personalizados**</span><span class="sxs-lookup"><span data-stu-id="f05d8-125">**Validate custom data type**</span></span>|<span data-ttu-id="f05d8-126">Seleccione esta opción para realizar una validación estándar HL7 en DT, TS, TM y TN tipos de datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="f05d8-126">Select this option to perform HL7 standard validation on DT, TS, TM, and TN custom data types.</span></span>|  
    |<span data-ttu-id="f05d8-127">**Permitir finales delimitadores (separadores)**</span><span class="sxs-lookup"><span data-stu-id="f05d8-127">**Allow trailing delimiters (separators)**</span></span>|<span data-ttu-id="f05d8-128">Seleccione esta opción para habilitar los delimitadores finales de campo en instancias de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f05d8-128">Select this option to enable trailing field delimiters in message instances.</span></span>|  
    |<span data-ttu-id="f05d8-129">**Namespace de esquema**</span><span class="sxs-lookup"><span data-stu-id="f05d8-129">**Schema Namespace**</span></span>|<span data-ttu-id="f05d8-130">Escriba la ubicación del espacio de nombres de esquema.</span><span class="sxs-lookup"><span data-stu-id="f05d8-130">Type the schema namespace location.</span></span> <span data-ttu-id="f05d8-131">El valor predeterminado es http://microsoft.com/HealthCare/HL7/2X.</span><span class="sxs-lookup"><span data-stu-id="f05d8-131">The default value is http://microsoft.com/HealthCare/HL7/2X.</span></span>|  
  
2.  <span data-ttu-id="f05d8-132">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f05d8-132">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05d8-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="f05d8-133">See Also</span></span>  
 <span data-ttu-id="f05d8-134">[Configuración de registro](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f05d8-134">[Logging Configuration](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span></span>  
 <span data-ttu-id="f05d8-135">[Configuración de confirmación](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f05d8-135">[Acknowledgment Settings](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span></span>  
[<span data-ttu-id="f05d8-136">Registro operativo, el procesamiento por lotes de mensajes, validación y configuración de asknowledgment</span><span class="sxs-lookup"><span data-stu-id="f05d8-136">Operational logging, message batching, validation and asknowledgment settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)