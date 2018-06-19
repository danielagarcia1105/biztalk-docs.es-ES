---
title: Agregar un puerto de envío MX | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3ad5d2f-1fcb-49d4-9974-664733308f45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cd4c16658ad0ff6b85976fbc6a97c4f397acbdb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208916"
---
# <a name="adding-an-mx-send-port"></a><span data-ttu-id="1d443-102">Agregar un puerto de envío de MX</span><span class="sxs-lookup"><span data-stu-id="1d443-102">Adding an MX Send Port</span></span>
<span data-ttu-id="1d443-103">**Para agregar un puerto de envío MX:**</span><span class="sxs-lookup"><span data-stu-id="1d443-103">**To add an MX send port:**</span></span>  
  
1.  <span data-ttu-id="1d443-104">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="1d443-104">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
2.  <span data-ttu-id="1d443-105">En el cuadro de diálogo Propiedades de puerto de envío, en el cuadro Nombre tipo **MX_SendPort**.</span><span class="sxs-lookup"><span data-stu-id="1d443-105">In the Send Port Properties dialog box, in the Name box type **MX_SendPort**.</span></span>  
  
3.  <span data-ttu-id="1d443-106">En la sección transporte, en el cuadro Tipo, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="1d443-106">In the Transport section, for the Type box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="1d443-107">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.</span><span class="sxs-lookup"><span data-stu-id="1d443-107">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="1d443-108">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="1d443-108">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="1d443-109">En el cuadro de diálogo carpeta buscar, seleccione una ubicación de archivo.</span><span class="sxs-lookup"><span data-stu-id="1d443-109">In the Browse for Folder dialog box, select a file location.</span></span>  
  
7.  <span data-ttu-id="1d443-110">En el cuadro de nombre de archivo, escriba **%MessageID%.xml**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d443-110">In the File name box, type **%MessageID%.xml**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="1d443-111">En el cuadro de diálogo Propiedades de puerto de envío, haga clic en la lista desplegable del cuadro de la canalización de envío y, a continuación, seleccione la canalización de envío que haya implementado en el proyecto de canalización.</span><span class="sxs-lookup"><span data-stu-id="1d443-111">In the Send Port Properties dialog box, click the drop-down list for the send pipeline box, and then select the send pipeline you have deployed in the pipeline project.</span></span>  
  
9. <span data-ttu-id="1d443-112">En el panel izquierdo, haga clic en **filtros**y, a continuación, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d443-112">In the left pane, click **Filters**, and then specify the following:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="1d443-113">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1d443-113">Property</span></span>|<span data-ttu-id="1d443-114">Microsoft.Solutions.MX_A4SWIFT. Property.MX_A4SWIFT_Failed</span><span class="sxs-lookup"><span data-stu-id="1d443-114">Microsoft.Solutions.MX_A4SWIFT.Property.MX_A4SWIFT_Failed</span></span>|  
    |<span data-ttu-id="1d443-115">Operador</span><span class="sxs-lookup"><span data-stu-id="1d443-115">Operator</span></span>|<span data-ttu-id="1d443-116">Seleccione ==</span><span class="sxs-lookup"><span data-stu-id="1d443-116">Select ==</span></span>|  
    |<span data-ttu-id="1d443-117">Valor</span><span class="sxs-lookup"><span data-stu-id="1d443-117">Value</span></span>|<span data-ttu-id="1d443-118">False</span><span class="sxs-lookup"><span data-stu-id="1d443-118">False</span></span>|  
  
10. <span data-ttu-id="1d443-119">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d443-119">Click **Apply**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="1d443-120">En el panel de puertos de envío, haga clic en **MX_SendPort**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="1d443-120">In the Send Ports pane, right-click **MX_SendPort**, and then click **Start**.</span></span>