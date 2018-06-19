---
title: Automatizar el servidor BizTalk Server Performance Tuning | Documentos de Microsoft
description: Utilizar BTSTask para importar o exportar la configuración de rendimiento entre los entornos de servidor BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07ff73b5-25d9-4f3f-9a4b-127c0b843741
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e4ea364345ed9f2a8f642e11650cfcd9d09f10f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230356"
---
# <a name="automate-biztalk-server-performance-tuning"></a><span data-ttu-id="ef4a7-103">Automatizar el servidor BizTalk Server ajuste del rendimiento</span><span class="sxs-lookup"><span data-stu-id="ef4a7-103">Automate BizTalk Server Performance Tuning</span></span>

## <a name="overview"></a><span data-ttu-id="ef4a7-104">Información general</span><span class="sxs-lookup"><span data-stu-id="ef4a7-104">Overview</span></span>
<span data-ttu-id="ef4a7-105">Puede automatizar el ajuste de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración de rendimiento mediante la importación o exportación de la configuración de BizTalk o manipulando la configuración mediante [WMI](http://go.microsoft.com/fwlink/?LinkId=200464).</span><span class="sxs-lookup"><span data-stu-id="ef4a7-105">You can automate the tuning of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance settings either by importing or exporting the BizTalk settings or by manipulating the settings using [WMI](http://go.microsoft.com/fwlink/?LinkId=200464).</span></span>  
  
 <span data-ttu-id="ef4a7-106">Una vez configurado el entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para un óptimo rendimiento, puede exportar o importar la configuración de BizTalk Server a un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="ef4a7-106">After the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is set up for optimum performance, you can export or import the BizTalk Server settings to an XML file.</span></span> <span data-ttu-id="ef4a7-107">Puede importar/exportar la configuración de BizTalk Server usando el Panel de configuración o la utilidad de línea de comandos BTSTask.</span><span class="sxs-lookup"><span data-stu-id="ef4a7-107">You can import/export the BizTalk Server settings either using the Settings Dashboard or the BTSTask command-line utility.</span></span> <span data-ttu-id="ef4a7-108">**BTSTask.exe** con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite a los administradores de BizTalk utilizar comandos de BTSTask al crear nuevos scripts.</span><span class="sxs-lookup"><span data-stu-id="ef4a7-108">**BTSTask.exe** with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] allows BizTalk administrators to use BTSTask commands when creating new scripts.</span></span>  
  
 <span data-ttu-id="ef4a7-109">Para obtener información acerca de cómo importar o exportar configuración de BizTalk Server de un entorno a otro utilizando [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], consulte [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="ef4a7-109">For information about importing/exporting BizTalk Server settings from one environment to another using [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="ef4a7-110">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ef4a7-110">Next steps</span></span> 
  
-   [<span data-ttu-id="ef4a7-111">Importar o exportar BTSTask de uso de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ef4a7-111">Import or export BizTalk Settings Using BTSTask</span></span>](../core/how-to-import-biztalk-settings-using-btstask.md)  
  
- [<span data-ttu-id="ef4a7-112">Referencia de línea de comandos de BTSTask</span><span class="sxs-lookup"><span data-stu-id="ef4a7-112">BTSTask Command-Line Reference</span></span>](btstask-command-line-reference.md)
  
## <a name="see-also"></a><span data-ttu-id="ef4a7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef4a7-113">See Also</span></span>  
 [<span data-ttu-id="ef4a7-114">Administración de la configuración de rendimiento de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ef4a7-114">Managing BizTalk Server Performance Settings</span></span>](../core/managing-biztalk-server-performance-settings.md)