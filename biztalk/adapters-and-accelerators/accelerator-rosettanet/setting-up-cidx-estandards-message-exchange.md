---
title: Configuración CIDX las normas europeas de intercambio de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, configuring message exchange
ms.assetid: 90468459-cef7-436b-8c0b-3a7455a091c3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2aef1c49ca4bb87ef2e9388b9cdfcc86d2f35f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988869"
---
# <a name="setting-up-cidx-estandards-message-exchange"></a><span data-ttu-id="80494-102">Configuración CIDX las normas europeas de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="80494-102">Setting Up CIDX eStandards Message Exchange</span></span>
<span data-ttu-id="80494-103">Este tema describe cómo configurar el intercambio de mensajes de las normas europeas de intercambio de datos química (CIDX).</span><span class="sxs-lookup"><span data-stu-id="80494-103">This topic describes how to set up Chemical Data Exchange (CIDX) eStandards message exchange.</span></span> <span data-ttu-id="80494-104">CIDX requiere que establezca las tres propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="80494-104">CIDX requires that you set the following three properties:</span></span>  
  
- <span data-ttu-id="80494-105">`Standard` propiedad en la configuración del proceso para **CIDX**</span><span class="sxs-lookup"><span data-stu-id="80494-105">`Standard` property in the process configuration settings to **CIDX**</span></span>  
  
- <span data-ttu-id="80494-106">`Is Single Action` propiedad de los valores de configuración de proceso a `True`</span><span class="sxs-lookup"><span data-stu-id="80494-106">`Is Single Action` property in the process configuration settings to `True`</span></span>  
  
- <span data-ttu-id="80494-107">`0A1 agreement` propiedad en el acuerdo de socio comercial a **ningún 0A1**</span><span class="sxs-lookup"><span data-stu-id="80494-107">`0A1 agreement` property in the trading partner agreement to **No 0A1**</span></span>  
  
  <span data-ttu-id="80494-108">Para obtener información sobre las diferencias entre CIDX y RosettaNet, consulte [compatibilidad con CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md).</span><span class="sxs-lookup"><span data-stu-id="80494-108">For information about the differences between CIDX and RosettaNet, see [CIDX Support](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md).</span></span>  
  
### <a name="to-set-up-cidx-message-exchange"></a><span data-ttu-id="80494-109">Para configurar el intercambio de mensajes CIDX</span><span class="sxs-lookup"><span data-stu-id="80494-109">To set up CIDX message exchange</span></span>  
  
1. <span data-ttu-id="80494-110">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span><span class="sxs-lookup"><span data-stu-id="80494-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="80494-111">En el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80494-111">In the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].</span></span>  
  
3. <span data-ttu-id="80494-112">Haga clic con el botón derecho en **Opciones de configuración de procesos**, seleccione **Nuevo**y haga clic en **Configuración de procesos**.</span><span class="sxs-lookup"><span data-stu-id="80494-112">Right-click **Process Configuration Settings**, point to **New**, and then click **Process Configuration**.</span></span>  
  
4. <span data-ttu-id="80494-113">En el cuadro de diálogo Propiedades de configuración de proceso nuevo, en el **General** ficha, para el **estándar** propiedad, seleccione **CIDX**.</span><span class="sxs-lookup"><span data-stu-id="80494-113">In the New Process Configuration Properties dialog box, on the **General** tab, for the **Standard** property, select **CIDX**.</span></span>  
  
5. <span data-ttu-id="80494-114">En el **actividad** ficha, para el **es la única acción** propiedad, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="80494-114">On the **Activity** tab, for the **Is Single Action** property, select **True**.</span></span>  
  
6. <span data-ttu-id="80494-115">Especifique otras opciones de configuración de proceso según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="80494-115">Enter other process configuration settings as needed.</span></span> <span data-ttu-id="80494-116">Para obtener información sobre estas opciones, vea la tabla en [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="80494-116">For information about these settings, see the table in [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
7. <span data-ttu-id="80494-117">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="80494-117">Click **OK**.</span></span>  
  
8. <span data-ttu-id="80494-118">Haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **contrato**.</span><span class="sxs-lookup"><span data-stu-id="80494-118">Right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
9. <span data-ttu-id="80494-119">En el **General**, **puertos**, **protocolo**, y **propiedades personalizadas** fichas, introduzca valores para las distintas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="80494-119">On the **General**, **Ports**, **Protocol**, and **Custom Properties** tabs, enter the values for the various settings.</span></span> <span data-ttu-id="80494-120">Para obtener información sobre estas opciones, vea la tabla en [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span><span class="sxs-lookup"><span data-stu-id="80494-120">For information about these settings, see the table in [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
10. <span data-ttu-id="80494-121">En el cuadro de diálogo Propiedades de nuevo contrato, en el **General** ficha, para el **0A1 acuerdo** propiedad, seleccione **ningún 0A1**.</span><span class="sxs-lookup"><span data-stu-id="80494-121">In the New Agreement Properties dialog box, on the **General** tab, for the **0A1 agreement** property, select **No 0A1**.</span></span>  
  
11. <span data-ttu-id="80494-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="80494-122">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80494-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="80494-123">See Also</span></span>  
 <span data-ttu-id="80494-124">[Cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="80494-124">[How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span></span>  
 <span data-ttu-id="80494-125">[Crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="80494-125">[Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span></span>  
 <span data-ttu-id="80494-126">[Creación o edición de la organización principal](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span><span class="sxs-lookup"><span data-stu-id="80494-126">[Creating or Editing a Home Organization](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span></span>  
 [<span data-ttu-id="80494-127">Creación o edición de un socio</span><span class="sxs-lookup"><span data-stu-id="80494-127">Creating or Editing a Partner</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)