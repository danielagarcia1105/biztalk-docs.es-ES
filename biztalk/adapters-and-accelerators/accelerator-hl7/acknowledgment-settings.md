---
title: Configuración de las confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- acknowledgements, acknowledgement types
- configuring, acknowledgements
ms.assetid: 99ab8caa-8788-4438-96db-8001a6523cc8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c1f19fa1a0d1abaad29f454f25f0d8608ed497
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967141"
---
# <a name="acknowledgment-settings"></a><span data-ttu-id="4cc4d-102">Configuración de confirmación</span><span class="sxs-lookup"><span data-stu-id="4cc4d-102">Acknowledgment Settings</span></span>
<span data-ttu-id="4cc4d-103">Usa el **confirmación** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración (bajo el alto nivel **partes** pestaña) para configurar las opciones de confirmación (ACK).</span><span class="sxs-lookup"><span data-stu-id="4cc4d-103">You use the **Acknowledgment** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure acknowledgment (ACK) settings.</span></span>  
  
 <span data-ttu-id="4cc4d-104">Están disponibles los siguientes tipos de confirmación:</span><span class="sxs-lookup"><span data-stu-id="4cc4d-104">The following acknowledgment types are available:</span></span>  
  
- <span data-ttu-id="4cc4d-105">**Ninguna**.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-105">**None**.</span></span> <span data-ttu-id="4cc4d-106">Seleccione esta opción si no desea configurar confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-106">Select this option if you do not want to configure any acknowledgments.</span></span>  
  
- <span data-ttu-id="4cc4d-107">**Original**.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-107">**Original**.</span></span> <span data-ttu-id="4cc4d-108">Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**y el **MSH8 – seguridad** sólo las opciones.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-108">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and the **MSH8 – Security** options only.</span></span>  
  
- <span data-ttu-id="4cc4d-109">**Mejorado**.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-109">**Enhanced**.</span></span> <span data-ttu-id="4cc4d-110">Seleccione esta opción para configurar todas las opciones disponibles de confirmación.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-110">Select this option to configure all available acknowledgment options.</span></span>  
  
- <span data-ttu-id="4cc4d-111">**Aplaza**.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-111">**Deferred**.</span></span> <span data-ttu-id="4cc4d-112">Seleccione esta opción para configurar **MSH1: separador de campos**, **MSH2: codificación de caracteres**, y **MSH8 – seguridad** sólo las opciones.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-112">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and **MSH8 – Security** options only.</span></span>  
  
- <span data-ttu-id="4cc4d-113">**Estática**.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-113">**Static**.</span></span> <span data-ttu-id="4cc4d-114">Seleccione esta opción para configurar el **en caso de éxito** y **en caso de error** opciones de confirmación.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-114">Select this option to configure the **On success** and **On failure** acknowledgment options.</span></span>  
  
  <span data-ttu-id="4cc4d-115">Una vez que se establece el tipo de confirmación, puede establecer los valores de campos de encabezado y las confirmaciones, en función del tipo de confirmación.</span><span class="sxs-lookup"><span data-stu-id="4cc4d-115">Once the acknowledgment type is set, you can set values for header fields and acknowledgments, depending upon the acknowledgment type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4cc4d-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4cc4d-116">In This Section</span></span>  
  
-   [<span data-ttu-id="4cc4d-117">Parámetros de configuración de ACK</span><span class="sxs-lookup"><span data-stu-id="4cc4d-117">ACK Configuration Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)  
  
-   [<span data-ttu-id="4cc4d-118">Configuración de confirmaciones de mensajes</span><span class="sxs-lookup"><span data-stu-id="4cc4d-118">Configuring Message Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)