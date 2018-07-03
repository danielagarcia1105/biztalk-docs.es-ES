---
title: Cómo mostrar invalidaciones para un módulo de administración | Microsoft Docs
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
ms.openlocfilehash: bc2a40fde14001668f94549240643160fd1af73a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979661"
---
# <a name="how-to-display-overrides-for-a-management-pack"></a><span data-ttu-id="ada68-102">Cómo mostrar invalidaciones para un módulo de administración</span><span class="sxs-lookup"><span data-stu-id="ada68-102">How to Display Overrides for a Management Pack</span></span>
<span data-ttu-id="ada68-103">Para mostrar invalidaciones para un módulo de administración, use el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="ada68-103">To display overrides for a management pack, use the following procedure.</span></span>  
  
### <a name="to-display-overrides-for-a-management-pack"></a><span data-ttu-id="ada68-104">Para mostrar invalidaciones para un módulo de administración</span><span class="sxs-lookup"><span data-stu-id="ada68-104">To display overrides for a management pack</span></span>  
  
1. <span data-ttu-id="ada68-105">En el servidor de administración, haga clic en **programas**y, a continuación, haga clic en **System Center**.</span><span class="sxs-lookup"><span data-stu-id="ada68-105">In your management server, click **Programs**, and then click **System Center**.</span></span>  
  
2. <span data-ttu-id="ada68-106">Haga clic en **Shell de comandos**.</span><span class="sxs-lookup"><span data-stu-id="ada68-106">Click **Command Shell**.</span></span>  
  
3. <span data-ttu-id="ada68-107">En el Shell de comandos, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ada68-107">In the Command Shell, type the following command:</span></span>   
   `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
   `$mp.GetOverrides()`  
  
4. <span data-ttu-id="ada68-108">Se crea un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ada68-108">A .csv file is created.</span></span> <span data-ttu-id="ada68-109">El archivo .csv se puede abrir en Office Excel.</span><span class="sxs-lookup"><span data-stu-id="ada68-109">The .csv file can be opened in Office Excel.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="ada68-110">En Office Excel, puede requerirse para especificar que el archivo .csv es un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="ada68-110">In Office Excel, you may be required to specify that the .csv file is a text file.</span></span>  
  
   <span data-ttu-id="ada68-111">Por ejemplo, el comando siguiente muestra las anulaciones para uno de los módulos de administración principales:</span><span class="sxs-lookup"><span data-stu-id="ada68-111">For example, the following command displays the overrides for one of the core management packs:</span></span>   
   `$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
   `$mp.GetOverrides()`