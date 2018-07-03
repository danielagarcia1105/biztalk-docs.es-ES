---
title: Instalación de paquetes acumulativos de revisiones de COM + | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110dced7d3931e1987ccf966efffb700e1c5555b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020522"
---
# <a name="installing-com-hotfix-rollup-packages"></a><span data-ttu-id="c7552-102">Instalación de paquetes acumulativos de revisiones de COM +</span><span class="sxs-lookup"><span data-stu-id="c7552-102">Installing COM+ Hotfix Rollup Packages</span></span>
> [!NOTE]  
>  <span data-ttu-id="c7552-103">En este tema es aplicable sólo a Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="c7552-103">This topic is applicable only for Windows Server 2003.</span></span>  
  
 <span data-ttu-id="c7552-104">Debe instalar la última versión del paquete de acumulativo de revisiones de COM + de Windows Server 2003 y la versión más reciente del paquete acumulativo de coordinador de transacciones distribuidas (DTC).</span><span class="sxs-lookup"><span data-stu-id="c7552-104">You should install the last version of the Windows Server 2003 COM+ hotfix rollup package and latest version of the Distributed Transaction Coordinator (DTC) rollup package.</span></span> <span data-ttu-id="c7552-105">Esto es porque los paquetes incluyen muchas correcciones de rendimiento y estabilidad.</span><span class="sxs-lookup"><span data-stu-id="c7552-105">This is because the packages include many performance and stability fixes.</span></span>  
  
 <span data-ttu-id="c7552-106">Debe instalar estos paquetes acumulativos de actualizaciones en todos los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y en todos los equipos que ejecuten SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c7552-106">You should install these rollups on all computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and on all computers running SQL Server.</span></span> <span data-ttu-id="c7552-107">Los paquetes acumulativos son especialmente importantes para la solución de BizTalk funcionar bien en escenarios de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c7552-107">The rollups are especially important for your BizTalk solution to perform well in high-throughput scenarios.</span></span>  
  
 <span data-ttu-id="c7552-108">Los problemas DTC que se han corregido son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7552-108">The DTC issues that have been fixed are as follows:</span></span>  
  
- <span data-ttu-id="c7552-109">Cierre inesperado de DTC</span><span class="sxs-lookup"><span data-stu-id="c7552-109">Unexpected DTC shutdown</span></span>  
  
- <span data-ttu-id="c7552-110">Problemas de fragmentación de memoria</span><span class="sxs-lookup"><span data-stu-id="c7552-110">Memory fragmentation issues</span></span>  
  
- <span data-ttu-id="c7552-111">DTC puede dejar de responder bajo carga</span><span class="sxs-lookup"><span data-stu-id="c7552-111">DTC may stop responding under load</span></span>  
  
- <span data-ttu-id="c7552-112">DTC puede perder memoria o deje de responder cuando se usa con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7552-112">DTC may leak memory or stop responding when used with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="c7552-113">Se ha mejorado el rendimiento de DTC bajo carga</span><span class="sxs-lookup"><span data-stu-id="c7552-113">Performance of DTC under load has been improved</span></span>  
  
## <a name="installing-the-com-rollup-package"></a><span data-ttu-id="c7552-114">Instalar el paquete de COM + paquete acumulativo de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="c7552-114">Installing the COM+ Rollup Package</span></span>  
 <span data-ttu-id="c7552-115">COM + ya no está liberando paquetes acumulativos de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="c7552-115">COM+ is no longer releasing rollup packages.</span></span> <span data-ttu-id="c7552-116">Siga esta información para instalar el último paquete de COM +:</span><span class="sxs-lookup"><span data-stu-id="c7552-116">Follow this information to install the last COM+ package:</span></span>  
  
-   <span data-ttu-id="c7552-117">La versión final de la acumulación de COM + es la "Windows Server 2003 posterior al Service Pack 2 COM + 1.5 Hotfix Rollup paquete 12".</span><span class="sxs-lookup"><span data-stu-id="c7552-117">The final version of the COM+ rollup is the “Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12”.</span></span> <span data-ttu-id="c7552-118">Esta revisión se instalará en cualquier versión de Windows Server 2003, incluso aquellos sin un service pack instalado.</span><span class="sxs-lookup"><span data-stu-id="c7552-118">This hotfix will install on any version of Windows Server 2003, even those without a service pack installed.</span></span> <span data-ttu-id="c7552-119">Para obtener más información acerca de esta revisión puede encontrarse en el artículo de Microsoft Knowledge Base 934016, ["disponibilidad de Windows Server 2003 posterior al Service Pack 2 COM + 1.5 Hotfix Rollup paquete 12"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756).</span><span class="sxs-lookup"><span data-stu-id="c7552-119">More information about this hotfix can be found in Microsoft Knowledge Base article 934016, ["Availability of Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756).</span></span>  
  
## <a name="installing-the-dtc-rollup-package"></a><span data-ttu-id="c7552-120">Instalar el paquete acumulativo de DTC</span><span class="sxs-lookup"><span data-stu-id="c7552-120">Installing the DTC Rollup Package</span></span>  
 <span data-ttu-id="c7552-121">DTC lanzará paquetes acumulativos de actualizaciones independientes de COM +.</span><span class="sxs-lookup"><span data-stu-id="c7552-121">DTC will be releasing rollup packages independent of COM+.</span></span> <span data-ttu-id="c7552-122">Siga esta información para instalar el paquete más reciente de DTC:</span><span class="sxs-lookup"><span data-stu-id="c7552-122">Follow this information to install the latest DTC package:</span></span>  
  
-   <span data-ttu-id="c7552-123">Cuando se redactó este documento, el último paquete acumulativo de revisiones DTC es "Paquete de 16".</span><span class="sxs-lookup"><span data-stu-id="c7552-123">As of this writing, the latest DTC hotfix rollup is “Package 16”.</span></span> <span data-ttu-id="c7552-124">Para obtener más información acerca de esta revisión puede encontrarse en el artículo de Microsoft Knowledge Base 958013, ["Lista de los problemas de MS DTC que se han corregido en Windows Server 2003 MS DTC Hotfix Rollup Package 16"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).</span><span class="sxs-lookup"><span data-stu-id="c7552-124">More information about this hotfix can be found in Microsoft Knowledge Base article 958013, ["List of the MS DTC issues that are fixed in Windows Server 2003 MS DTC Hotfix Rollup Package 16"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).</span></span>  
  
     <span data-ttu-id="c7552-125">El artículo de KB sobre el paquete de revisión DTC más reciente puede encontrarse mediante la búsqueda [ http://support.microsoft.com ](http://support.microsoft.com/) la frase (incluidas las comillas):</span><span class="sxs-lookup"><span data-stu-id="c7552-125">The KB article about the latest DTC hotfix rollup package can be found by searching [http://support.microsoft.com](http://support.microsoft.com/) for the phrase (including the quotes):</span></span>  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     <span data-ttu-id="c7552-126">La consulta siguiente realiza esta búsqueda para usted.</span><span class="sxs-lookup"><span data-stu-id="c7552-126">The following query does this search for you.</span></span> <span data-ttu-id="c7552-127">Elija la última de ellas:</span><span class="sxs-lookup"><span data-stu-id="c7552-127">Choose the latest one:</span></span>  
  
     [<span data-ttu-id="c7552-128">http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"</span><span class="sxs-lookup"><span data-stu-id="c7552-128">http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"</span></span>](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)