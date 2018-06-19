---
title: Normas europeas de configuración seguridad CIDX intercambio de mensajes | Documentos de Microsoft
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
ms.openlocfilehash: 4c4606dfc4b912d884a997bb65acb26cb4352448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210500"
---
# <a name="setting-up-cidx-estandards-message-exchange"></a><span data-ttu-id="6c06b-102">Normas europeas de configuración seguridad CIDX intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="6c06b-102">Setting Up CIDX eStandards Message Exchange</span></span>
<span data-ttu-id="6c06b-103">En este tema se describe cómo configurar el intercambio de mensajes de normas europeas de intercambio de datos para la industria química (CIDX).</span><span class="sxs-lookup"><span data-stu-id="6c06b-103">This topic describes how to set up Chemical Data Exchange (CIDX) eStandards message exchange.</span></span> <span data-ttu-id="6c06b-104">CIDX requiere que se establezcan las tres propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c06b-104">CIDX requires that you set the following three properties:</span></span>  
  
-   <span data-ttu-id="6c06b-105">`Standard`propiedad en los valores de configuración de proceso para **CIDX**</span><span class="sxs-lookup"><span data-stu-id="6c06b-105">`Standard` property in the process configuration settings to **CIDX**</span></span>  
  
-   <span data-ttu-id="6c06b-106">`Is Single Action`propiedad en las opciones de configuración de proceso`True`</span><span class="sxs-lookup"><span data-stu-id="6c06b-106">`Is Single Action` property in the process configuration settings to `True`</span></span>  
  
-   <span data-ttu-id="6c06b-107">`0A1 agreement`propiedad en el acuerdo de socio comercial a **No 0A1**</span><span class="sxs-lookup"><span data-stu-id="6c06b-107">`0A1 agreement` property in the trading partner agreement to **No 0A1**</span></span>  
  
 <span data-ttu-id="6c06b-108">Para obtener información sobre las diferencias entre CIDX y RosettaNet, consulte [CIDX compatibilidad](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md).</span><span class="sxs-lookup"><span data-stu-id="6c06b-108">For information about the differences between CIDX and RosettaNet, see [CIDX Support](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md).</span></span>  
  
### <a name="to-set-up-cidx-message-exchange"></a><span data-ttu-id="6c06b-109">Para configurar el intercambio de mensajes CIDX</span><span class="sxs-lookup"><span data-stu-id="6c06b-109">To set up CIDX message exchange</span></span>  
  
1.  <span data-ttu-id="6c06b-110">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.</span><span class="sxs-lookup"><span data-stu-id="6c06b-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="6c06b-111">En el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c06b-111">In the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].</span></span>  
  
3.  <span data-ttu-id="6c06b-112">Haga clic con el botón derecho en **Opciones de configuración de procesos**, seleccione **Nuevo**y haga clic en **Configuración de procesos**.</span><span class="sxs-lookup"><span data-stu-id="6c06b-112">Right-click **Process Configuration Settings**, point to **New**, and then click **Process Configuration**.</span></span>  
  
4.  <span data-ttu-id="6c06b-113">En el cuadro de diálogo Propiedades de configuración de proceso nuevo, en la **General** ficha, para el **estándar** propiedad, seleccione **CIDX**.</span><span class="sxs-lookup"><span data-stu-id="6c06b-113">In the New Process Configuration Properties dialog box, on the **General** tab, for the **Standard** property, select **CIDX**.</span></span>  
  
5.  <span data-ttu-id="6c06b-114">En el **actividad** ficha, para el **es la única acción** propiedad, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="6c06b-114">On the **Activity** tab, for the **Is Single Action** property, select **True**.</span></span>  
  
6.  <span data-ttu-id="6c06b-115">Especifique otras opciones de configuración de proceso según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6c06b-115">Enter other process configuration settings as needed.</span></span> <span data-ttu-id="6c06b-116">Para obtener información acerca de estas opciones, vea la tabla de [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="6c06b-116">For information about these settings, see the table in [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
7.  <span data-ttu-id="6c06b-117">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c06b-117">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="6c06b-118">Haga clic en **contratos**, seleccione **New**y, a continuación, haga clic en **acuerdo**.</span><span class="sxs-lookup"><span data-stu-id="6c06b-118">Right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
9. <span data-ttu-id="6c06b-119">En el **General**, **puertos**, **protocolo**, y **propiedades personalizadas** fichas, introduzca valores para las distintas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="6c06b-119">On the **General**, **Ports**, **Protocol**, and **Custom Properties** tabs, enter the values for the various settings.</span></span> <span data-ttu-id="6c06b-120">Para obtener información acerca de estas opciones, vea la tabla de [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span><span class="sxs-lookup"><span data-stu-id="6c06b-120">For information about these settings, see the table in [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
10. <span data-ttu-id="6c06b-121">En el cuadro de diálogo Propiedades del acuerdo nuevo, en la **General** ficha, para el **0A1 acuerdo** propiedad, seleccione **No 0A1**.</span><span class="sxs-lookup"><span data-stu-id="6c06b-121">In the New Agreement Properties dialog box, on the **General** tab, for the **0A1 agreement** property, select **No 0A1**.</span></span>  
  
11. <span data-ttu-id="6c06b-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c06b-122">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c06b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c06b-123">See Also</span></span>  
 <span data-ttu-id="6c06b-124">[Cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6c06b-124">[How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span></span>  
 <span data-ttu-id="6c06b-125">[Crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="6c06b-125">[Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span></span>  
 <span data-ttu-id="6c06b-126">[Creación o edición de la organización principal](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span><span class="sxs-lookup"><span data-stu-id="6c06b-126">[Creating or Editing a Home Organization](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span></span>  
 [<span data-ttu-id="6c06b-127">Crear o editar un socio</span><span class="sxs-lookup"><span data-stu-id="6c06b-127">Creating or Editing a Partner</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)