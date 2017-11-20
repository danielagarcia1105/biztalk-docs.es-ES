---
title: "Configuración de confirmación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- acknowledgements, acknowledgement types
- configuring, acknowledgements
ms.assetid: 99ab8caa-8788-4438-96db-8001a6523cc8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34eda8a977de0dadbad974268b46e4d580cc1f33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgment-settings"></a><span data-ttu-id="0d81e-102">Configuración de confirmación</span><span class="sxs-lookup"><span data-stu-id="0d81e-102">Acknowledgment Settings</span></span>
<span data-ttu-id="0d81e-103">Usa el **confirmación** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración (en el nivel superior **partes** pestaña) para configurar opciones de confirmación (ACK).</span><span class="sxs-lookup"><span data-stu-id="0d81e-103">You use the **Acknowledgment** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure acknowledgment (ACK) settings.</span></span>  
  
 <span data-ttu-id="0d81e-104">Están disponibles los siguientes tipos de confirmación:</span><span class="sxs-lookup"><span data-stu-id="0d81e-104">The following acknowledgment types are available:</span></span>  
  
-   <span data-ttu-id="0d81e-105">**Ninguna**.</span><span class="sxs-lookup"><span data-stu-id="0d81e-105">**None**.</span></span> <span data-ttu-id="0d81e-106">Seleccione esta opción si no desea configurar las confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="0d81e-106">Select this option if you do not want to configure any acknowledgments.</span></span>  
  
-   <span data-ttu-id="0d81e-107">**Original**.</span><span class="sxs-lookup"><span data-stu-id="0d81e-107">**Original**.</span></span> <span data-ttu-id="0d81e-108">Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**y el **MSH8 – seguridad** opciones solo.</span><span class="sxs-lookup"><span data-stu-id="0d81e-108">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and the **MSH8 – Security** options only.</span></span>  
  
-   <span data-ttu-id="0d81e-109">**Mejorado**.</span><span class="sxs-lookup"><span data-stu-id="0d81e-109">**Enhanced**.</span></span> <span data-ttu-id="0d81e-110">Seleccione esta opción para configurar todas las opciones de confirmación disponibles.</span><span class="sxs-lookup"><span data-stu-id="0d81e-110">Select this option to configure all available acknowledgment options.</span></span>  
  
-   <span data-ttu-id="0d81e-111">**Deferred**.</span><span class="sxs-lookup"><span data-stu-id="0d81e-111">**Deferred**.</span></span> <span data-ttu-id="0d81e-112">Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**, y **MSH8 – seguridad** opciones solo.</span><span class="sxs-lookup"><span data-stu-id="0d81e-112">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and **MSH8 – Security** options only.</span></span>  
  
-   <span data-ttu-id="0d81e-113">**Estático**.</span><span class="sxs-lookup"><span data-stu-id="0d81e-113">**Static**.</span></span> <span data-ttu-id="0d81e-114">Seleccione esta opción para configurar el **en caso de éxito** y **en caso de error** opciones de confirmación.</span><span class="sxs-lookup"><span data-stu-id="0d81e-114">Select this option to configure the **On success** and **On failure** acknowledgment options.</span></span>  
  
 <span data-ttu-id="0d81e-115">Una vez que se establece el tipo de confirmación, puede establecer valores para los campos de encabezado y confirmaciones, dependiendo del tipo de confirmación.</span><span class="sxs-lookup"><span data-stu-id="0d81e-115">Once the acknowledgment type is set, you can set values for header fields and acknowledgments, depending upon the acknowledgment type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d81e-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0d81e-116">In This Section</span></span>  
  
-   [<span data-ttu-id="0d81e-117">Opciones de configuración de confirmación</span><span class="sxs-lookup"><span data-stu-id="0d81e-117">ACK Configuration Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)  
  
-   [<span data-ttu-id="0d81e-118">Configurar confirmaciones de mensajes</span><span class="sxs-lookup"><span data-stu-id="0d81e-118">Configuring Message Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)