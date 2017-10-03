---
title: "Cómo mostrar todas las reglas del módulo de administración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fdec550-6713-4f5f-8c04-d9218bf2df3c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08ec94eb3adb87bf6feaff032e00a61bc9b0fead
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-all-management-pack-rules"></a><span data-ttu-id="2f215-102">Cómo mostrar todas las reglas del módulo de administración</span><span class="sxs-lookup"><span data-stu-id="2f215-102">How to Display All Management Pack Rules</span></span>
<span data-ttu-id="2f215-103">Utilice el procedimiento siguiente para mostrar una lista de reglas para los módulos de administración que ha importado.</span><span class="sxs-lookup"><span data-stu-id="2f215-103">Use the following procedure to display a list of rules for the management packs that you imported.</span></span> <span data-ttu-id="2f215-104">La lista de reglas puede verse en Office Excel.</span><span class="sxs-lookup"><span data-stu-id="2f215-104">The list of rules can be viewed in Office Excel.</span></span>  
  
### <a name="to-display-management-pack-rules"></a><span data-ttu-id="2f215-105">Para mostrar las reglas del módulo de administración</span><span class="sxs-lookup"><span data-stu-id="2f215-105">To display management pack rules</span></span>  
  
1.  <span data-ttu-id="2f215-106">En el servidor de administración, haga clic en **programas**y, a continuación, haga clic en **System Center**.</span><span class="sxs-lookup"><span data-stu-id="2f215-106">In your management server, click **Programs**, and then click **System Center**.</span></span>  
  
2.  <span data-ttu-id="2f215-107">Haga clic en **Shell de comandos**.</span><span class="sxs-lookup"><span data-stu-id="2f215-107">Click **Command Shell**.</span></span>  
  
3.  <span data-ttu-id="2f215-108">En el Shell de comandos, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2f215-108">In the Command Shell, type the following command:</span></span>   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  <span data-ttu-id="2f215-109">Se crea un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="2f215-109">A .csv file is created.</span></span> <span data-ttu-id="2f215-110">Puede abrir el archivo .csv en Office Excel.</span><span class="sxs-lookup"><span data-stu-id="2f215-110">You can open the .csv file in Office Excel.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f215-111">En Office Excel, puede ser necesario para especificar que el archivo .csv es un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="2f215-111">In Office Excel, you may be required to specify that the .csv file is a text file.</span></span>