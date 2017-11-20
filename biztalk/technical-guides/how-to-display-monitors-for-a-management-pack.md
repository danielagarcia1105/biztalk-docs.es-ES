---
title: "Cómo mostrar monitores para un módulo de administración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7c4d2b3-9c01-40f5-b983-bf29a3a5cacc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b3954052159633894e59b4251ee20b1ea0844a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-monitors-for-a-management-pack"></a><span data-ttu-id="eff30-102">Cómo mostrar monitores para un módulo de administración</span><span class="sxs-lookup"><span data-stu-id="eff30-102">How to Display Monitors for a Management Pack</span></span>
<span data-ttu-id="eff30-103">Para mostrar una lista de resultados para un módulo de administración monitores e invalidaciones usando el Shell de comandos, utilice el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="eff30-103">To display a list of outputs for a management pack's monitors and overrides using the Command Shell, use the following procedure.</span></span>  
  
### <a name="to-display-monitors-for-a-management-pack"></a><span data-ttu-id="eff30-104">Para mostrar a monitores para un módulo de administración</span><span class="sxs-lookup"><span data-stu-id="eff30-104">To display monitors for a management pack</span></span>  
  
1.  <span data-ttu-id="eff30-105">En el servidor de administración, haga clic en **programas**y, a continuación, haga clic en **System Center.**</span><span class="sxs-lookup"><span data-stu-id="eff30-105">In your management server, click **Programs**, and then click **System Center.**</span></span>  
  
2.  <span data-ttu-id="eff30-106">Haga clic en **Shell de comandos**.</span><span class="sxs-lookup"><span data-stu-id="eff30-106">Click **Command Shell**.</span></span>  
  
3.  <span data-ttu-id="eff30-107">En el Shell de comandos, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="eff30-107">In the Command Shell, type the following command:</span></span>   
    `get-scommanagementpack –DisplayName “DisplayName” | get-scommonitor | export.csv filename`  
  
4.  <span data-ttu-id="eff30-108">Se crea un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="eff30-108">A .csv file is created.</span></span> <span data-ttu-id="eff30-109">El archivo .csv se puede abrir en Microsoft Office Excel.</span><span class="sxs-lookup"><span data-stu-id="eff30-109">The .csv file can be opened in Microsoft Office Excel.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eff30-110">En Excel, puede ser necesario para especificar que el archivo .csv es un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="eff30-110">In Excel, you may be required to specify that the .csv file is a text file.</span></span>  
  
 <span data-ttu-id="eff30-111">Por ejemplo, el comando siguiente recupera datos para los monitores asociados a uno de los módulos de administración principales:</span><span class="sxs-lookup"><span data-stu-id="eff30-111">For example, the following command retrieves data for the monitors associated with one of the core management packs:</span></span>   
`get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-ScomMonitor | export-csv "c:\monitors.csv"`