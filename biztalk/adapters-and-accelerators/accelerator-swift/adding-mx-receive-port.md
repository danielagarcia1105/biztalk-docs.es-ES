---
title: Puerto de recepción de agregar MX | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4818d6af-df1d-481e-becf-1af633735248
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69123b876bdda4b5f999277a1710cdeb1cb61fe7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209484"
---
# <a name="adding-mx-receive-port"></a><span data-ttu-id="b7511-102">Agregar MX de puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="b7511-102">Adding MX Receive Port</span></span>
<span data-ttu-id="b7511-103">**Para agregar un MX de puerto de recepción:**</span><span class="sxs-lookup"><span data-stu-id="b7511-103">**To add an MX receive port:**</span></span>  
  
1.  <span data-ttu-id="b7511-104">Iniciar **administración de BizTalk Server** consola.</span><span class="sxs-lookup"><span data-stu-id="b7511-104">Start **BizTalk Server Administration** console.</span></span>  
  
2.  <span data-ttu-id="b7511-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Aplicación de BizTalk 1**.</span><span class="sxs-lookup"><span data-stu-id="b7511-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="b7511-106">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="b7511-106">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="b7511-107">En el cuadro de diálogo Propiedades de puerto de recepción, en el cuadro Nombre, escriba **puerto de recepción de MX_**.</span><span class="sxs-lookup"><span data-stu-id="b7511-107">In the Receive Port Properties dialog box, in the Name box, type **MX_ Receive Port**.</span></span>  
  
5.  <span data-ttu-id="b7511-108">Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7511-108">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b7511-109">Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="b7511-109">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="b7511-110">En el, seleccione un cuadro de diálogo de puerto de recepción, haga clic en **puerto de recepción de MX_** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7511-110">In the Select a Receive Port dialog box, click **MX_ Receive Port**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="b7511-111">En el cuadro de diálogo Propiedades de la ubicación de recepción, en el cuadro Nombre, escriba **ubicación de recepción de MX_**.</span><span class="sxs-lookup"><span data-stu-id="b7511-111">In the Receive Location Properties dialog box, in the Name box, type **MX_ Receive Location**.</span></span>  
  
9. <span data-ttu-id="b7511-112">En la sección transporte, en el cuadro de texto de tipo, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="b7511-112">In the Transport section, for the Type text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="b7511-113">Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.</span><span class="sxs-lookup"><span data-stu-id="b7511-113">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="b7511-114">En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**y, a continuación, seleccione una ubicación de archivo.</span><span class="sxs-lookup"><span data-stu-id="b7511-114">In the FILE Transport Properties dialog box, click **Browse**, and then select a file location.</span></span>  
  
12. <span data-ttu-id="b7511-115">En el cuadro de diálogo Propiedades de transporte de archivo, asegúrese de que \*.xml se escribe en el cuadro de máscara de archivo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7511-115">In the FILE Transport Properties dialog box, ensure that \*.xml is entered in the File Mask box, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="b7511-116">En el cuadro de diálogo Propiedades de la ubicación de recepción, asegúrese de que BizTalkServerApplication se haya especificado para el cuadro de controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="b7511-116">In the Receive Location Properties dialog box, ensure that BizTalkServerApplication is entered for the Receive handler box.</span></span>  
  
14. <span data-ttu-id="b7511-117">En el cuadro de la canalización de recepción, seleccione **canalización de recepción** (la canalización de recepción que se ha implementado en el proyecto de canalización) en la lista desplegable, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7511-117">In the Receive Pipeline box, select **Receive Pipeline** (the receive pipeline that has been deployed in the Pipeline project) from the drop-down list, click **Apply**, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="b7511-118">Haga clic en la ubicación que acaba de configurar y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="b7511-118">Right-click the location you have just configured, and then click **Enable**.</span></span>