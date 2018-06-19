---
title: Cómo mostrar invalidaciones para un módulo de administración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8261a514-b4c4-4e6b-ac35-40a3e3e090e0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a28c4ab2ef8f82fdd770203816239ad78e74418e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297692"
---
# <a name="how-to-display-overrides-for-a-management-pack"></a><span data-ttu-id="7deed-102">Cómo mostrar invalidaciones para un módulo de administración</span><span class="sxs-lookup"><span data-stu-id="7deed-102">How to Display Overrides for a Management Pack</span></span>
<span data-ttu-id="7deed-103">Para mostrar invalidaciones para un módulo de administración, utilice el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="7deed-103">To display overrides for a management pack, use the following procedure.</span></span>  
  
### <a name="to-display-overrides-for-a-management-pack"></a><span data-ttu-id="7deed-104">Para mostrar invalidaciones para un módulo de administración</span><span class="sxs-lookup"><span data-stu-id="7deed-104">To display overrides for a management pack</span></span>  
  
1.  <span data-ttu-id="7deed-105">En el servidor de administración, haga clic en **programas**y, a continuación, haga clic en **System Center**.</span><span class="sxs-lookup"><span data-stu-id="7deed-105">In your management server, click **Programs**, and then click **System Center**.</span></span>  
  
2.  <span data-ttu-id="7deed-106">Haga clic en **Shell de comandos**.</span><span class="sxs-lookup"><span data-stu-id="7deed-106">Click **Command Shell**.</span></span>  
  
3.  <span data-ttu-id="7deed-107">En el Shell de comandos, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7deed-107">In the Command Shell, type the following command:</span></span>   
    `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
    `$mp.GetOverrides()`  
  
4.  <span data-ttu-id="7deed-108">Se crea un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="7deed-108">A .csv file is created.</span></span> <span data-ttu-id="7deed-109">El archivo .csv se puede abrir en Office Excel.</span><span class="sxs-lookup"><span data-stu-id="7deed-109">The .csv file can be opened in Office Excel.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7deed-110">En Office Excel, puede ser necesario para especificar que el archivo .csv es un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7deed-110">In Office Excel, you may be required to specify that the .csv file is a text file.</span></span>  
  
 <span data-ttu-id="7deed-111">Por ejemplo, el comando siguiente muestra las anulaciones para uno de los módulos de administración principales:</span><span class="sxs-lookup"><span data-stu-id="7deed-111">For example, the following command displays the overrides for one of the core management packs:</span></span>   
`$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
`$mp.GetOverrides()`