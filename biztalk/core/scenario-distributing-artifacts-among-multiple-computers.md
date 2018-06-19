---
title: 'Escenario: Distribuir artefactos entre varios equipos | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [artifacts], multiple computers
- examples, distributing
- examples, artifacts
- artifacts, distributing
- artifacts, examples
- deploying [artifacts], examples
- examples, deploying
ms.assetid: 7000cded-1fda-4276-b7f3-3f427f686f64
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abedc60ad13c7e8b2be3ce4caa7b8d34262b4e5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269164"
---
# <a name="scenario-distributing-artifacts-among-multiple-computers"></a><span data-ttu-id="ee572-102">Escenario: Distribuir artefactos entre varios equipos</span><span class="sxs-lookup"><span data-stu-id="ee572-102">Scenario: Distributing Artifacts Among Multiple Computers</span></span>
<span data-ttu-id="ee572-103">En este tema se describe el escenario de implementación de la aplicación cuando los artefactos de una aplicación se instalan de forma selectiva en diferentes equipos.</span><span class="sxs-lookup"><span data-stu-id="ee572-103">This topic describes the application deployment scenario when the artifacts in an application are selectively installed on different computers.</span></span> <span data-ttu-id="ee572-104">Puede que desee hacerlo si quiere instalar determinados ensamblados u otros tipos de artefactos de una aplicación solo en determinados equipos de un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ee572-104">You might want to do this if you want certain assemblies or other types of artifacts in an application to be installed only on specific computers in a BizTalk group.</span></span> <span data-ttu-id="ee572-105">Para ello, puede exportar los artefactos que se incluyen en una aplicación a varios archivos .msi, según los artefactos que desee instalar juntos en un equipo físico.</span><span class="sxs-lookup"><span data-stu-id="ee572-105">To do this, you can export the artifacts included in an application into multiple .msi files, according to which artifacts you want to install together on a physical computer.</span></span>  
  
 <span data-ttu-id="ee572-106">El siguiente diagrama muestra un archivo .msi que se importa en la base de datos de administración de BizTalk para el grupo de BizTalk 1.</span><span class="sxs-lookup"><span data-stu-id="ee572-106">The following diagram shows an .msi file that is imported into the BizTalk Management database for BizTalk Group 1.</span></span> <span data-ttu-id="ee572-107">Esto crea la aplicación de procesamiento de pedidos y todos sus artefactos en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="ee572-107">This creates the Order Processing application and all of its artifacts in that group.</span></span> <span data-ttu-id="ee572-108">Los artefactos de la aplicación se exportan, a continuación, a dos archivos .msi diferentes.</span><span class="sxs-lookup"><span data-stu-id="ee572-108">The application artifacts are then exported into two different .msi files.</span></span> <span data-ttu-id="ee572-109">Un archivo .msi contiene Assembly1, Certificate1 y Script1.</span><span class="sxs-lookup"><span data-stu-id="ee572-109">One .msi file contains Assembly1, Certificate1, and Script1.</span></span> <span data-ttu-id="ee572-110">El otro archivo .msi contiene Assembly2, Script2 y VirtualDirectory1.</span><span class="sxs-lookup"><span data-stu-id="ee572-110">The other .msi file contains Assembly2, Script2, and VirtualDirectory1.</span></span>  
  
 <span data-ttu-id="ee572-111">Ambos archivos .msi se importan en 2 del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ee572-111">Both .msi files are imported into BizTalk Group 2.</span></span> <span data-ttu-id="ee572-112">Ya que ambos pertenecen a la aplicación de procesamiento de pedidos, todos los artefactos en los dos archivos .msi se importan en la misma aplicación, denominada procesamiento de pedidos en el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="ee572-112">Because they both belong to the Order Processing application, all of the artifacts in both .msi files are imported into the same application named Order Processing in the new group.</span></span>  
  
 <span data-ttu-id="ee572-113">Además, los artefactos de la aplicación se instalan de los archivos .msi en los equipos del grupo que los ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="ee572-113">In addition, the application artifacts are installed from the .msi files onto the computers in the group that will run them.</span></span> <span data-ttu-id="ee572-114">Observe que el archivo .msi que contiene el directorio virtual se instala en el servidor B y en el servidor C de BizTalk Server; los dos que ejecutan IIS.</span><span class="sxs-lookup"><span data-stu-id="ee572-114">Note that the .msi file containing the virtual directory is installed on BizTalk Server B and BizTalk Server C, which are both running IIS.</span></span>  
  
 <span data-ttu-id="ee572-115">![Artefactos instalados en equipos diferentes](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")</span><span class="sxs-lookup"><span data-stu-id="ee572-115">![Artifacts installed on different computers](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee572-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee572-116">See Also</span></span>  
 <span data-ttu-id="ee572-117">[Escenarios de administración e implementación de aplicaciones](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="ee572-117">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 <span data-ttu-id="ee572-118">[Cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="ee572-118">[How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md) </span></span>  
 <span data-ttu-id="ee572-119">[Cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="ee572-119">[How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="ee572-120">Cómo instalar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ee572-120">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)