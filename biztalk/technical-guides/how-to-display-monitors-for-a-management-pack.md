---
title: Cómo mostrar monitores para un módulo de administración | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7c4d2b3-9c01-40f5-b983-bf29a3a5cacc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d561c7b49c47d59f7affccaaee582e26db500c09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010277"
---
# <a name="how-to-display-monitors-for-a-management-pack"></a><span data-ttu-id="f3d67-102">Cómo mostrar monitores para un módulo de administración</span><span class="sxs-lookup"><span data-stu-id="f3d67-102">How to Display Monitors for a Management Pack</span></span>
<span data-ttu-id="f3d67-103">Para mostrar una lista de salidas de un módulo de administración monitores e invalidaciones usando el Shell de comandos, utilice el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="f3d67-103">To display a list of outputs for a management pack's monitors and overrides using the Command Shell, use the following procedure.</span></span>  
  
### <a name="to-display-monitors-for-a-management-pack"></a><span data-ttu-id="f3d67-104">Para mostrar a monitores para un módulo de administración</span><span class="sxs-lookup"><span data-stu-id="f3d67-104">To display monitors for a management pack</span></span>  
  
1. <span data-ttu-id="f3d67-105">En el servidor de administración, haga clic en **programas**y, a continuación, haga clic en **System Center.**</span><span class="sxs-lookup"><span data-stu-id="f3d67-105">In your management server, click **Programs**, and then click **System Center.**</span></span>  
  
2. <span data-ttu-id="f3d67-106">Haga clic en **Shell de comandos**.</span><span class="sxs-lookup"><span data-stu-id="f3d67-106">Click **Command Shell**.</span></span>  
  
3. <span data-ttu-id="f3d67-107">En el Shell de comandos, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f3d67-107">In the Command Shell, type the following command:</span></span>   
   `get-scommanagementpack –DisplayName “DisplayName” | get-scommonitor | export.csv filename`  
  
4. <span data-ttu-id="f3d67-108">Se crea un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f3d67-108">A .csv file is created.</span></span> <span data-ttu-id="f3d67-109">El archivo .csv se puede abrir en Microsoft Office Excel.</span><span class="sxs-lookup"><span data-stu-id="f3d67-109">The .csv file can be opened in Microsoft Office Excel.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="f3d67-110">En Excel, puede requerirse para especificar que el archivo .csv es un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f3d67-110">In Excel, you may be required to specify that the .csv file is a text file.</span></span>  
  
   <span data-ttu-id="f3d67-111">Por ejemplo, el comando siguiente recupera los datos para los monitores asociados a uno de los módulos de administración principales:</span><span class="sxs-lookup"><span data-stu-id="f3d67-111">For example, the following command retrieves data for the monitors associated with one of the core management packs:</span></span>   
   `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-ScomMonitor | export-csv "c:\monitors.csv"`